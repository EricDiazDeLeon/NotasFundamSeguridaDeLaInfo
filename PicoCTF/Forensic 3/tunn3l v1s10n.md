## Objetivo
We found this file. Recover the flag. [tunn3l_v1s10n](https://challenge-files.picoctf.net/c_wily_courier/626df9feed926c1e1280804f5d87fde5576e266ff250a819a5528b0471b0f3f7/tunn3l_v1s10n)
## Solución
```bash
ericdiazdeleon in @Descargas/retos ❯ wget https://challenge-files.picoctf.net/c_wily_courier/626df9feed926c1e1280804f5d87fde5576e266ff250a819a5528b0471b0f3f7/tunn3l_v1s10n
Saving 'tunn3l_v1s10n'
HTTP response 200  [https://challenge-files.picoctf.net/c_wily_courier/626df9feed926c1e1280804f5d87fde557tunn3l_v1s10n        100% [======================================================>]    2.75M    4.95MB/s
                          [Files: 1  Bytes: 2.75M [1.79MB/s] Redirects: 0  Todo: 0]
ericdiazdeleon in @Descargas/retos ❯ hexedit tunn3l_v1s10n
ericdiazdeleon in @Descargas/retos ❯ hexedit tunn3l_v1s10n
ericdiazdeleon in @Descargas/retos ❯ python
Python 3.14.3 (main, Feb  4 2026, 00:00:00) [GCC 15.2.1 20260123 (Red Hat 15.2.1-7)] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> hex(1134)
'0x46e'
>>> Hex(306)
Traceback (most recent call last):
  File "<python-input-1>", line 1, in <module>
    Hex(306)
    ^^^
NameError: name 'Hex' is not defined. Did you mean: 'hex'?
>>> hex(306)
'0x132'
>>> hex(850)
'0x352'
>>>  
ericdiazdeleon in @Descargas/retos ❯ hexedit tunn3l_v1s10n 
00000000   42 4D 8E 26  2C 00 00 00  00 00 36 00  00 00 28 00  00 00 6E 04  BM.&,.....6...(...n.
00000014   00 00 52 03  00 00 01 00  18 00 00 00  00 00 58 26  2C 00 25 16  ..R...........X&,.%.
00000028   00 00 25 16  00 00 00 00  00 00 00 00  00 00 23 1A  17 27 1E 1B  ..%...........#..'..
0000003C   29 20 1D 2A  21 1E 26 1D  1A 31 28 25  35 2C 29 33  2A 27 38 2F  ) .*!.&..1(%5,)3*'8/
00000050   2C 2F 26 23  33 2A 26 2D  24 20 3B 32  2E 32 29 25  30 27 23 33  ,/&#3*&-$ ;2.2)%0'#3
00000064   2A 26 38 2C  28 36 2B 27  39 2D 2B 2F  26 23 1D 12  0E 23 17 11  *&8,(6+'9-+/&#...#..
00000078   29 16 0E 55  3D 31 97 76  66 8B 66 52  99 6D 56 9E  70 58 9E 6F  )..U=1.vf.fR.mV.pX.o
0000008C   54 9C 6F 54  AB 7E 63 BA  8C 6D BD 8A  69 C8 97 71  C1 93 71 C1  T.oT.~c..m..i..q..q.
000000A0   97 74 C1 94  73 C0 93 72  C0 8F 6F BD  8E 6E BA 8D  6B B7 8D 6A  .t..s..r..o..n..k..j
000000B4   B0 85 64 A0  74 55 A3 77  5A 98 6F 56  76 52 3A 71  52 3D 6C 4F  ..d.tU.wZ.oVvR:qR=lO
000000C8   40 6D 52 44  6E 53 49 77  5E 54 53 39  33 70 58 52  76 61 59 73  @mRDnSIw^TS93pXRvaYs
000000DC   5F 54 7E 6B  5E 86 74 63  7E 6A 59 76  62 50 76 5E  4C 7A 62 50  _T~k^.tc~jYvbPv^LzbP
000000F0   87 6D 5D 83  69 59 8D 73  63 9B 81 71  9E 84 74 98  7E 6E 9B 81  .m].iY.sc..q..t.~n..
00000104   71 8D 73 63  73 5A 4A 70  57 47 5A 41  31 4F 36 26  4E 37 27 4F  q.scsZJpWGZA1O6&N7'O
00000118   38 28 4F 38  28 51 3A 2A  50 39 29 4F  38 29 4B 35  29 50 3A 2F  8(O8(Q:*P9)O8)K5)P:/
0000012C   4B 35 2A 3F  29 1E 42 2E  23 4B 37 2C  45 31 26 3F  2B 20 43 2F  K5*?).B.#K7,E1&?+ C/
00000140   24 43 2F 24  40 2A 1F 48  32 27 4B 32  28 47 2E 24  40 27 1D 45  $C/$@*.H2'K2(G.$@'.E
00000154   2C 22 4C 34  28 4C 34 28  4B 33 27 4A  32 26 4C 32  24 4E 34 26  ,"L4(L4(K3'J2&L2$N4&
00000168   50 35 27 52  37 29 53 36  28 55 38 2A  4B 30 22 5D  42 34 63 49  P5'R7)S6(U8*K0"]B4cI
0000017C   39 49 2F 1F  44 2B 1B 4D  34 24 4D 36  27 4A 33 24  46 2C 20 48  9I/.D+.M4$M6'J3$F, H
00000190   2E 22 46 2E  22 44 2E 22  3C 26 1B 32  20 15 30 1F  16 32 23 1A  ."F."D."<&.2 .0..2#.
---  tunn3l_v1s10n	--0x0/0x2C268E--0%-----------------------------------------------------
```
## Notas Adicionales
Reparé la cabecera de el archivo usando el hexedit y la imagen se arregló pero había una flag falsa, por lo que investigué y al parecer lo que se hace en este reto es cambiar la resolucion de la imagen, ya que es muy larga y debemos hacerla mas pequeña (850) y pasar este numero a hexadecimal para posteriormente modificarlo en el hexedit, guardar y abrir la imagen para encontrar ahí la bandera.
picoCTF{qu1t3_a_v13w_2020}
### Referencias
