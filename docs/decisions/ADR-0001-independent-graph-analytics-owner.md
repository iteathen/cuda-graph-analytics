# ADR-0001: Independent Graph-Analytics Semantic Owner

**Status:** Accepted
**Date:** 2026-09-02

## Context

Graph analytics includes graph representation, traversal, centrality, components, community, link analysis, similarity and related algorithms. CUDA-MCGS also uses graph structures, but its semantic purpose is decision/search progression with selection, expansion, evaluation and backup. Sharing graph vocabulary does not justify making either library the other's core.

## Decision

`cuda-graph-analytics` owns reusable graph-analysis semantics. CUDA-MCGS remains the independent search/MCGS owner. CUDA-JS, Tensor, Data, RNG and COMM retain their natural lower/sibling semantics.

## Deletion test

Deleting CUDA-MCGS leaves graph analytics coherent. Deleting graph analytics leaves CUDA-MCGS coherent. A contract that requires search-stage/evaluator/backup meaning does not belong here; an analytics algorithm does not become MCGS because it traverses a graph.

## Implementation gate

Issue #3 selects a bounded graph representation plus first algorithm profile and independent references before source/API implementation. Vendor APIs do not define the semantic contract.

## Consequences

Graph analytics can grow independently without polluting search semantics, while explicit adapters remain possible later through public contracts.