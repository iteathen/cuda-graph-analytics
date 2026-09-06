# SPEC-0001: Native Boundary and JavaScript/TypeScript Implementation

**Status:** Accepted architecture/ownership authority; production graph-analytics profiles remain separately gated.

**Version:** 1.0.0

**Owner:** CUDA-GRAPH-ANALYTICS

**Lower authority:** `iteathen/CUDA-JS` SPEC-0032

## Purpose

CUDA-GRAPH-ANALYTICS owns reusable graph representation and graph-analytics semantics. CUDA-JS is the sole native CUDA/provider integration owner.

CUDA Graph capture/replay is a CUDA-JS execution mechanism and is unrelated to ownership of graph-data/analytics semantics.

## Repository implementation rule

Maintained CUDA-GRAPH-ANALYTICS source is JavaScript/TypeScript. Restricted Device-JS generation is permitted only through public CUDA-JS contracts.

CUDA-GRAPH-ANALYTICS does not maintain C, C++, CUDA C++, PTX, direct native FFI, native addons, provider bindings, native handles/pointers, ABI structs or platform discovery code. Native evidence may be produced externally and recorded, but native oracle/provider source is not maintained here.

A missing native mechanism routes to CUDA-JS before any local workaround.

## CUDA-GRAPH-ANALYTICS owns

- graph representation, vertex/edge/property and traversal/analytics meaning;
- reusable graph-algorithm semantics and result equivalence;
- graph-specific material/liveness/resource planning;
- graph-specific provider/algorithm eligibility/fallback;
- JavaScript/TypeScript reference and conformance evidence.

## CUDA-JS owns

- device/context/memory/view/transfer mechanisms;
- compiler/artifact/module/function execution;
- atomics/synchronization/operations;
- prepared execution and CUDA Graph realization;
- native graph-library/provider mechanisms if later selected;
- native errors, compatibility and teardown.

CUDA-MCGS remains the separate owner of search/MCGS graph-search semantics.

## Memory-policy boundary

Graph-specific semantic liveness/reclamation remains here. Generic cross-domain physical memory placement, pooling, fragmentation, reuse, migration or spill policy requires its own JavaScript/TypeScript owner if independently justified and must consume public CUDA-JS.

## Activation gate preservation

This specification does not select a graph representation, algorithm, provider or production API.

## Non-goals

No native graph backend, no search semantics, no CUDA Graph ownership, no arbitrary provider passthrough, no generic memory manager, no production capability or support claim.
