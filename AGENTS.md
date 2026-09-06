# CUDA-GRAPH-ANALYTICS Agent Entry Point

Read before changing the repository. Authority: owner instruction -> this file -> accepted ADRs -> accepted specs -> charter -> status/roadmap/issues.

Use `assess -> research -> reassess -> plan -> execute -> qualify -> review -> cleanup/document` and `LEGO -> SOLID -> CUPID -> KISS`.

LEGO is the outer architecture rule: ownership, universality, replaceability, scope containment, damage-limiting encapsulation, supported connection surfaces, and context containment. **The application/system is the outermost LEGO.** Its supported external inputs, outputs, commands, events, data contracts, and lifecycle entry/exit points are its public **studs/surfaces**. Large sections, subsystems, components, and large objects should preferentially compose smaller child LEGOs when that preserves cohesion; the parent owns the external responsibility and hides child topology.

A LEGO is too large when one agent cannot hold its complete authoritative working set—contract/studs/surfaces, implementation, invariants, lifecycle/resource/failure rules, tests/conformance, and immediate dependency/consumer interfaces—in focused attention with substantial headroom for reasoning and review. Context fit is a first-class boundary criterion alongside semantic, lifecycle, resource/failure, substitution, and change cohesion. When exceeded, recursively split at the strongest real seam or narrow scope; do not create arbitrary modules that duplicate truth or require cross-boundary internal knowledge. Callers connect through deliberate studs/surfaces and never drill through a parent to a private child. Inside a valid LEGO, SOLID structures responsibilities and dependency direction, CUPID shapes the implementation, and KISS removes remaining unjustified complexity; lower levels may not defeat higher ones.

CUDA-GRAPH-ANALYTICS owns reusable graph representation and graph-analysis semantics when separately accepted: directed/undirected graphs and multigraphs, vertex/edge/property/weight meaning, construction/normalization/renumbering/subgraphs, traversal/paths, centrality/components/cores/community/similarity/link-analysis/spanning-tree algorithms, graph sampling/walk semantics, and graph-specific conformance.

CUDA-GRAPH-ANALYTICS does not own CUDA-MCGS Search IR, selection/reservation/expansion/evaluation/backup/stopping/progress/session/stage/channel/search-resource semantics. Shared words such as graph/node/edge are not shared ownership.

CUDA-JS owns generic GPU mechanisms; CUDA-JS-Tensor owns generic Tensor math; `cuda-rng` may own reusable random generation; `cuda-comm` may own reusable multi-GPU communication; `cuda-data` may own reusable columnar/property-table semantics. These are optional dependencies, not hidden subcomponents.

No cuGraph/RAPIDS provider is selected by repository creation. Direct native/FFI/CUDA C++/PTX/private imports or duplicated lower lifecycle are ownership-gap signals. Maintained code, when authorized, is JavaScript/ESM plus accepted restricted Device-JS; no Python/native escape path without a successor decision.

Repository creation authorizes no production API/source. #3 is the graph semantic roadmap; #2 owns repository controls. Accepted bounded specs are required before implementation.