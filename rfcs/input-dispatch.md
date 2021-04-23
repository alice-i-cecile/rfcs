# Feature Name: `input-dispatch`

## Summary

Raw input events are taken in by the central dispatch, handled according to the input handler components and then transformed into actions.

## Motivation

Directly reading input streams is simple, but doesn't scale well.
Rebinding, multiple interchangeable input devices, and more advanced input paradigms like "overlapping widgets" or "widget cycling"
all require a more cohesive framework.

By passing our inputs through a central dispatch, converting raw inputs into actions, we can expose a much cleaner abstraction to our gameplay code and enable a data-driven workflow for input handling.

## Guide-level explanation

Every game must eventually, on some terrible day, actually accept input from its users.
In Bevy, that means they must listen for **input events**, created by your mouse, keyboard, joystick, touch or hand-rolled hum-to-move input pipeline.
But once we receive an input event, what are we to make of it?

For simple prototypes, it makes sense to take a simple approach: just listen to the event stream you care about directly.

```rust
fn jump(query: Query<&mut Velocity, With<Player>>, keyboard_input: Res<Input<KeyCode>>) {
    if keyboard_input.just_pressed(KeyCode::Space) {
        let mut vel = query.single_mut().unwrap();
        vel += Velocity::new(0.0, 1.0);
    }
}
```

This feels natural when building out simple gameplay systems, but if you were so inclined, you could extend this out to classical "user interfaces":
reading the mouse's position and then fire off a button event if the mouse was over a button at the time it was clicked.

While refreshingly simple and perfectly modular, this approach runs into some challenges as you attempt to scale it out to more complex games:

1. Your input logic is scattered across your code-base, making writing a rebinding interface very hard.
2. Supporting multiple input methods (e.g. mouse and hotkeys or gamepad and keyboard) becomes very complex. Do you duplicate these systems? Do you read in two input streams?
3. Handling input events that rely on information from other entities and systems is very frustrating.
   1. Consider overlapping clickable UI widgets; you can't rely on a button's position alone to tell you whether it's correct to execute as that section may be covered.
   2. In game play systems, actors can typically only do one thing at once, or combinations result in different non-additive behavior.
4. Each system listens to the whole input stream of events. When you have 100 different systems, and they each discard 99% of all candidate input events, this creates unnecessary performance drag.

This is where Bevy's **central input dispatch** comes in.
Here's the high-level overview:

1. Every entity that responds to input through the central input dispatch has the `Interactable` component.
These may be classic UI widgets, pure gameplay objects, or something in between.
2. Each `Interactable` entity also has some number of `InputHandler<E>` components which convert raw input events to entity-specific **action events** (`E`) that they store in that component.
3. Because we can map from several input streams to a single unified entity-specific event, we can unify multiple input methods without code duplication.
4. By changing the fields of the `InputHandler` components, we can quickly rebind our user interfaces or design them in a data-driven fashion.
5. A central `dispatch_input` system collects all of our input streams, parses the events according to the rules of our input handlers, then stores the transformed events in the appropriate entity-specific event components.
6. These entity-specific events are then handled as usual on a per-entity basis in later systems, where their actual effects occur.

### Multiple inputs

### Crossing the streams

### C-c-c-combos

### Pointers

### Selection cycling

## Reference-level explanation

### `InputHandler`

### The `dispatch_input` exclusive system

### Pointer disambiguation

### Selection cycling

## Drawbacks

1. This is a complex problem domain that will take a fair bit of developer effort to design, build and maintain.
2. Including this as part of Bevy itself means that we need to design to accommodate arbitrary new input streams.
3. There will be two ways to handle inputs: we can't (and probably don't want) disable the simple approach.

## Rationale and alternatives

### Why do we need a central dispatch?

### Why does the logic need to be stored as data?

### Why don't we have more complex logic in our input handlers?

## \[Optional\] Prior art

### Input Mapping

There are already two basic third-party crates in Bevy to cover some of this functionality:

- [`bevy_input_actionmap`](https://github.com/lightsoutgames/bevy_input_actionmap)
- [`kurinji`](https://crates.io/crates/kurinji)

### Pointer disambiguation

The existing [focus system](https://github.com/bevyengine/bevy/blob/cf221f9659127427c99d621b76c8085c4860e2ef/crates/bevy_ui/src/focus.rs).

### Selection cycling

## Unresolved questions

1. Pointer disambiguation algorithm
2. Selection cycling algorithm
3. Configuration API for event mapping

## \[Optional\] Future possibilities

This work directly enables #11, by providing a source of clean actions for our UI widgets to read from.

Down the line, this abstraction layer will enable serious automation for testing and machine learning purposes, as these interfaces can write to action events directly.

Getting this right is vitally important to ensuring that games and apps made in Bevy are accessible.
Alternative input paradigms are vitally important to a wide range of accommodations,
and proper selection cycling is critical to keyboard and screen-reader workflows.
