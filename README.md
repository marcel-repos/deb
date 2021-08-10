# Marcel's Debian Repository

## Setup

First you need to install some requirements:
```bash
sudo apt-get update

sudo apt-get install \
  apt-transport-https \
  ca-certificates \
  wget
```

After that you need to import the public GPG key:
```bash
wget -qO - https://m4rc3l.de/static/deb-repo.pem | sudo apt-key add -
```

Now verify the GPG public key fingerprint.
<br>
The fingerprint should be `B0B1 DC86 8FF8 2295 E5D5  D338 3D7B FEF0 C780 7326`.
```bash
apt-key list
```

After that is finished you need to add the package list:
```bash
sudo apt-add-repository "deb http://deb.m4rc3l.de all main"
```

## Packages

| Package | Description | Reposetory |
|---------|-------------|------------|
| `genpw` | Generate strong passwords directly from the command line. | [MarcelCoding/debian-genpw](https://github.com/MarcelCoding/debian-genpw) |