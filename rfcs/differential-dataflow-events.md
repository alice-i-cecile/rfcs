# Feature Name: `differential-dataflow-schedule`

## Summary

Differential dataflows is an extremely efficient tool for computing data.
We can leverage a nested loop scheduler, reliable change detection and multiple worlds to access it in Bevy.

## Motivation

RunCriteria are very frustrating.

## User-facing explanation

Two parts:

1. Update computations.
2. Pipe input to dependencies.

Incremental updating algorithms are dramatically more powerful because we have reliable change detection: can detect changes for multiple runs of the system in the same loop.

**Operators** correspond to systems, **collections** correspond to components (and resources?).
Operators react to deltas, producing even more deltas.

Tools for automatically transforming operators into differential operators may be useful?

### Time stamps

Multidimensional: (Tick, Iteration of system loop^n) where n is the degree of loop nesting

Caches all previous state as **versions** across all dimensions. Use parallel worlds for this. These versions have a partial order, defined by dimensional time stamp coordinates.

Set of all versions is a **collection trace**. Operators applied to traces create new traces.

Reuse work done (access previous value computed) in both previous tick and previous loop pass.

### Extended change detection

Store arbitrary difference operators in traces, not just binary Changed.

### Dependency tracking

### Control flow

Proposal: Schedule contains tree of nested loops: series-parallel graph (tree width 2). This is way way better than YesAndLoop.

## Implementation strategy

1. Multiple worlds.
2. Nested loop scheduler.
3. Extended difference creation.
4. Take advantage of alignment of traces across worlds?

## Drawbacks

Increased data costs: requires automatic opt-in change detection.

## Rationale and alternatives

## \[Optional\] Prior art

**Differential dataflow** ([link](https://timelydataflow.github.io/differential-dataflow/) / [paper](https://github.com/timelydataflow/differential-dataflow/blob/master/differentialdataflow.pdf)) generalizes both incremental and prioritized dataflows.

## Unresolved questions

- ???

## Future work

Complex graph algorithm applications:

1. Checking groups-at-rest in statics problems in physics.
2. UI / event resolution.
