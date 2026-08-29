# Python SDK generation

This client is generated from `openapi/corelink-public-v1.yaml` with OpenAPI Generator `7.12.0`.

Authoritative immutable input:

- repository: `CoreLinkPlatform/api-contracts`
- tag: `v1.0.0-draft`
- commit: `5bdc07b80c8acbd0617b75e2d7ae3edd17f6324b`
- contract blob: `11cd7034f2b6dc736e23a4cf36242a34f0d637e5`

The original development revision used for generation resolves to the same contract blob as the immutable tag above. Supported regeneration must always use the immutable tag/commit recorded in `.corelink-contract.json`.

```sh
java -jar openapi-generator-cli-7.12.0.jar generate \
  -i /path/to/corelink-public-v1.yaml \
  -g python \
  -o . \
  --additional-properties=packageName=corelink_sdk,projectName=corelink-sdk,packageVersion=0.1.0.dev0 \
  --global-property=apiDocs=false,modelDocs=false
```

CI regenerates the client from the pinned contract and compares generated `corelink_sdk/` output before compiling the checked-in package. Do not hand-edit generated files.

When a newer public contract slice is accepted, update the pinned tag/commit/blob in one reviewed change, regenerate, review the diff, then run `python -m compileall corelink_sdk`.
