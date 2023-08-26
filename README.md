# solidity-fixtures
Zero-Knowledge files required for generating proofs against circom.

This repository uses DVC to manage large fixtures files and uploads to a public AWS S3 bucket. This allows anyone to fetch the fixtures, while minimizing impact on git size.

### Fetching fixtures from remote storage

`dvc pull`

### Pushing new fixtures to remote storage

After generating new fixtures (likely from `protocol-solidity`), you should run the following steps:

```
dvc add solidity-fixtures
git add -A
git commit
dvc push --remote s3-read-write # This should be done after a PR merge by the creator of the fixtures
```
