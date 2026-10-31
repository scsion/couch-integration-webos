# Fork notes (scsion)

This is a personal fork of
[Couch-OS/couch-integration-webos](https://github.com/Couch-OS/couch-integration-webos).

## What is different

- Optional connection setting **"Home button opens app"**. Set it to a webOS app
  ID (for example `io.github.chiotas.lightkeeper`) and Couch's Home button
  launches that app instead of pressing the TV's own Home key. Leave it empty
  for the original behaviour.
- `.github/workflows/publish.yml` builds, tests, signs and publishes the package
  to `https://scsion.github.io/couch-integration-webos` (Couch custom repository).

## Versions

Fork versions are the upstream version plus `_pN`, for example `0.1.0_pre5_p1`.
Every change to the package needs a new version, or the remote rejects it.
A newer upstream release (for example `0.1.0_pre6`) sorts above the fork's.

## Pulling in upstream changes

```sh
git remote add upstream https://github.com/Couch-OS/couch-integration-webos.git
git fetch upstream
git merge upstream/main
# resolve conflicts, set plugin.json "version" to <upstream version>_p1, push
```

## Going back to the official package

Clear the "Home button opens app" field on the LG connection first. The official
package does not know that setting, and Couch rejects unknown settings.
