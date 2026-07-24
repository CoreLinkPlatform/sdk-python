# Python SDK generation

This client is generated from `corelink-public-v1.yaml` with OpenAPI Generator
`7.12.0`. The authoritative input for this prerelease was contract commit
`2fb0dc8` on `agent/p3-1-contracts`.

```sh
java -jar openapi-generator-cli-7.12.0.jar generate \
  -i /path/to/corelink-public-v1.yaml \
  -g python \
  -o . \
  --additional-properties=packageName=corelink_sdk,projectName=corelink-sdk,packageVersion=0.1.0.dev0 \
  --global-property=apiDocs=false,modelDocs=false
```

Regenerate in a clean worktree, restore this README and package metadata, then
run `python -m compileall corelink_sdk`. A release may only use a merged,
tagged contract commit.
