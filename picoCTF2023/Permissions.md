## Objetivo
Can you read files in the root file?
Additional details will be available after launching your challenge instance.
## Pistas
What permissions do you have?
## Solucion
```
picoplayer@challenge:/$ ls
bin   challenge  etc   lib    lib64   media  opt   root  sbin  sys  usr
boot  dev        home  lib32  libx32  mnt    proc  run   srv   tmp  var
picoplayer@challenge:/$ cd sys
picoplayer@challenge:/sys$ ls
block  bus  class  dev  devices  firmware  fs  hypervisor  kernel  module  power
picoplayer@challenge:/sys$ cd ..
picoplayer@challenge:/$ cd challenge
picoplayer@challenge:/challenge$ ls
metadata.json
picoplayer@challenge:/challenge$ cat metadata.json 
{"flag": "picoCTF{uS1ng_v1m_3dit0r_89e9cf1a}", "username": "picoplayer", "password": "Sd9KYTm5kr"}picoplayer@challenge:/challenge$ Connection to saturn.picoctf.net closed by remote host.                      
Connection to saturn.picoctf.net closed.
```
## Notas Adicionales
|comando|descripcion|
|-------|-----------|
|xxx|xxx|
## Referencias