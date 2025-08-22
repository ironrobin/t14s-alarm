Packages for the ThinkPad T14s

## Binary repository
To use pre-built packages, add this section to the end of your `/etc/pacman.conf`:

```conf
[ironrobin-t14s]
Server = https://github.com/ironrobin/t14s-alarm/releases/download/packages
```

You'll need to trust the public key in order to verify package signature:

```bash
sudo pacman-key --recv-keys 6ED02751500A833A
sudo pacman-key --lsign-key 6ED02751500A833A
```

if it still says "unknown trust" even after you lsign it, try this and then resign:
```bash
sudo rm -rf /etc/pacman.d/gnupg
sudo pacman-key --init
sudo pacman-key --populate archlinux
sudo pacman-key --populate archlinuxarm
```

## Note on `linux-t14s`
For now, you will need `efi=noruntime clk_ignore_unused pd_ignore_unused arm64.nopauth` as kernel parameters to boot into the kernel.
