# penguins-eggs-arch

## Build and install penguins-eggs on Arch

Copy and paste follow instructions
```
git clone https://github.com/pieroproietti/penguins-eggs-arch
cd penguins-eggs-arch
makepkg -srcCi
```

## Configuration (default)

```sudo eggs dad -d```

## Create your first iso, just with CLI installer krill
```sudo eggs produce --fast```

## Create your first desktop iso, with GUI installer calamares

```sudo eggs calamares --install```

```sudo eggs produce --fast```

### clone a system with users uncrypted
You can prefere to clone your system, all users will be saved uncrypted on the live.
```sudo eggs produce --fast --clone```

### backup a system with users crypted
Or you can prefere to backup your system: all users will be saved crypted in a LUKS volume inside the live system and will be restored with krill during installation.

## Copy your iso image and boot the son of your system
You can use ventoy, simple USB, iso file with proxmox ve, virtualbox, vmware etc.


# Develop and collaborations link
* facebook group: [facebook group](https://www.facebook.com/groups/128861437762355)
* telegram: [telegram penguin's eggs](https://web.telegram.org/z/#-1447280458)
* penguins-eggs [sources](https://github.com/pieroproietti/penguins-eggs)
* penguins-eggs [book](https://penguins-eggs.net/book/)
* penguins-eggs [blog](https://penguins-eggs.net)

