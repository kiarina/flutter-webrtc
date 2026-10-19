# Downstream integration branch

`codex/spirits-external-media` combines the policy and external media proposals
for consumers while upstream review proceeds. Pin a commit SHA, not this moving
branch. These proposals are not officially merged.

Windows x64 automatically downloads the matched SDK prerelease:
https://github.com/kiarina/libwebrtc/releases/tag/external-media-sdk-windows-x64-20261020.1

`third_party/spirits_sdk.cmake` verifies the archive SHA256 and all 51 extracted
files (headers, import library, DLL, license notices and source manifests) on
configuration. Stock SDK files are stored separately and never substituted.
A mismatched cache fails closed. The SDK manifest records source inputs; source
build/packaging instructions live in the libwebrtc integration branch. macOS
uses the original upstream SwiftPM SDK with the custom-device API.

The generic upstream API proposal does not contain this downstream distribution
configuration. Update the SDK manifest and fork pin together, rerun physical
capture/RTP/AEC regression, then update consumers. Return to official releases
only when equivalent APIs, SDK policy and those regressions are available.
