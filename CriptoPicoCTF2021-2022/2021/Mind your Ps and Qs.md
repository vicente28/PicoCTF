# Mind your Ps and Qs

## Objetivos
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/51d68e61bb41207a55f24e753f07c5a3/values)


## Solución 
```bash
>>> from Crypto.Util.number import long_to_bytes
>>> from Crypto.Util.number import inverse
>>> 
>>> c = 62324783949134119159408816513334912534343517300880137691662780895409992760262021
>>> e = 65537
>>> p = 1899107986527483535344517113948531328331
>>> q = 674357869540600933870145899564746495319033
>>> n = p * q 
>>> n
1280678415822214057864524798453297819181910621573945477544758171055968245116423923
>>> tn= ( p - 1)*(q - 1) 
>>> d = inverse (e, tn)
>>> d
449332735606084960351204406909610297301574728466820933515942864925459265983556193
>>> m = pow(c,d,n)
>>> m
13016382529449106065927291425342535437996222135352905256639555654677400177227645
>>> long_to_bytes(m)
b'picoCTF{sma11_N_n0_g0od_05012767}'



┌──(kali㉿kali)-[~]
└─$ cd /opt  
                                                                                                                    
┌──(kali㉿kali)-[/opt]
└─$ cd RsaCtfTool 
                                                                                                                    
┌──(kali㉿kali)-[/opt/RsaCtfTool]
└─$ ls
attacks          Dockerfile       lib                        README.md         sage
CHANGELOG.md     Dockerfile_full  LICENSE.md                 requirements.txt  setup.py
CONTRIBUTING.md  examples         optional-requirements.txt  RsaCtfTool.py     test.sh
                                                                                                                    
┌──(kali㉿kali)-[/opt/RsaCtfTool]
└─$ python3 RsaCtfTool.py -n 1280678415822214057864524798453297819181910621573945477544758171055968245116423923 -e 65537 --uncipher 62324783949134119159408816513334912534343517300880137691662780895409992760262021
private argument is not set, the private key will not be displayed, even if recovered.

[*] Testing key /tmp/tmpz0z4r6jo.
attack initialized...
[*] Performing smallq attack on /tmp/tmpz0z4r6jo.
[*] Performing factordb attack on /tmp/tmpz0z4r6jo.
[*] Attack success with factordb method !

Results for /tmp/tmpz0z4r6jo:

Unciphered data :
HEX : 0x7069636f4354467b736d6131315f4e5f6e305f67306f645f30353031323736377d
INT (big endian) : 13016382529449106065927291425342535437996222135352905256639555654677400177227645
INT (little endian) : 14498984152027328652717047150172180511619660760336976443081352114340772802947440
utf-8 : picoCTF{sma11_N_n0_g0od_05012767}
STR : b'picoCTF{sma11_N_n0_g0od_05012767}'
HEX : 0x007069636f4354467b736d6131315f4e5f6e305f67306f645f30353031323736377d
INT (big endian) : 13016382529449106065927291425342535437996222135352905256639555654677400177227645
INT (little endian) : 3711739942918996135095564070444078210974633154646265969428826141271237837554544640
utf-8 : picoCTF{sma11_N_n0_g0od_05012767}
utf-16 : 瀀捩䍯䙔獻慭ㄱ也湟弰で摯た〵㈱㘷紷
STR : b'\x00picoCTF{sma11_N_n0_g0od_05012767}'
                                                                                                                    
┌──(kali㉿kali)-[/opt/RsaCtfTool]


```

## Notas adicionales 
c - texto cifrado
m - mensaje texto plano
p  - primo 
q  - primo 2
n - modulo 
tn - totient n (euler)
e - exponente (llave publica) 2^16+1 = 65537
d - llave privada 


n = p*q
tn= ( p - 1)*  * (q - 1) 
d = e mod inv tn  / inverse (e, tn)

Encriptar : c = m^e mod n / pow(m,e,n) 

Desencriptar : m = c^d mod  n / pow(c,d,n)

Para este nivel el detalle esta en la n que es muy pequeña por esa razón nosotros podemos factorizar la n en la pagina factor de b 
y podemos obtener p y q  http://factordb.com/