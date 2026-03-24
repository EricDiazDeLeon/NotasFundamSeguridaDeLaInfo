## Objetivo
Download this disk image and find the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/213/disk.flag.img.gz)
## Solución
```bash
ericdiazdeleon in @Descargas/retos ❯ wget https://artifacts.picoctf.net/c/213/disk.flag.img.gz
Saving 'disk.flag.img.gz'
HTTP response 200  [https://artifacts.picoctf.net/c/213/disk.flag.img.gz]
disk.flag.img.gz     100% [======================================================>]   42.30M   13.81MB/s
                          [Files: 1  Bytes: 42.30M [10.66MB/s] Redirects: 0  Todo:]
ericdiazdeleon in @Descargas/retos ❯ gzip -d disk.flag.img.gz
ericdiazdeleon in @retos/orchid ❯ mmls disk.flag.img 
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000411647   0000204800   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000411648   0000819199   0000407552   Linux (0x83)

ericdiazdeleon in @retos/orchid ❯ fls -o 2048 disk.flag.img 
d/d 11:	lost+found
r/r 12:	ldlinux.sys
r/r 13:	ldlinux.c32
r/r 15:	config-virt
r/r 16:	vmlinuz-virt
r/r 17:	initramfs-virt
l/l 18:	boot
r/r 20:	libutil.c32
r/r 19:	extlinux.conf
r/r 21:	libcom32.c32
r/r 22:	mboot.c32
r/r 23:	menu.c32
r/r 14:	System.map-virt
r/r 24:	vesamenu.c32
V/V 25585:	$OrphanFiles

ericdiazdeleon in @retos/orchid ❯ fls -o 411648 disk.flag.img  472
r/r 1875:	.ash_history
r/r * 1876(realloc):	flag.txt
r/r 1782:	flag.txt.enc

ericdiazdeleon in @retos/orchid ❯ icat -0 411648 disk.flag.img 1782
icat: opción inválida -- '0'
Invalid argument: 411648
usage: icat [-hrRsvV] [-f fstype] [-i imgtype] [-b dev_sector_size] [-o imgoffset] image [images] inum[-typ[-id]]
	-h: Do not display holes in sparse files
	-r: Recover deleted file
	-R: Recover deleted file and suppress recovery errors
	-s: Display slack space at end of file
	-i imgtype: The format of the image file (use '-i list' for supported types)
	-b dev_sector_size: The size (in bytes) of the device sectors
	-f fstype: File system type (use '-f list' for supported types)
	-o imgoffset: The offset of the file system in the image (in sectors)
	-P pooltype: Pool container type (use '-P list' for supported types)
	-B pool_volume_block: Starting block (for pool volumes only)
	-S snap_id: Snapshot ID (for APFS only)
	-v: verbose to stderr
	-V: Print version
	-k password: Decryption password for encrypted volumes

ericdiazdeleon in @retos/orchid ❯ icat -o 411648 disk.flag.img 1782
Salted__�ށ��e��B�J�c�$QE&$��4jM�KGeE�1�^Ȥ7� ���؎$�'%
ericdiazdeleon in @retos/orchid ❯ strings -t d disk.flag.img | grep flag.txt
218985524 flag.txt
218985540 flag.txt.enc
219964416 touch flag.txt
219964431 nano flag.txt 
219964483 nano flag.txt 
219964506 openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
219964588 shred -u flag.txt
303193140 flag.txt
303317044 flag.txt
303317060 flag.txt.enc
303328308 flag.txt
303328324 flag.txt.enc

ericdiazdeleon in @retos/orchid ❯ icat -o 411648 disk.flag.img 1782 > flag.txt.enc

ericdiazdeleon in @retos/orchid ❯ ls
disk.flag.img  flag.txt.enc
ericdiazdeleon in @retos/orchid ❯ aes256 -d -salt flag.txt.enc -out flag.txt umbreakablepassword1234567
ericdiazdeleon in @retos/orchid ❯ cat flag.txt
picoCTF{h4un71ng_p457_5113beab}

```
## Notas Adicionales
Primero, descargue una imagen de disco comprimida y la descomprimí. Luego, usando herramientas de análisis forense, examine las particiones del disco y explore los archivos en ellas. Encontre un archivo cifrado que contenía la bandera, así como un comando en el historial del sistema que revelaba la contraseña utilizada para cifrarlo. Finalmente, extraje el archivo cifrado y lo descifre con la contraseña obtenida, obteniendo así la bandera.
### Referencias