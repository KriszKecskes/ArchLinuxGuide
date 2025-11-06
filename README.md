# Arch Linux Segédlet

Ez a segédlet azért jött létre, hogy segítse a kezdő és a kevésbé kezdő Arch Linux felhasználókat az alapvető dolgok végrehajtásában.

## USB-s nyomtató és scannelő engedélyezése:
Arch Linuxon a nyomtatás CUPS (Common Unix Printing System) segítségével működik. A legtöbb modern nyomtató támogatja a "driverless" nyomtatást (IPP Everywhere/AirPrint protokollon keresztül), de régebbi modellekhez szükség lehet specifikus driverekre, például a Gutenprint csomagból vagy Canon-specifikus AUR csomagokból.

```bash
sudo pacman -S cups cups-pdf
```
```bash
sudo systemctl enable --now cups.service
```

Ha USB-s a nyomtatód, akkor az `usbutils` telepítése után az `lsusb` parancsot futtatva már látdnod kell a listában a nyomtatódat.

## CUE és BIN fájlok ISO-ba konvertálása:

Szükség van hozzá a `bchunk` nevű alkalmazásra.

```bash
sudo pacman -S bchunk
```

Aztán példa:

```bash
bchunk disc1.bin disc1.cue disc1
```
A fenti példa egy disc1 nevű iso-t készít a bin és a cue fájlokból.

## DaVinci Resolve telepítés utáni műveletek:

```bash
cd /opt/resolve/libs
sudo mkdir disabled-libraries
sudo mv libglib* disabled-libraries
sudo mv libgio* disabled-libraries
sudo mv libgmodule* disabled-libraries
```


