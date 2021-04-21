---
layout: post
title: Low budget NAS build
author: jelle
---

I built myself a cheap NAS to store my backups and media. These are the parts I chose:

- [Fractal Design Node 804](https://tweakers.net/pricewatch/375787/fractal-design-node-804.html) (€109,85)
- [Asus Prime A320M-K](https://tweakers.net/pricewatch/765703/asus-prime-a320m-k.html) (€47,00)
- [AMD Ryzen 5 1600](https://tweakers.net/pricewatch/1507322/amd-ryzen-5-1600-12nm-wraith-stealth-koeler-boxed.html) (€109,00)
- [EVGA 500W BQ](https://tweakers.net/pricewatch/741657/evga-500w-bq.html) (€66,20)
- [Corsair ValueSelect CMV4GX4M1A2133C15](https://tweakers.net/pricewatch/438352/corsair-valueselect-cmv4gx4m1a2133c15.html) (€22,87)
- [XPG SX6000 Lite 128GB](https://tweakers.net/pricewatch/1288472/xpg-sx6000-lite-128gb.html) (€24,99)
- Dell PERC H310 SAS/SATA controller (€55,00 second hand)
- [Toshiba MG07ACA12TE (512e), 12TB](https://tweakers.net/pricewatch/1165311/toshiba-mg07aca12te-512e-12tb.html) × 4 (€284,31)

Total without disks: €435,91

This NAS can fit and connect ten 3,5" disks and two 2,5" disks. Similarly sized commercial NASs start at double the price. 

At the moment I haven't tested everything yet, but I installed NixOS on the ssd and that is working fine. I didn't actually have a screen to do the installation, so I made a custom USB image with SSH opened and checked my DHCP server for the IP address. Luckily the motherboard defaults to booting from an attached USB drive (on the USB 2.0 port that is).

The parts were all chosen to be the cheapest that support the maximum amount of drives. The power supply was chosen because the cables can be replaced. It comes with 2 SATA power cables, but those have only 3 connectors and the case fan controller also uses SATA power. I bought some extra power cables which support 4 connectors. The power supply supports 3 of these cables.

The CPU isn't the cheapest option, but is very good for the price. I wanted to use a modern Ryzen CPU and wanted to make sure it wasn't underpowered, because it would be the hardest to replace. I also wasn't sure if the amount of RAM was enough, but it was so cheap that I could easily replace it with two 8GB sticks or I could add another 4GB stick. For now the RAM amount seems enough though.

I am very happy with the case, the drives are inserted in drive bays with 4 drives, and can be removed without tools. I only need a screwdriver to bolt down the power supply and the motherboard.