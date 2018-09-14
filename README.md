# qemu-on-win

Cia daug dokumentacijos:  
https://qemu.weilnetz.de/doc/qemu-doc.html#Introduction

1. pervadinom iso faila i paprasta pavadinima
2. ikelem ji i qemu folda
3. run cmd
4. cd qemu_foldas
5. alokuojam vieta "hardui"  
   `qemu-img.exe create -f qcow2 kali64.img 8G`
6. paleidziam iso faila, priskyre ramus  
   `qemu-system-x86_64.exe kali64.img -boot d -cdrom kali64.iso -m 4096`  
Gudriau butu buve: sets the guest startup RAM size to 1GB, creates 3 slots to hotplug additional memory and sets the maximum memory the guest can reach to 4GB:  
   `qemu-system-x86_64.exe kali64.img -boot d -cdrom kali64.iso -m 1G,slots=3,maxmem=4G`
   
