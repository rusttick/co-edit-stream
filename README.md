# co-edit-stream

An open-source, standards-based framework for building **live, collaborative, cryptographically-verifiable digital twins** of any design/manufacturing domain — not a product for any one industry, but the generic substrate a product would be built on.

# Goals

## Composable, federated data model

No single monolithic schema.

A thin, stable core vocabulary (part-of, connected-to, satisfies, verified-by, supersedes)
with everything domain-specific (electrical, mechanical, thermal, chemical, safety, ERP, etc.)
plugged in as independently-owned, independently-versioned submodels

informed by Industry 4.0's Asset Administration Shell (AAS) and related standards (ISA-95, AutomationML, eCl@ss, OSLC)

## Real-time, multi-party collaboration

Every party — internal team, vendor, contractor, regulator — can edit live, simultaneously, from a role-appropriate view over the same underlying data,
using CRDT-based convergence (no locks, no check-out/check-in).

## Git-like, cryptographically verifiable history

Every accepted state is content-addressed and immutable,
so any state is globally and cryptographically identifiable, lockable, and exportable/importable —
durable storage built on Merkle-DAG principles, favoring implementations with an open-source clustering implementation and a clear, documented CAP position.

## Continuous, not phase-gated, workflow

Change is proposed, reviewed, and merged like a pull request at any point in a lifecycle;
acceptance automatically cascades to invalidate exactly the downstream sign-offs/certifications that depended on what changed
replacing rigid waterfall gates with always-consistent agile collaboration,
with standards-compliance checks running continuously against the live graph rather than at fixed audit milestones.

## Backward-compatible

Legacy tool formats become adapters that canonicalize into the same representation everything else uses, so adoption is incremental
no hard cutover required for any one format or vendor.

This repository contains the framework and generic worked examples only — no industry-specific product.
See [`ferrulink`](../ferrulink) for the first real application built on it: collaborative design, build, and test of industrial electrical control panels.

# Research

- [`possible_agile_manufacturing.md`](possible_agile_manufacturing.md) — the generalized, composable graph architecture: depth (nested assemblies down to individual components), breadth (every engineering discipline), and party (every organization) axes, and the standards/open-source projects that already solve pieces of each.
- [`possible_data_architecture.md`](possible_data_architecture.md) — the concrete three-layer technical architecture (semantic layer, live CRDT collaboration layer, durable content-addressed history layer), with a reasoned comparison of candidate technologies (Automerge, Fluree, Dolt, TerminusDB, Neo4j, Irmin, BaSyx) against git-like cryptographic properties and CAP-clear open-source clustering.
