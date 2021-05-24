# Feature Name: 'quick-start-book'

## Summary

The [Bevy book](https://bevyengine.org/learn/book/introduction/) will be extended by the community, and supplemented by a Quick Start guide.

## Motivation

The Bevy book has fallen behind the pace of Bevy's features, leaving newcomers a bit baffled and worried about the state of the documentation.

## User-facing explanation

So, you want to help write some learning material for the [Bevy website](https://bevyengine.org/)?

As you probably noticed, our introductory learning material is split into two main sections:

1. **Bevy Quick Start:** "Get started making your first game now!"
2. **Bevy Book:** "Understand how Bevy works, and how you can use it"

This is intended to cater to two different types of learners, without compromising the experience for either:

- **Example-first:** These users want to dive right in, see everything in action and get a working game as quickly as possible.
These users often have an idea in their mind that they want to start prototyping as quickly as possible.
- **Definition-first:** These users want to carefully build up a mental model of Bevy, thoroughly understanding each new concept before moving on.
These users tend to be driven by curiosity, or are aiming to carefully develop a new skill.

Crucially, these paths are independent of the experience levels of the learner!
Bevy intentionally aims to be inclusive of both complete beginners who have never programmed before, and professionals coming from other engines.

|                      | **Beginner**                                                       | **Professional**                                                     |
| -------------------- | ------------------------------------------------------------------ | -------------------------------------------------------------------- |
| **Example-first**    | Enthusiastic, wants to create a new version of the game they love. | Exploratory, wants to dive in and see how Bevy holds up in practice. |
| **Definition-first** | Curious, wants to understand how making games works.               | Critical, wants to understand Bevy's unique design choices.          |

Each of these requires their own complementary learning paths that branch as soon as they get to the [Learn page](https://bevyengine.org/learn/) to ensure that the first experience that they have with Bevy matches what they need.

Once users have completed the introductory learning materials in their path of choice, they can begin creating their own games or move on to our advanced examples to see how everything comes together in a realistic way.

### Bevy Quick Start: the example-first path

Users following the example-first path will tend to take the following route:

1. Encounter the Bevy homepage due to social media or word of mouth.
2. Navigate to the Learn page.
3. Choose one of the most relevant **quick start games**.
4. Complete that tutorial.
5. Dive into making the game they have in mind, accessing the following resources as needed when they encounter road-blocks:
   1. Official Examples.
   2. The Bevy book.
   3. Community tutorials and template games.
   4. Various community support forums.
   5. Streams, YouTube channels and blogs.
   6. Advanced examples.

Each quick start game should:

1. Assume zero existing knowledge of Bevy.
2. Begin with a initial high-level explanation of what we're trying to build.
3. Introduce commented code first, then explain what each of the critical terms means as they come up.
4. Be broken into compilable, playable sections: one per page of the guide.
5. Gradually refactor the code to add more functionality.
6. End with a list of suggestions (with appropriate links) on how you could extend the game in interesting ways.

This path should prioritize:

1. Rapid time-to-fun.
2. Functional, good-enough explanations that are tied to the code in front of them.
3. Relevance of quick-start game to the genre of game they want to make.
4. High asset quality.
5. Ease of extending the quick-start game with their own tweaks.
6. Explaining how to get unstuck, through documentation, community help and filing issues.

### The Bevy Book: the definition-first path

Users following the definition-first path will tend to take the following route:

1. Encounter the Bevy homepage due to social media or word of mouth.
2. Navigate to the Learn page.
3. Select the **Bevy book**.
4. Read through the book, largely in order.
5. Once they feel they have a good enough understanding of the engine, they will begin to make their own games, typically by jumping over onto the example-first path.
6. As they explore, they will also browse:
   1. The source code.
   2. [docs.rs](https://docs.rs/bevy/)
   3. CONTRIBUTING.md, GitHub issues and pull requests.
   4. Release notes.
   5. The engine development channels on Discord.
   6. Advanced examples to see how everything comes together.

Each chapter of the Bevy Book should:

1. Have a clear topic, and give a high-level overview of the subtopics it is going to cover and how they fit together.
2. Be broken down into several sections / pages to focus on detailed topics.
   1. These should have simple, minimal examples explaining how that functionality works.
3. Link to appropriate sections of quick start guides that demonstrate the ideas being taught in a more coherent way.

This path should prioritize:

1. Clear, thorough explanations.
2. Carefully introducing one concept at a time in an organized fashion.
3. Connecting concepts to each other in context.
4. Explaining the technical details of how things work, but only in clearly marked asides.
5. Communicating all of the supporting development practices that make Bevy productive:
   1. How to set up your dev environment.
   2. Code organization.
   3. Design patterns and best practices.
   4. Testing, benchmarking and debugging.
   5. Contributing to Bevy itself.
6. Linking to further reading: official examples, `docs.rs` and (very sparingly) source code links.

### Contributor's style guide

When writing and reviewing learning material for the Bevy Book and Quick Start Games, please try to follow these guidelines:

#### Writing

1. Use clear, simple language.
2. Prefer short sentences. Remove extra words.
3. **Bold** new vocabulary words where they are defined.
   1. Define them as soon as is reasonable after they are introduced.
4. Make sure your grammar and spelling are correct.
5. Avoid idioms and slang.
6. Speak directly to the reader in an approachable tone. Use "we" and "you" pronouns.
7. It can be useful to create specific, named characters to demonstrate a point.
   1. If you do, pick a pronoun set for them and stick to it.
   2. Otherwise, use  "they/them" third-person pronouns to refer to the reader or others.
8. Keep humor light.
   1. Avoid off-color or offensive humor.
   2. Be mindful not to overuse in-jokes or cultural references.
   3. Don't drag your jokes out: that's not what the audience is here to read.

#### Organizational

1. Carefully organize your work into separate pages, headings, paragraphs and code blocks.
2. Clearly signal when you are explaining a concept in technical depth so it can be skipped.
3. Use lists, numbered lists and sub-lists to present information in bite-sized ways.
   1. Refer back to these items by number!
4. Provide plenty of links, but be sure that what you are linking to is obvious by context.
   1. Link to other sections of the book / example / web page when you mention them.
   2. Always link to the most specific location you can, whether that's a section on a page or a method on a struct.
   3. Use the `latest` tag when linking to Bevy docs and source code so it won't go stale every time the version is updated.
   4. When linking to detailed explanations or discussions, summarize the most important points in addition to providing a link.

#### Technical

1. All examples must be able to be compiled and run.
2. Prefer game-relevant, descriptive examples and variable names over generic ones like `MyEvent`. Avoid meaningless names like `foo` at all times.
3. It's good practice to break your code into blocks with comments or explanatory text, but you need to link to a cohesive, copy-able whole at the end.
4. Examples must pass Bevy's standard `clippy` lints.
5. The polish level of your examples should correspond to the point you're trying to make.
   1. If you're demonstrating a new feature, show only the most basic syntax as locally as possible.
   2. When trying to explain how a game can be made, organize and polish your code to showcase best practices.
   3. Lack of polish should serve an end: don't show bad or sloppy practices without a good reason.
   4. Showing how (and why!) to refactor your code is a very powerful teaching tool.
6. Stick to a consistent style (e.g. for loops vs map) within each example.
7. If you need to give advice that will only matter to some of your audience (e.g. how to handle an edge case, or support a specific platform), do so in a clearly marked aside or list.
8. Examples should not use or rely on third-party plugins.
These may be appropriate to link in "next steps" however at the end of the examples.
   1. Third-party crates should be limited to the most essential, such as `rand`.

## Implementation strategy

1. The user-facing explanation above should live in `CONTRIBUTING.md` of the [`bevy-website` repo](https://github.com/bevyengine/bevy-website).
2. This should be linked to from the website, likely under a "Contributing" tab.
3. Per [bevy-website #143](https://github.com/bevyengine/bevy-website/issues/143),the website will need to be revamped somewhat.
4. Automatic compilation of code snippets is the critical feature from the above, ensuring that we can keep the examples current in a reliable way.
5. Once this RFC is merged, work should begin on a separate branch of `bevy-website` repo to create a new book.
6. For the launch of 0.6 (or perhaps sooner), this branch is merged and becomes the new `main`.
7. A persistent `bevy-main` branch of the repo is maintained and with a dependency on the `main` branch of `bevy` to ensure that we can test out new changes and refine the code before new features and breaking changes go live and reduce release crunch.

### Quick Start examples

### Breakout

**Genres:** arcade
**Focus:** basic physics, keyboard controls, sprites

Control a paddle with your keyboard to smash bricks and score points in this classic arcade game!

### Falling Sand

**Genres:** simulation, RTS, factory-builder
**Focus:** advanced ECS patterns, pixel graphics, handling mouse input

Simulate the interactions between different materials as you build your own creation.

### 3D Puzzle Game

**Genres:** puzzle, 3rd person platformer
**Focus:** camera controls, rule checking, level creation, 3D graphics

Create devious puzzles for your players to solve as they navigate a 3D world.

### Bevy Book chapters

Sections within each chapter increase in difficulty and obscurity; this book is not particularly intended to be read from cover-to-cover.

1. Getting Started
   1. Why Bevy?
   2. Installing Rust and Bevy
   3. `App`, `AppBuilder` and `World`
   4. Plugins as modular building blocks
   5. The Bevy community
2. Entities, Components and Systems
   1. Entities have components
   2. Systems access data through queries
   3. Resources are global singletons
   4. Spawning, despawning and modifying entities with `Commands`
   5. Filtering queries
   6. Reliable change detection
   7. Generic systems
   8. Exclusive `World` access
3. Game logic
   1. Stages and system ordering
   2. Events
   3. States
   4. Time and timers
   5. Run criteria and fixed timesteps
   6. Async tasks
   7. Custom runners and headless operation
4. Graphics
   1. The `Transform` component controls position
   2. Cameras
   3. `Parent`-`Child` hierarchy
   4. Configuring window(s)
   5. 2D
      1. Sprites
      2. Sprite sheets
   6. 3D
      1. Meshes
      2. Physically-based rendering
   7. Rendering internals
      1. Shader basics
5. Assets
   1. Loading assets
   2. Working with handles
   3. Custom asset types
   4. Hot reloading
   5. Scenes and reflection
6. Input
   1. Input basics
   2. Keyboard input
   3. Mouse and touchpad input
   4. Gamepad input
7. Audio
   1. Audio basics
8. User interfaces
   1. User interface basics
9. Development practices
   1. Rust module refresh
   2. Plugins
   3. Fast compiles
   4. Testing
   5. Error handling
   6. Boilerplate reduction tools
10. Performance optimizations
    1. Diagnostics and benchmarking
    2. Parallel iteration
    3. Custom "indexing" patterns
    4. Component storage types
11. Platforms
    1. Android
    2. iOS
    3. Web

### Advanced examples

### Text adventure

**Genres:** rpg, rogue-like, adventure
**Focus:** custom runners, terminal integration

Explore a dungeon from the command line in this old school roleplaying game.

### Sudoku

**Genres:** puzzle
**Focus:** ui, polish

Play Sudoku in this polished, all-UI game.

## Drawbacks

1. Delegating much of this work to the community risks creating an inconsistent editorial voice for the book.
2. Documentation created here *absolutely* must remain correct and current or we will lose new users.
3. Synchronizing the examples against main while in a separate repo is somewhat frustrating.

## Rationale and alternatives

### Why can't this live in community-provided documentation?

Community documentation is hugely important, but it:

- isn't as visible
- isn't as approachable
- community content varies significantly in quality and freshness
- scattered resources are poorly equipped to provide high-level explanations of how all of the pieces of Bevy fit together
- relying on community content as the only solution creates an untenable maintenance burden on critical ecosystem members and restricts their creative control

### Why can't we just write more examples?

Examples are great!
They're quick to reference, easy to keep up to date, and can be extensively commented.
However, they struggle with two main issues:

1. They lack the context required to make them truly useful to beginners. The order they should be read in, how features relate to each other and so on.
2. Making examples more useful to beginners makes them less useful to intermediate and advanced users as their verbosity increases.

The [Diátaxis Framework](https://diataxis.fr/) model of documentation makes it clear that examples belong in the `How-To-Guides` quadrant.
Beginners need `Tutorials` (the Quick Start) and `Explanations` (the Bevy Book) to complement our `Reference` material found on [docs.rs](https://docs.rs/bevy/).

### Why do we need two paths?

This distinction is not new, but is quite striking within Bevy's community (see [this user report](https://github.com/bevyengine/bevy/issues/2109)).

The types of explanation that one group prefers serve only to frustrate the other group: we can't effectively tackle both use cases at once without painful sacrifices.
Instead, by clearly sign-posting two equally-valid paths to get started, we can trust users to filter into the path that works for them, and consult the other path's learning material when it's particularly relevant.

### Why do we need more than one example game in the Bevy Quick Start?

As discussed above, example-first users often want to jump straight into making their game.
This is great, but Bevy can cover a huge number of use cases, each of which demand very different strategies.

A user trying to adapt a chess tutorial to a first-person shooter will be just as frustrated as one trying to turn an arcade game into a scientific simulation or card game.

We *cannot* tell these users to "just read the docs" and build up their game from first-principles: this isn't how they want to learn, and they generally won't have strong enough conceptual models to do so effectively!
The closer the first example they explore is to the genre they have in mind, the better their experience will be (as long as we are careful to avoid overwhelming them with similar options).

### Why don't we include an FPS or platformer in our Quick Start games?

These are popular and well-known genres, and would make a great addition to our guides!

Unfortunately, Bevy isn't very *good* at making them yet.
Both require a physics engine, and we don't have a native physics engine yet.
First person games in general *also* want nice mouse picking functionality, which is not yet integrated.

Linking to third-party plugins risks the entire example breaking if the plugin is not maintained and shapes the ecosystem in somewhat uncomfortable ways.
For now, these are better suited to community tutorials.

### Why don't we include a turn-based game in our Quick Start games?

A ~~JRPG~~ sparkling turn-based battler would be a great fit, as would a classic board game.
They're popular, simple, and not entirely obvious how to do in a real-time-focused ECS engine.

Unfortunately, this style of game tends to be very UI-heavy, and our design patterns for writing good turn-based games are not very mature.
More fodder for the future!

### Why doesn't the Bevy Book have more chapters?

There are two main reasons for this:

1. Scope: we want to keep the scope *reasonably* small to have a polished, useful product in time for 0.6.
2. Stability: many useful features (such as rendering, audio or UI) are not sufficiently stable or mature to document in this way.

We can (and should!) add more chapters later and extend the chapters we do have.
