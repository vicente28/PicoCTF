# waves over lambda

## Objetivos
We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with `nc jupiter.challenges.picoctf.org 39894`.

## Solución 
```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ nc jupiter.challenges.picoctf.org 39894
-------------------------------------------------------------------------------
pktzxmij wyxy aj ekbx dfmz - dxycbytpe_aj_p_koyx_fmglrm_mzdfpzieby
-------------------------------------------------------------------------------
mfyqye dekrkxkoaipw smxmgmnko vmj iwy iwaxr jkt kd dekrkx hmofkoaipw smxmgmnko, m fmtr kvtyx vyff stkvt at kbx rajixapi at waj kvt rme, mtr jiaff xygyglyxyr mgktz bj kvatz ik waj zfkkge mtr ixmzap rymiw, vwapw wmhhytyr iwaxiyyt eymxj mzk, mtr vwapw a jwmff ryjpxaly at aij hxkhyx hfmpy. dkx iwy hxyjyti a vaff ktfe jme iwmi iwaj fmtrkvtyxdkx jk vy bjyr ik pmff wag, mfiwkbzw wy wmxrfe jhyti m rme kd waj fady kt waj kvt yjimiyvmj m jixmtzy iehy, eyi kty hxyiie dxycbytife ik ly gyi vaiw, m iehy mluypi mtr oapakbj mtr mi iwy jmgy iagy jytjyfyjj. lbi wy vmj kty kd iwkjy jytjyfyjj hyxjktj vwk mxy oyxe vyff pmhmlfy kd fkksatz mdiyx iwyax vkxfrfe mddmaxj, mtr, mhhmxytife, mdiyx tkiwatz yfjy. dekrkx hmofkoaipw, dkx atjimtpy, lyzmt vaiw tyqi ik tkiwatz; waj yjimiy vmj kd iwy jgmffyji; wy xmt ik raty mi kiwyx gyt'j imlfyj, mtr dmjiytyr kt iwyg mj m ikmre, eyi mi waj rymiw ai mhhymxyr iwmi wy wmr m wbtrxyr iwkbjmtr xkblfyj at wmxr pmjw. mi iwy jmgy iagy, wy vmj mff waj fady kty kd iwy gkji jytjyfyjj, dmtimjiapmf dyffkvj at iwy vwkfy rajixapi. a xyhymi, ai vmj tki jibharaieiwy gmukxaie kd iwyjy dmtimjiapmf dyffkvj mxy jwxyvr mtr atiyffazyti ytkbzwlbi ubji jytjyfyjjtyjj, mtr m hypbfamx tmiaktmf dkxg kd ai.


-------------------------------------------------------------------------------
congrats here is your flag - frequency_is_c_over_lambda_agflcgtyue
-------------------------------------------------------------------------------
alexey fyodorovitch karamazov was the third son of fyodor pavlovitch karamazov, a land owner well known in our district in his own day, and still remembered among us owing to his gloomy and tragic death, which happened thirteen years ago, and which i shall describe in its proper place. for the present i will only say that this landownerfor so we used to call him, although he hardly spent a day of his life on his own estatewas a strange type, yet one pretty frequently to be met with, a type abject and vicious and at the same time senseless. but he was one of those senseless persons who are very well capable of looking after their worldly affairs, and, apparently, after nothing else. fyodor pavlovitch, for instance, began with next to nothing; his estate was of the smallest; he ran to dine at other men's tables, and fastened on them as a toady, yet at his death it appeared that he had a hundred thousand roubles in hard cash. at the same time, he was all his life one of the most senseless, fantastical fellows in the whole district. i repeat, it was not stupiditythe majority of these fantastical fellows are shrewd and intelligent enoughbut just senselessness, and a peculiar national form of it.

```

## Notas adicionales 

https://es.wikipedia.org/wiki/Cifrado_por_sustituci%C3%B3n

Para este reto nos enconramos con un cifrado de sustitucón en el cual metodos de texto plano son remplazadas con el texto encriptado de manera definida con ayuda de una llave, 
al no contar con la llave tenemos que hacer un ataque de fuerza bruta o un analisis de frecuencias para ver cuales letras se repiten y con que frecuencia 