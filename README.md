# qemu-on-win

Cia daug dokumentacijos:  
https://qemu.weilnetz.de/doc/qemu-doc.html#Introduction

1. pervadinom iso faila i paprasta pavadinima
2. ikelem ji i qemu folda
3. run cmd
4. cd qemu_foldas
5. alokuojam vieta "hardui" 8G, qcow reiskia dynamic  
   `qemu-img.exe create -f qcow2 kali64.img 8G`
   Jeigu reikia ne dynamic, o fixed, galima bandyti taip:
   `qemu-img.exe create -f vpc -o subformat=fixed kali64.vhd 8G`
6. paleidziam iso faila, priskyre ramus(sets the guest startup RAM size to 2GB, creates 3 slots to hotplug additional memory and sets the maximum memory the guest can reach to 6GB):  
   `qemu-system-x86_64.exe kali64.img -boot d -cdrom kali64.iso -m 2G,slots=3,maxmem=6G`
   
Dabartinis kodas paleidimui:
  `qemu-system-x86_64.exe kali64.vhd -boot d -m 2G,slots=3,maxmem=6G`
