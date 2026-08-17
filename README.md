# goodmagma bucket

A [Scoop](https://scoop.sh) bucket for software published by goodmagma.

```powershell
scoop bucket add goodmagma https://github.com/goodmagma/scoop-bucket
```

```powershell
scoop install goodmagma/hostpad
```

## What is in it

| Package | What it is |
| --- | --- |
| [hostpad](https://github.com/goodmagma/Hostpad) | A connection manager for Windows: every remote machine in one place, opened with a double click through PuTTY, WinSCP, mstsc or your VNC viewer. |

## About the packages

Hostpad's builds are not code-signed, so Windows may warn the first time you run
one. The manifest pins the SHA-256 of the file it installs, and Scoop refuses
anything that does not match — which is the check the warning is asking you to
make.

The self-contained build is the one packaged here. It is the largest download
and the only one that cannot fail to start: it carries the .NET runtime inside
it, so nothing has to be installed first.

Nothing here needs to be preserved across upgrades. Hostpad keeps its vault and
its settings in `%USERPROFILE%\.hostpad`, outside the directory Scoop owns, so
uninstalling or updating never touches your connections.

## How it stays current

The [Excavator workflow](.github/workflows/excavator.yml) runs daily: it reads
the `checkver` block in each manifest, notices a new upstream release, downloads
the new file, computes its hash and commits the result. Manifests here are not
normally edited by hand.

## Licence

The manifests in this repository are MIT (see [LICENSE](LICENSE)). The software
they install keeps its own licence — Hostpad is GPLv3 or later.
