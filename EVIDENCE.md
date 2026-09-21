# Evidence status

This repository follows the shared [iteathen evidence and validation policy](https://github.com/iteathen/.github/blob/main/EVIDENCE_POLICY.md).

## Current posture

CUDA-GRAPH-ANALYTICS is currently an architecture/planning repository. Its intended scope is documented, but there is no production implementation, installable package, public API, native-provider qualification, cuGraph-provider claim, or performance claim.

## Registered claims

| Claim | Evidence class | Status |
| --- | --- | --- |
| `CUDA-GRAPH-ANALYTICS-PLAN-001` — intended scope: reusable GPU graph analysis through public CUDA-JS contracts | **UNVALIDATED** | planning hypothesis / project boundary |

The claim record is machine-readable in [`evidence/claims.json`](evidence/claims.json).

## What current evidence establishes

The repository establishes the current project boundary, planning state, architecture decisions, and separation between graph-analysis semantics and CUDA-MCGS search semantics.

## What it does not establish

It does not establish production graph analytics, CUDA correctness, a selected native provider, API stability, performance, or external reproduction.

## Path to stronger evidence

When implementation is authorized, qualification should begin with deterministic semantic/reference cases and then add hardware-measured and reference-grounded evidence appropriate to each algorithm.

## Non-mutation rule

Evidence work may inspect, test, benchmark, and document CUDA-GRAPH-ANALYTICS. It must not change substantive operational behavior merely to make an evidence claim pass.
