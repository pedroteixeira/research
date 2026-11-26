# research

Experiments with AI agents and machine checks: Lean proofs and differential testing of
open-source code.

## What goes here

Only results anyone can check: a proof Lean accepts, a bug with a reproduction script, an
issue or PR upstream. Each one lives in its own `<target>-research` repo, with its own build
and a README that says what was tested, what held, what failed and how to rerun it.

## Results

| Target | What was checked | Result | Upstream |
|---|---|---|---|
| [Restate](https://github.com/restatedev/restate) (durable execution) | Lean 4 model of the service-protocol message header (`bv_decide`); end-to-end repro against released servers | Invoker panics and the partition processor crash-loops when a deployment sends a custom or unassigned message type (1.7.14, 1.8.1-hotfix.3); fix tested | [restate-research](https://github.com/pedroteixeira/restate-research) · issue [#6061](https://github.com/restatedev/restate/issues/6061) · PR [#6062](https://github.com/restatedev/restate/pull/6062) |

## AI use

Claude (Anthropic) does most of the modelling, harness writing and drafting. Every result is
checked by a machine (Lean, a reproduction script, the project's own tests) and by hand
before it is reported upstream. Reports to maintainers say so.
