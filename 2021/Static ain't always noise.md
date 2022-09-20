# Static ain't always noise

## Objetivos
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/static)? This [BASH script](https://mercury.picoctf.net/static/bc72945175d643626d6ea9a689672dbd/ltdis.sh) might help!


## Solución 
```bash
┌──(kali㉿kali)-[~]
└─$ cd Downloads  
                                                                             
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
ltdis.sh  Obsidian-0.15.9.AppImage  static
                                                                             
┌──(kali㉿kali)-[~/Downloads]
└─$ chmod +x ./ltdis.sh 
                                                                             
┌──(kali㉿kali)-[~/Downloads]
└─$ ./ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
                                                                             
┌──(kali㉿kali)-[~/Downloads]
└─$ more static.ltdis.strings.txt 
    238 /lib64/ld-linux-x86-64.so.2
    361 libc.so.6
    36b puts
    370 __cxa_finalize
    37f __libc_start_main
    391 GLIBC_2.2.5
    39d _ITM_deregisterTMCloneTable
    3b9 __gmon_start__
    3c8 _ITM_registerTMCloneTable
    660 AWAVI
    667 AUATL
    6ba []A\A]A^A_
    6e8 Oh hai! Wait what? A flag? Yes, its around here somewhere!
    7c7 ;*3$
   1020 picoCTF{d15a5m_t34s3r_1e6a7731}
   1040 GCC: (Ubuntu 7.5.0-3ubuntu1~18.04) 7.5.0
   1671 crtstuff.c
   167c deregister_tm_clones
   1691 __do_global_dtors_aux
   16a7 completed.7698
   16b6 __do_global_dtors_aux_fini_array_entry
   16dd frame_dummy
   16e9 __frame_dummy_init_array_entry
   1708 static.c
   1711 __FRAME_END__
   171f __init_array_end
   1730 _DYNAMIC
   1739 __init_array_start                                                            
                                                                                      
┌──(kali㉿kali)-[~/Downloads]
└─$ more static.ltdis.strings.txt | grep picoCTF
   1020 picoCTF{d15a5m_t34s3r_1e6a7731}

```

## Notas adicionales 