# penguins-eggs-manjaro

This is a fork of [penguins-eggs PKGBUILD](https://gitlab.manjaro.org/packages/community/penguins-eggs), created from the author 
to investigate about the problems of the package eggs on manjaro.

# build and install

```
pamac update
```
If your are with bash, I suggest to install bash-completion.

```
pamac install bash-completion
```
## Build and install penguins-eggs

Copy and paste follow instructions
```
git clone https://github.com/pieroproietti/penguins-eggs-archilinux
cd penguins-eggs-archilinux
makepkg -srcCi
```
## Create your first iso, just CLI installer krill
```sudo eggs produce --fast```

## Create your first desktop iso, installer calamares
```sudo eggs calamares --install```
```sudo eggs produce --fast```

## Copy your iso image and boot the son of your system
You can use ventoy, simple USB, iso file with proxmox ve, virtualbox, vmware etc.


# Develop and collaborations link
* penguins-eggs discussion on [manjaro-forum](https://forum.manjaro.org/t/penguins-eggs-help-needed-for-manjaro-compatibility/96799)
* penguins-eggs PKGBUILD on [community](https://gitlab.manjaro.org/packages/community/penguins-eggs)
* penguins-eggs PKGBUILD [my way](https://github.com/pieroproietti/penguins-eggs-manjaro) (*)
* penguins-eggs [sources](https://github.com/pieroproietti/penguins-eggs)
* penguins-eggs [book](https://penguins-eggs.net/book/)
* penguins-eggs [blog](https://penguins-eggs.net)

(*) Here we refere always to that, but I hope with same help to solve the problems and have it in community again.


## Notes
This PKGBUILD is incomplete, I just started it. It's a good point to start to collaborate.

I'm starting with penguins-eggs-manjaro, removing the follow packages from dependencies:
* manjaro-tools-iso
* erofs-utils
^ glibc-locales

Of course, now there is the need to replace them with archlinux packages, the main question
is to produce an initramfs for live.

Started to use archiso and his hooks, but I have the follow problem: I have problems mounting lower a binded directory with overlayfs. 

Example:
~~~
mount --bind --make-slave /boot /home/eggs/ovarium/.overlay/lowerdir/boot
mount -o remount,bind,ro /home/eggs/ovarium/.overlay/lowerdir/boot
ovary: makeIfNotExist(/home/eggs/ovarium/.overlay/upperdir/boot)
mkdir /home/eggs/ovarium/.overlay/upperdir/boot -p
ovary: makeIfNotExist(/home/eggs/ovarium/.overlay/workdir/boot)
mkdir /home/eggs/ovarium/.overlay/workdir/boot -p
ovary: makeIfNotExist(/home/eggs/ovarium/filesystem.squashfs/boot)
mkdir /home/eggs/ovarium/filesystem.squashfs/boot -p
mount -t overlay overlay -o lowerdir=/home/eggs/ovarium/.overlay/lowerdir/boot,upperdir=/home/eggs/ovarium/.overlay/upperdir/boot,workdir=/home/eggs/ovarium/.overlay/workdir/boot /home/eggs/ovarium/filesystem.squashfs/boot
mount: /home/eggs/ovarium/filesystem.squashfs/boot: wrong fs type, bad option, bad superblock on overlay, missing codepage or helper program, or other error.
       dmesg(1) may have more information after failed mount system call.
~~~       
This is that I found in dmesg:
~~~
overlayfs: filesystem on '/home/eggs/ovarium/.overlay/lowerdir/boot' not supported
Strange enought becouse same code work on Debian, Devuan, Ubuntu and ManjaroLinux too. Perhaps I need some other package, at the moment I'm literally lost: imported the changement on the master and we stay here.
~~~
# How to create a new release (memo for me)
To create a new release, just edit followig lines in PKBUILD, essentiallt pkgver and _commit.

```
pkgver=9.1.29
pkgrel=1
_commit='29f20ce50a8fcdb855a70a40603a7c8b40163421'
```
