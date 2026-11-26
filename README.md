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
| [Erdős #389](https://www.erdosproblems.com/389) (open problem; statement in [formal-conjectures](https://github.com/google-deepmind/formal-conjectures)) | Lean 4 proofs, written by an LLM in a propose–check loop, that the tabulated least k is minimal; the loop measured first on 19 already-proved theorems; then existence for n ≤ 35 | `IsLeast` proved for n = 1–3 and 5–12, up to k = 3,648,830 (p-adic certificate from n = 10); a witness k for every n ≤ 35 (k up to 2·10^16; minimality not claimed), kernel-checked without `native_decide`, via a general "governor" criterion proved in Lean; all replayed by `leanchecker`; eval 18/19 | [erdos-389-research](https://github.com/pedroteixeira/erdos-389-research) · issue [#8334](https://github.com/google-deepmind/formal-conjectures/issues/8334) · PR [#8335](https://github.com/google-deepmind/formal-conjectures/pull/8335) |

## AI use

Claude (Anthropic) does most of the modelling, harness writing and drafting. Every result is
checked by a machine (Lean, a reproduction script, the project's own tests) and by hand
before it is reported upstream. Reports to maintainers say so.
