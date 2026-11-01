# AppKiln Delivery Workflow

AppKiln turns a product idea into a repository and a verified mobile artifact.

## Request intake

The AI extracts the product purpose, target user, primary job, core entities, platform, technology, artifact, visual expectations, and delivery requirements. It asks only for information that cannot be inferred safely from the request.

## Platform selection

| Request | Technology | Runner | Artifact |
|---|---|---|---|
| Flutter Android | Flutter | Ubuntu | APK |
| Flutter iOS | Flutter | macOS | IPA |
| Swift native iOS | Swift / SwiftUI | macOS | IPA |
| Both Android and iOS | Flutter or compatible platform setup | Ubuntu + macOS | APK + IPA |

## Build sequence

1. Read the five design modules.
2. Create `DESIGN_DIRECTION.md`.
3. Implement the app from the shared contract.
4. Run formatting, analysis, unit tests, UI tests, and platform checks.
5. Add the appropriate GitHub Actions workflow.
6. Build the requested APK or IPA.
7. Upload the artifact with `actions/upload-artifact@v4`.
8. Generate a SHA-256 checksum and upload it with the artifact.
9. Verify the remote commit, workflow result, artifact type, file size, and checksum.

## Delivery report

The final response includes:

- Product name and selected technology.
- Implemented capabilities and visual direction.
- GitHub repository URL and published commit.
- Successful GitHub Actions workflow URL.
- APK or IPA artifact URL.
- Artifact size and SHA-256 checksum.
- Installation instructions.
- Remaining implementation notes and practical next steps.
