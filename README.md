# CoreLink Python SDK

[![Maturity: Prerelease Alpha](https://img.shields.io/badge/maturity-prerelease%20alpha-orange)](https://github.com/CoreLinkPlatform/.github/blob/main/REPOSITORY_MATURITY.md)
[![Generated conformance](https://github.com/CoreLinkPlatform/sdk-python/actions/workflows/generated-conformance.yml/badge.svg?branch=main)](https://github.com/CoreLinkPlatform/sdk-python/actions/workflows/generated-conformance.yml)
[![Package: 0.1.0.dev0](https://img.shields.io/badge/package-0.1.0.dev0-orange)](pyproject.toml)
[![Python >=3.9](https://img.shields.io/badge/python-%3E%3D3.9-blue)](https://www.python.org/)
[![Contract: 1.0.0-draft](https://img.shields.io/badge/contract-1.0.0--draft-blue)](https://github.com/CoreLinkPlatform/api-contracts)

> **Maturity: Prerelease Alpha**  
> Package metadata: `corelink-sdk` `0.1.0.dev0`  
> Python: `>=3.9`  
> Public contract: `corelink-public-v1.yaml` `1.0.0-draft`

Generated Python client for the CoreLink Public API. The package source exists, but CoreLink does not yet claim a production-supported PyPI/Stable release. Public license/support policy and sandbox/runtime conformance remain release gates.

## What is currently covered

The generated client follows the current reviewed public contract, whose primary public slice is Device + Command. Broader telemetry/location/partner/event behavior remains contract- and acceptance-gated.

## Build/verify from source

Create a Python 3.9+ environment and install the repository requirements/package using your normal isolated Python workflow. For a basic generated-source verification:

```bash
python -m compileall corelink_sdk
```

This is a prerelease source workflow, not a claim that a Stable public package is published.

## Authentication and tenant context

The current public API uses Bearer JWT authentication and explicit tenant-scoped paths. Obtain credentials through the approved CoreLink environment/onboarding boundary; do not invent a token endpoint from SDK internals.

Use least-privilege credentials, keep tenant context explicit, and avoid logging credentials or sensitive customer payloads.

## Devices and commands

Public device identity is `corelink_device_id`. Provider-specific IDs remain internal implementation details.

Command creation is asynchronous and idempotency-aware. Retrying the same logical command must preserve the original `Idempotency-Key`; an accepted POST does not prove that the physical device executed the command.

Because this package is generated/prerelease, exact generated class and method names may change. Use the generated source/type hints for the pinned revision instead of relying on undocumented wrapper APIs.

## Errors and retries

Follow the OpenAPI problem/error definitions. Validation/auth/authorization failures should not be blindly retried. Preserve correlation/request identifiers needed for diagnosis and reconcile uncertain writes before creating a second logical operation.

## Contract provenance

Generation provenance is recorded in `.corelink-contract.json` and [CODEGEN.md](CODEGEN.md). Existing prerelease metadata references a development source revision; supported releases must use immutable/tagged contract provenance.

## Regeneration

Generated files under `corelink_sdk/` are not hand-maintained. Change normative schemas in [`CoreLinkPlatform/api-contracts`](https://github.com/CoreLinkPlatform/api-contracts), regenerate deterministically, then review the generated diff.

## License and publication gate

Current package metadata declares `LicenseRef-Proprietary`. Public repository visibility is not an open-source license. The applicable organization license/support policy must be explicitly resolved before supported public package publication.

## Release gates

Before a supported package release:

- license/support policy is accepted;
- contract provenance is immutable/version-identifiable;
- generation/build is reproducible;
- auth/tenant/error/retry behavior matches the contract;
- conformance passes against an accepted mock/sandbox/runtime revision;
- release provenance/signing/documentation gates pass.

Backlog: [PY-01](https://github.com/CoreLinkPlatform/sdk-python/issues/4), [PY-02](https://github.com/CoreLinkPlatform/sdk-python/issues/2), [PY-03](https://github.com/CoreLinkPlatform/sdk-python/issues/3).

## Documentation

- [CoreLink developer docs](https://github.com/CoreLinkPlatform/developer-docs)
- [API contracts](https://github.com/CoreLinkPlatform/api-contracts)
- [Repository maturity](https://github.com/CoreLinkPlatform/.github/blob/main/REPOSITORY_MATURITY.md)
