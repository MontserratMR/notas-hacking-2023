## Descripción
Can you break into this super secure portal?
https://jupiter.challenges.picoctf.org/problem/37821/

## Pistas 
Never trust the client

## Solución
El error es que el programador dejó el código de la validación de la contraseña del lado de cliente.
Al checar el código fuente podemos ver una función como la siguiente:
```
function verify() {

checkpass = document.getElementById("pass").value;

split = 4;

if (checkpass.substring(0, split) == 'pico') {

if (checkpass.substring(split*6, split*7) == 'a3c8') {

if (checkpass.substring(split, split*2) == 'CTF{') {

if (checkpass.substring(split*4, split*5) == 'ts_p') {

if (checkpass.substring(split*3, split*4) == 'lien') {

if (checkpass.substring(split*5, split*6) == 'lz_1') {

if (checkpass.substring(split*2, split*3) == 'no_c') {

if (checkpass.substring(split*7, split*8) == '9}') {

alert("Password Verified")
...

```
con la cual podemos nosotros mismos armar la bandera.

## Bandera
picoCTF{no_clients_plz_1a3c89}

## Notas Adicionales

## Referencias
[Client-side vs. Server-side](https://www.educative.io/answers/client-side-vs-server-side)