# CUDA-GRAPH-ANALYTICS Project Charter

**Status:** Accepted architecture after bootstrap integration; production implementation not authorized.

## Purpose

Own reusable provider-neutral graph representation and graph-analysis semantics without turning CUDA-MCGS into a general graph library or conflating graph analytics with CUDA runtime/dataframe semantics.

## Owns, when separately accepted

- directed/undirected graph and multigraph semantics;
- vertex/edge/property/weight identity and graph construction/normalization/renumbering/subgraphs;
- BFS/SSSP and other traversal/path semantics;
- components, cores, spanning-tree, centrality, PageRank/link-analysis, community and similarity families;
- graph random-walk/sampling meaning while consuming reusable RNG where natural;
- finite graph plans/resource meaning and provider-neutral conformance.

## Does not own CUDA-MCGS search

CUDA-MCGS owns Search IR, search-state/action/transition identity, selection/reservation/expansion/evaluation/backup/stopping, progress/output/session/stage/channel, search-resource and reroot/attention semantics. A search graph is not a graph-analytics API merely because both contain nodes and edges.

Neither repository depends on the other as a hidden core. A future explicit adapter may translate between accepted public contracts without transferring ownership.

## Other boundaries

CUDA-JS owns generic GPU mechanisms. CUDA-JS-Tensor owns generic math. `cuda-data`, `cuda-rng` and `cuda-comm` may be optional semantic dependencies for property tables, random walks and multi-GPU algorithms. Their semantics remain independently owned.

No vendor graph library is selected by this architecture decision.

## Activation gate

Issue #3 must select a bounded graph representation plus a first algorithm family and prove the MCGS boundary before production source/API.

## Non-goals

Search engine, graph database, GNN framework, arbitrary cuGraph passthrough, or immediate multi-GPU breadth.