# debian-pxe-installer

Original netboot: http://deb.debian.org/debian/dists/bookworm/main/installer-amd64/current/images/netboot/netboot.tar.gz

Based on Debian 12.12 release (bookworm).

Use at your own risk.

## Set root password

```shell
ROOTPWD=$(mkpasswd -m sha-512 -S saltsalt -s <<< root)
sed -i.bak -e "/root-password-crypted/ s/XXX/$ROOTPWD/" debian-preseed/bookworm.cfg
```
