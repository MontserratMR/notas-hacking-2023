## Descripción
I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/d3dd8cd51524d9fafcccd1b7d55f85e7/Forensics%20is%20fun.pptm)

## Pistas 
None
## Solución
- Con ayuda del visual code abrimos la carpeta con los contenidos descomprimidos del pptm que nos pasaron.
- ppt - slideMaster - hidden
- Viene un archivo en base54
```
Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q
```
- Lo decodificamos usando una herramienta como CyberChef y tenemos la bandera
- Dice "did you know ppts are zip" o "sabías que las presentaciones de PowerPoint son zip".
## Bandera
picoCTF{D1d_u_kn0w_ppts_r_z1p5}
## Notas Adicionales

## Referencias
https://gchq.github.io/CyberChef/