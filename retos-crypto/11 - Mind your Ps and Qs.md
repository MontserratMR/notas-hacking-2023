## Descripción
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/b9ddda080c56fb421bf30409bec3460d/values)

## Pistas 
Bits are expensive, I used only a little bit over 100 to save money

## Solución
```
┌──(kali㉿kali)-[~]
└─$ cat values         
Decrypt my super sick RSA:
c: 964354128913912393938480857590969826308054462950561875638492039363373779803642185
n: 1584586296183412107468474423529992275940096154074798537916936609523894209759157543
e: 65537

*factorizamos n para obtener p y q*

┌──(kali㉿kali)-[~]
└─$ python3
Python 3.11.2 (main, Feb 12 2023, 00:48:52) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from Crypto.Util.number import long_to_bytes
>>> from Crypto.Util.number import inverse
>>> 
>>> c=964354128913912393938480857590969826308054462950561875638492039363373779803642185
>>> e=65537
>>> p=2434792384523484381583634042478415057961
>>> q=650809615742055581459820253356987396346063
>>> n=p*q
>>> n
1584586296183412107468474423529992275940096154074798537916936609523894209759157543
>>> tn= (p-1)*(q-1)
>>> d= inverse(e,tn)
>>> m=pow(c,d,n)
>>> m
13016382529449106065927291425342535437996222135352905256639684640304028661985917
>>> long_to_bytes(m)
b'picoCTF{sma11_N_n0_g0od_73918962}'

```

## Bandera
picoCTF{sma11_N_n0_g0od_73918962}

## Notas Adicionales
c - texto cifrado
m - mensaje texto plano
p - primo 1
q - primo 2
n - modulo
tn - totient n (euler)
e - exponente (llave pública) 2^16+1 = 65537
d - llave privada 

n = p * q
tn = (p - 1) * (q - 1)
d = e mod inv tn / inverse(e,tn)

Encriptar 
c = m^e mod n / pow(m,e,n)

Desencriptar
m = c^d mod n / pow(c,d,n)
