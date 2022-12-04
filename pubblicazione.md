# Pubblicazione in AUR

penguins-eggs è pubblicato su AUR, lo si può trovare alla pagina:
```
https://aur.archlinux.org/packages/penguins-eggs
```

Loggandosi vi sono due link, uno in sola lettura:

```
https://aur.archlinux.org/penguins-eggs.git
```

ed uno per lettura e scrittura:
```
ssh://aur@aur.archlinux.org/penguins-eggs.git
```

# Aggiornamento
Per aggiornare, con un utente in possesso della chiave privata:

```git clone ssh://aur@aur.archlinux.org/penguins-eggs.git```

## .SRCINFO
Prima di poter pubblicare occorre ri-creare il file .SRCINFO con il comando:

```makepkg --printsrcinfo > .SRCINFO```

 