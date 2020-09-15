# linux

Linux: Most useful commands for Full Stack developers

## 1. Remove `PPA`

When you are updating Ubuntu, sometimes appear errors like this:

```bash
E: The repository 'http://ppa.launchpad.net/armagetronad-dev/ppa/ubuntu bionic Release' does not have a Release file.
```

You can solve with this:

```bash
sudo apt-add-repository -r ppa:armagetronad-dev/ppa
sudo apt update
```
