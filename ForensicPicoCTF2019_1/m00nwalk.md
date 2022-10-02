# m00nwalk

## Objetivos
Decode this [message](https://jupiter.challenges.picoctf.org/static/fc1edf07742e98a480c6aff7d2546107/message.wav) from the moo


## Solución 
```bash
──(kali㉿kali)-[/]
└─$ cd opt 
                                                                                                                 
┌──(kali㉿kali)-[/opt]
└─$ sudo git clone https://github.com/colaclanth/sstv.git
[sudo] password for kali: 
Cloning into 'sstv'...
remote: Enumerating objects: 221, done.
remote: Total 221 (delta 0), reused 0 (delta 0), pack-reused 221
Receiving objects: 100% (221/221), 1.01 MiB | 505.00 KiB/s, done.
Resolving deltas: 100% (140/140), done.
                                                                                                                 
┌──(kali㉿kali)-[/opt]
└─$ python setup.py install
python: can't open file '/opt/setup.py: [Errno 2] No such file or directory
                                                                                                                 
┌──(kali㉿kali)-[/opt]
└─$ ls
microsoft  sstv
                                                                                                                 
┌──(kali㉿kali)-[/opt]
└─$ sstv                                                 
                                                                                                                 
┌──(kali㉿kali)-[/opt/sstv]
└─$ ls    
examples  LICENSE  README.md  setup.py  sstv  test

┌──(kali㉿kali)-[/opt/sstv]
└─$ sudo python setup.py install

┌──(kali㉿kali)-[/home]
└─$ cd ~  

┌──(kali㉿kali)-[~]
└─$ cd Downloads 
                                                                                                                 
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
message.wav  Obsidian-0.15.9.AppImage
                                                                                                                 
┌──(kali㉿kali)-[~/Downloads]
└─$ sstv -d message.wav -o result.png
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [###############################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!


┌──(kali㉿kali)-[~/Downloads]
└─$ ls
message.wav  Obsidian-0.15.9.AppImage  result.png
                                                                                                                 
┌──(kali㉿kali)-[~/Downloads]
└─$ open result.png 

```

## Notas adicionales 