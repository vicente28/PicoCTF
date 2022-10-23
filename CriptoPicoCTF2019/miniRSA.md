# miniRSA

## Objetivos
Let's decrypt this: [ciphertext](https://jupiter.challenges.picoctf.org/static/eb5e6df8e14c52873cf88c582a1a4008/ciphertext)? Something seems a bit small.



## Solución 
```bash
└─$ cat ciphertext 

N: 29331922499794985782735976045591164936683059380558950386560160105740343201513369939006307531165922708949619162698623675349030430859547825708994708321803705309459438099340427770580064400911431856656901982789948285309956111848686906152664473350940486507451771223435835260168971210087470894448460745593956840586530527915802541450092946574694809584880896601317519794442862977471129319781313161842056501715040555964011899589002863730868679527184420789010551475067862907739054966183120621407246398518098981106431219207697870293412176440482900183550467375190239898455201170831410460483829448603477361305838743852756938687673
e: 3

ciphertext (c): 2205316413931134031074603746928247799030155221252519872650080519263755075355825243327515211479747536697517688468095325517209911688684309894900992899707504087647575997847717180766377832435022794675332132906451858990782325436498952049751141 
                                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ sudo python3 -m pip install gmpy2 
[sudo] password for kali: 
Collecting gmpy2
  Downloading gmpy2-2.1.2-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (3.6 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 3.6/3.6 MB 3.3 MB/s eta 0:00:00
Installing collected packages: gmpy2
Successfully installed gmpy2-2.1.2
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv  



```


``` shell

┌──(kali㉿kali)-[~]
└─$ python3                               
Python 3.10.7 (main, Sep  8 2022, 14:34:29) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from gmpy2 import * 
>>> from Crypto.Util.number import long_to_bytes
>>> 
>>> gmpy2.get_context().precision = 2048
>>> 
>>> e = 3
>>> c = 2205316413931134031074603746928247799030155221252519872650080519263755075355825243327515211479747536697517688468095325517209911688684309894900992899707504087647575997847717180766377832435022794675332132906451858990782325436498952049751141
>>> root, exact = iroot(c,e)
>>> root
mpz(13016382529449106065894479374027604750406953699090365388203722801043052339225981)
>>> print(long_to_bytes(root))
b'picoCTF{n33d_a_lArg3r_e_d0cd6eae}'

``` 





## Notas adicionales 

https://simple.wikipedia.org/wiki/RSA_algorithm

c - texto cifrado
m - mensaje texto plano
p  - primo 
q  - primo 2
n - modulo 
tn - totient n (euler)
e - exponente (llave publica) 2^16+1 = 65537
d - llave privada 


n = p*q
tn= ( p - q )*  * (q - 1) 
d = e mod inv tn  / inverse (e, tn)

Encriptar : c = m^e mod n / pow(m,e,n) 

Desencriptar : m = c^d mod  n / pow(c,d,n)

Como e es muy pequeña 
c = m^e mod n 
c = m ^ 3
m = 3 raiz c 

No aseguramos que tengamos la libreria de python gmpy para manegar números de alta presición

y tambien asegurarnos que tenemos intalada la libreria de cryptografía installada pycryptodome