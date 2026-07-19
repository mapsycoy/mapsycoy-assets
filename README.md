# mapsycoy-assets

Static media assets for `mapsycoy.github.io`.

## Directory structure

- `uploads/blog/` — media referenced by blog posts
- `uploads/works/` — media referenced by portfolio work entries
- `uploads/cv/` — profile, organization, and project media used by the CV
- `uploads/site/` — site-wide media such as the OG preview and home-page assets
- `uploads/misc/` — files with no confirmed content reference

Files must not be placed directly in `uploads/`.

## Commit-pinned URL policy

Content uses immutable jsDelivr URLs pinned to a Git commit, for example:

```text
https://cdn.jsdelivr.net/gh/mapsycoy/mapsycoy-assets@<COMMIT7>/uploads/<CATEGORY>/<FILE>
```

Moving or deleting a file in a later commit does not break URLs pinned to an older commit. Even so, whenever content URLs are updated after a move, every reference and every resulting URL must be checked before deployment.

## Manual upload

1. Add the new file to the appropriate category folder.
2. Commit and push the change.
3. Read the first seven characters of the resulting commit hash with `git rev-parse --short=7 HEAD`.
4. Build the URL using the format above and enter it in the site content.
5. Verify the URL returns HTTP 200 with the expected `Content-Type`.
