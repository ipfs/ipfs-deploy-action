# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## Unreleased

## [1.0.0] - 2025-02-19

### Added

- Add timeout and retry logic to IPFS Cluster uploads.
  - Uploads to IPFS Cluster have a default timeout of 5 minutes.
  - If the upload fails, the action will retry by default 3 times with a 5 second delay between attempts.
  - The number of retry attempts and timeout can be customized using the `cluster-retry-attempts` and `cluster-timeout-minutes` inputs.

### Fixed

- Remove duplicate preview link from PR comment.

## [0.3.1] - 2025-02-10

### Fixed

- Log info to stdout instead of GitHub workflow summary

## [0.3.0] - 2025-02-10

### Added

- Add support for CAR uploads to Kubo via the Kubo RPC API.

### Removed

- Removed `cluster-upload-timeout` input as GitHub Actions does not support setting [timeout-minutes](https://github.com/actions/runner/blob/main/docs/adrs/0549-composite-run-steps.md#composite-run-steps-features) for steps in composite actions.

## [0.2.2] - 2025-02-10

### Fixed

- Default for `cluster-upload-timeout` input is a number instead of a string.

## [0.2.1] - 2025-02-04

### Fixed

- Make sure that storacha inputs are not required by action to allow for IPFS Cluster only deployments (inputs will be validated at the beginning of the action ensuring that either Storacha or IPFS Cluster inputs are provided).

## [0.2.0] - 2025-02-04

### Added

- Add support for IPFS Cluster CAR uploads.
- Add `cluster-upload-timeout` input to set the timeout for IPFS Cluster CAR uploads.

### Changed

- Storacha is now optional. You can now choose to upload the build CAR to IPFS Cluster instead.

### Fixed

- Fix action step summary output from Merkleizing into CAR step.

## [0.1.0] - 2025-01-31

### Added

- Initial release of of the ipfs-deploy-action
