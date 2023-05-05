## Descripción
Can you get the flag?Go to this [website](http://saturn.picoctf.net:51108/) and see what you can discover.

## Pistas 
How is the password checked on this website?

## Solución
- Entramos a la página y tenemos que iniciar sesión a un "Portal Seguro de Clientes" con la nota de que sólo números y letras son permitidas para el nombre de usuario y la contraseña.
- Al inspeccionar el código no se muestra ningún archivo que parezca contener la bandera.
- Si intentamos entrar con una cuenta ficticia, nos lleva a una pantalla de **Log In Failed**, sin embargo, al volver tratar de inspeccionar el código ahora podemos ver un archivo .js llamado "login" con el siguiente código:
```
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}
```
- Entramos con nombre de usuario "admin" y contraseña "strongPassword098765" y obtenemos la bandera

## Bandera
picoCTF{j5_15_7r4n5p4r3n7_05df90c8}

