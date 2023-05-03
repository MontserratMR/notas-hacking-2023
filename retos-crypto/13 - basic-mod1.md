## Descripción
We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/129/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore. Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)

## Pistas 
1. Do you know what `mod 37` means?
2. `mod 37` means modulo 37. It gives the remainder of a number after being divided by 37.

## Solución
```
┌──(kali㉿kali)-[~]
└─$ cat message.txt 
350 63 353 198 114 369 346 184 202 322 94 235 114 110 185 188 225 212 366 374 261 213  


python script
mport string
alfabeto = string.ascii_lowercase
alfabeto += "0123456789_"

flag_enc = [350,63,353,198,114,369,346,184,202,322,94,235,114,110,185,188,225,212,366,374,2>
flag = ""
for c in flag_enc:
    pos = c % 37
    flag += alfabeto[pos]

print(flag)

──(kali㉿kali)-[~]
└─$ python3 challenge.py
r0und_n_r0und_add17ec2
```

## Bandera
picoCTF{r0und_n_r0und_add17ec2}


