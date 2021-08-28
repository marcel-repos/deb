# Marcel's Debian Repository

## Setup

First you need to install some requirements:

```bash
sudo apt update

sudo apt install \
  apt-transport-https \
  ca-certificates \
  curl \
  gnupg
```

After that you need to import the public GPG key:

```bash
curl -fsSL https://m4rc3l.de/static/deb-repo.pem | sudo gpg --dearmor -o /usr/share/keyrings/m4rc3l-deb-keyring.gpg
```

Now verify the public GPG key fingerprint.
<br>
The fingerprint should be `B0B1 DC86 8FF8 2295 E5D5 D338 3D7B FEF0 C780 7326`.

```bash
gpg --no-default-keyring --keyring /usr/share/keyrings/m4rc3l-deb-keyring.gpg --list-key repo@m4rc3l.de
```

After that is finished you need to add the package list:

```bash
echo "deb [signed-by=/usr/share/keyrings/m4rc3l-deb-keyring.gpg] http://deb.m4rc3l.de/ all main" \
  | sudo tee /etc/apt/sources.list.d/m4rc3l.list > /dev/null

sudo apt update
```

## Packages

```bash
sudo apt install <package>
```

| Package                 | Description                                               | Reposetory                                                                                  |
| ----------------------- | --------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| `genpw`                 | Generate strong passwords directly from the command line. | [MarcelCoding/debian-genpw](https://github.com/MarcelCoding/debian-genpw)                   |
| `docker-network-viewer` | Liste docker networks and according subnet.               | [MarcelCoding/docker-network-viewer](https://github.com/MarcelCoding/docker-network-viewer) |

## License

[LICENSE](LICENSE)
