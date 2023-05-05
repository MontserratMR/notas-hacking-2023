## Descripción
Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it. Download the data [here](https://artifacts.picoctf.net/c/125/anthem.flag.txt).

## Pistas 
Download the file and search for the flag based on the known prefix.

## Solución
- Si pasamos el archivo proporcionado por un cat, nos imprime un texto muy extenso. A simple vista tardaríamos mucho en encontrar la bandera.
```
┌──(kali㉿kali)-[~]
└─$ grep "pico"  anthem.flag.txt 
      we think that the men of picoCTF{gr3p_15_@w3s0m3_58f5c024}

```

## Bandera
picoCTF{gr3p_15_@w3s0m3_58f5c024}

## Notas Adicionales
Grep, in files management, is a command-line utility that can search and filter text using a common regular expression syntax. It is so ubiquitous that among developers, the verb “to grep” has emerged as a synonym for “to search.” The `grep` command is a useful tool for searching all occurrences of a search term in a selection of files, filtering a log file or stream, or as part of a script or chain of commands.

A basic `grep` command uses the following syntax:

```
grep "string" ~/threads.txt
```
## Referencias
https://www.linode.com/docs/guides/how-to-grep-for-text-in-files/