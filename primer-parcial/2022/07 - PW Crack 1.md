## Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/10/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/10/level1.flag.txt.enc) in the same directory too.

## Pistas 
1. To view the file in the webshell, do: `$ nano level1.py`
2. To exit `nano`, press Ctrl and x and follow the on-screen prompts.
3. The `str_xor` function does not need to be reverse engineered for this challenge.
## Solución
Descargamos los archivos y al analizar la validación para la contraseña podemos ver que es "691d", simplemente corremos el programa y cuando nos pregunta la contraseña la ingresamos. Tenemos la bandera.

```
Welcome to the picoCTF webshell!
dnightshade-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/10/level1.py
--2023-03-26 02:42:08--  https://artifacts.picoctf.net/c/10/level1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.6, 108.156.172.74, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 876 [application/octet-stream]
Saving to: 'level1.py'

level1.py                    100%[=============================================>]     876  --.-KB/s    in 0s      

2023-03-26 02:42:08 (469 MB/s) - 'level1.py' saved [876/876]

dnightshade-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/10/level1.flag.txt.enc
--2023-03-26 02:42:22--  https://artifacts.picoctf.net/c/10/level1.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.6, 108.156.172.74, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 30 [application/octet-stream]
Saving to: 'level1.flag.txt.enc'

level1.flag.txt.enc          100%[=============================================>]      30  --.-KB/s    in 0s      

2023-03-26 02:42:22 (26.3 MB/s) - 'level1.flag.txt.enc' saved [30/30]

dnightshade-picoctf@webshell:~$ nano level1.py

### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################


flag_enc = open('level1.flag.txt.enc', 'rb').read()



def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "691d"):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_1_pw_check()

dnightshade-picoctf@webshell:~$ python level1.py
Please enter correct password for flag: 691d
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_56891419}

```

## Bandera
picoCTF{545h_r1ng1ng_56891419}
## Notas Adicionales

## Referencias
