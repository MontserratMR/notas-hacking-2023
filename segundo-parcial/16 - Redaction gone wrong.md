## Descripción
Now you DON’T see me.This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?

## Pistas 
How can you be sure of the redaction?

## Solución

```
┌──(kali㉿kali)-[~]
└─$ pdftotext Financial_Report_for_ABC_Labs.pdf 
                                                                                            
┌──(kali㉿kali)-[~]
└─$ cat Financial_Report_for_ABC_Labs.txt
Financial Report for ABC Labs, Kigali, Rwanda for the year 2021.
Breakdown - Just painted over in MS word.

Cost Benefit Analysis
Credit Debit
This is not the flag, keep looking
Expenses from the
picoCTF{C4n_Y0u_S33_m3_fully}
Redacted document.

```

## Bandera
picoCTF{C4n_Y0u_S33_m3_fully}

## Notas Adicionales
**Pdftotext** converts Portable Document Format (PDF) files to plain text.

Pdftotext reads the PDF file, _PDF-file_, and writes a text file, _text-file_. If _text-file_ is not specified, pdftotext converts _file.pdf_ to _file.txt_. If _text-file_ is ´-’, the text is sent to stdout.

## Referencias
https://www.xpdfreader.com/pdftotext-man.html