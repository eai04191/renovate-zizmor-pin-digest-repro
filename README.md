# Renovate reproduction: Zizmor `version` input and `pinDigests`

## Current behavior

When `docker:pinDigests` is enabled, Renovate extracts the `version` input of `zizmorcore/zizmor-action` as the Docker dependency `ghcr.io/zizmorcore/zizmor` and creates a `pinDigest` update. Renovate cannot write the digest back to the `version` input, so branch creation fails with `Digest is not updated` and `foundValue: undefined`.

## Expected behavior

Renovate should continue to manage version updates for the `version` input, but it should not create a Docker `pinDigest` update for this `uses-with` dependency because the input accepts a version, not an image reference.

## Reproduction

Run Renovate with debug logging against this repository. The problem was originally observed with Renovate `43.275.0`.

## Discussion

Add the Renovate Discussion URL here after creating the report.
