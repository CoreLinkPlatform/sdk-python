# CoreLink Python SDK

Generated prerelease client for the CoreLink Public API. It is not published or
production-supported until its contract and runtime PRs are merged and sandbox
compatibility tests pass.

## Contract provenance

- Contract: `corelink-public-v1.yaml`, version `1.0.0-draft`
- Source branch: `agent/p3-1-contracts`
- Source commit: `701e693`
- Generator: OpenAPI Generator `7.12.0`, `python`

The SDK exposes canonical CoreLink identifiers only. Connector selection and
integration-provider identifiers remain server-side concerns.

## Local verification

```sh
python -m compileall corelink_sdk
```

See [CODEGEN.md](CODEGEN.md) for deterministic regeneration. Generated files
under `corelink_sdk/` are not hand-maintained.

## Release gate

Publish only after a merged, tagged contract, sandbox compatibility tests,
clean generated diff, package build, and release notes that record the exact
contract commit.
