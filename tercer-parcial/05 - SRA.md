## Descripción
I just recently learnt about the SRA public key cryptosystem... or wait, was it supposed to be RSA? Hmmm, I should probably check...

Additional details will be available after launching your challenge instance.

Connect to the program on our server: `nc saturn.picoctf.net 60304`
Download the program: [chal.py](https://artifacts.picoctf.net/c/299/chal.py)

## Pistas 

## Solución

```
┌──(kali㉿kali)-[~]
└─$ cat chal.py   
from Crypto.Util.number import getPrime, inverse, bytes_to_long
from string import ascii_letters, digits
from random import choice

pride = "".join(choice(ascii_letters + digits) for _ in range(16))
gluttony = getPrime(128)
greed = getPrime(128)
lust = gluttony * greed
sloth = 65537
envy = inverse(sloth, (gluttony - 1) * (greed - 1))

anger = pow(bytes_to_long(pride.encode()), sloth, lust)

print(f"{anger = }")
print(f"{envy = }")

print("vainglory?")
vainglory = input("> ").strip()

if vainglory == pride:
    print("Conquered!")
    with open("/challenge/flag.txt") as f:
        print(f.read())
else:
    print("Hubris!")
```

```
from pwn import *
import primefac
from itertools import combinations
from Crypto.Util.number import long_to_bytes

# function to generate all the sub lists
def sub_lists (l):
    # initializing empty list
    comb = []

    #Iterating till length of list
    for i in range(1,len(l)+1):
        # Generating sub list
        comb += [list(j) for j in combinations(l, i)]
    # Returning list
    return comb

def divisors(phi):
   print("Give me the divisors of ", phi-1)
   # this is dangerous, but I'm trusting me
   return(eval(input()))

# connect to the server
r = remote('saturn.picoctf.net', 59754)
# get ciphertext
r.recvuntil("anger =")
ciphertext=int(r.recvline())
# get d
r.recvuntil("envy =")
d=int(r.recvline())
print("cipher=",ciphertext)
print("d=",d)
print(r.recvuntil("vainglory?"))
r.recvline()
# since d is e^-1 mod (p-1)*(q-1), d*e=k*(p-1)*(q-1)+1
# so (p-1)*(q-1)*k = d*e-1
factors=divisors(d*65537)
combos = sub_lists(factors)
primes = set()
# try all possible subsets of the list of factors as the factors of (p-1)
for l in combos:
   product = 1
   # multiply them together to get p-1
   for k in l:
      product = product * k
   # if the right length and adding 1 yields a prime, then maybe
   if product.bit_length()==128 and primefac.isprime(product+1):
      primes.add(product+1)
print(primes)
primelist = list(primes)
# try all possible prime pairs
for p in primelist:
   for q in primelist:
      n=p*q
      # decode with this possible n
      plain = pow(ciphertext,d,n)
      try:
         plaintext = long_to_bytes(plain)
         # see if it corresponds to text and if so, try it
         print(plaintext.decode())
         r.sendline(plaintext.decode())
         print(r.recvline())
         print(r.recvline())
         print(r.recvline())
      except:
         continue
```

```
┌──(kali㉿kali)-[~]
└─$ python3 sra.py      
[+] Opening connection to saturn.picoctf.net on port 60864: Done
/home/kali/sra.py:26: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("anger =")
/home/kali/sra.py:29: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("envy =")
cipher= 16105063311218452452160853412000171954908470843488996832614498731304353629696
d= 22275182075968788418755804289214766540911731448188507684813016885589416540453
/home/kali/sra.py:33: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  print(r.recvuntil("vainglory?"))
b'vainglory?'
Give me the divisors of  1459848607712766486599999145702268154791732143919930228139590687630873591811668260
[2, 2, 3, 5, 23, 439, 7457, 132647, 2229701, 340928703961241524679088995687, 3204737349624981959212739653691]
{198529715397182471860830248067822416711, 328697879367023907374175821654425913987}
tGHycG0hqNHutJz5
/home/kali/sra.py:61: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.sendline(plaintext.decode())
b'> tGHycG0hqNHutJz5\r\n'
b'Conquered!\r\n'
b'picoCTF{7h053_51n5_4r3_n0_m0r3_3858bd66}\r\n'
tGHycG0hqNHutJz5
[*] Closed connection to saturn.picoctf.net port 60864
```


## Bandera
picoCTF{7h053_51n5_4r3_n0_m0r3_3858bd66}

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

## Referencias
https://www.dcode.fr/prime-factors-decomposition