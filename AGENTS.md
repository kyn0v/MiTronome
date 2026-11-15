# Workflow

After successfully building and verifying a new application package, provide the owner with a download link to the build artifact containing the verified `.rpk` file. The owner develops remotely through a relay and installs manually from the phone. Do not copy packages to iCloud or reveal them in Finder. Do not automatically AirDrop, install packages on the band, or flash device firmware.

# Release packaging

Follow the review requirements from AstroBox-Repo PR #1925:
- Deliver production packages built directly with `aiot release` using the existing project signing identity, never debug-signed packages.
- Set versionName and versionCode in source before building. Increment them for a new store update and keep package metadata consistent. Never use ABCC's versionCode modifier or otherwise modify the built RPK; rebuild and re-sign instead.
- Verify the artifact hash and signing certificate identity before delivery, and deliver the exact verified build output.
- This free application has one complete package, not a separate trial package.
- Keep the store resource name consistent with the packaged application name, currently `手环节拍器`.
- Do not claim device support based only on builds, automated tests, or browser previews. Redmi Watch 6 compatibility remains pending real-device acceptance until verified.

# Screenshots and remote delivery

After completing UI changes, capture and inspect screenshots of the affected screens and return them inline in the conversation using the client's supported image attachment or rendering mechanism, so the owner can view them directly while connected remotely through a relay. Do not provide only local file paths, Finder reveals, or download links in place of inline screenshots. If inline delivery is unavailable, state that limitation explicitly and provide an accessible artifact download link as a fallback; do not claim the images are visible in chat. Keep browser-preview screenshots visibly labelled `Browser simulation / 非真机截图`; never present them as device screenshots.

# Repository branches

The remote repository is `kyn0v/AstroBox-Xiaomi-Band-Metronome`. Develop on `source`; `main` contains CreatorConsole-managed release resources. Do not merge these independent histories. Keep the manual build workflow identical on both branches; dispatch it on `source` only. Never delete the AstroBox fork or a branch used by an open store PR.

# Publication privacy

Use the repository-local project identity for Git commits; do not fall back to a personal global Git identity. Keep private history backups and legacy packages outside this repository and the public delivery directory. Never publish local user-directory paths, personal contact details, signing private keys, or access tokens. Scan both tracked files and commit metadata before pushing. The current package ID is `org.bandmetronome.app`.
