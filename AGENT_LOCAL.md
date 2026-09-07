# Repository context: cuda-graph-analytics

Universal engineering and design guidance comes from the account-global `AGENTS.md`.

## Mission and ownership

CUDA-GRAPH-ANALYTICS owns reusable graph representation and graph-analysis semantics when accepted: graph/vertex/edge/property meaning, construction/normalization/subgraphs, traversal/paths, graph algorithms, sampling/walk semantics, and graph-specific conformance.

It does not own CUDA-MCGS search/evaluator/resource/session semantics. CUDA-JS owns generic GPU mechanisms; Tensor/RNG/communication/dataframe semantics remain with their natural sibling owners.

## Local routing

Accepted `docs/decisions/`, `docs/specs/`, repository status/roadmap, and current issues own local implementation/activation truth.

## Local constraints

Maintained code uses JavaScript/ESM plus accepted Device-JS through public lower contracts; no Python, direct native/provider escape path, or private lower imports.