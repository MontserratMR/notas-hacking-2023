## Descripción
We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with `nc jupiter.challenges.picoctf.org 39894`.

## Pistas 
Flag is not in the usual flag format

## Solución
Nos conectamos al puerto y tenemos lo siguiente:
```
--------------------------------------------------------------------------
xmsplwja qclc ya bmgl dzwp - dlchgcsxb_ya_x_mecl_zwoufw_wpdzxpjbgc
--------------------------------------------------------------------------
ucjnccs ga jqclc nwa, wa y qwec wzlcwfb awyf amocnqclc, jqc umsf md jqc acw. ucayfca qmzfysp mgl qcwlja jmpcjqcl jqlmgpq zmsp vclymfa md acvwlwjyms, yj qwf jqc cddcxj md owkysp ga jmzclwsj md cwxq mjqcl'a bwlsawsf cecs xmseyxjymsa. jqc zwnbcljqc ucaj md mzf dczzmnaqwf, ucxwgac md qya owsb bcwla wsf owsb eyljgca, jqc mszb xgaqyms ms fcxk, wsf nwa zbysp ms jqc mszb lgp. jqc wxxmgsjwsj qwf ulmgpqj mgj wzlcwfb w umt md fmoysmca, wsf nwa jmbysp wlxqyjcxjglwzzb nyjq jqc umsca. owlzmn awj xlmaa-zcppcf lypqj wdj, zcwsysp wpwysaj jqc oyiics-owaj. qc qwf agskcs xqccka, w bczzmn xmovzctyms, w ajlwypqj uwxk, ws waxcjyx wavcxj, wsf, nyjq qya wloa flmvvcf, jqc vwzoa md qwsfa mgjnwlfa, lcacouzcf ws yfmz. jqc fylcxjml, awjyadycf jqc wsxqml qwf pmmf qmzf, owfc qya nwb wdj wsf awj fmns womspaj ga. nc ctxqwspcf w dcn nmlfa zwiyzb. wdjclnwlfa jqclc nwa ayzcsxc ms umwlf jqc bwxqj. dml amoc lcwams ml mjqcl nc fyf smj ucpys jqwj pwoc md fmoysmca. nc dczj ocfyjwjyec, wsf dyj dml smjqysp ugj vzwxyf ajwlysp. jqc fwb nwa csfysp ys w aclcsyjb md ajyzz wsf cthgyayjc ulyzzywsxc. jqc nwjcl aqmsc vwxydyxwzzb; jqc akb, nyjqmgj w avcxk, nwa w ucsyps yoocsayjb md gsajwyscf zypqj; jqc eclb oyaj ms jqc caact owlaq nwa zykc w pwgib wsf lwfywsj dwulyx, qgsp dlmo jqc nmmfcf lyaca yszwsf, wsf flwvysp jqc zmn aqmlca ys fywvqwsmga dmzfa. mszb jqc pzmmo jm jqc ncaj, ulmmfysp mecl jqc gvvcl lcwxqca, ucxwoc omlc amoulc ceclb oysgjc, wa yd wspclcf ub jqc wvvlmwxq md jqc ags.
```

- Con ayuda de una herramienta para resolver criptogramas (en este caso yo utilicé boxentriq), pegamos el texto proporcionado y seleccionamos el idioma inglés.
- Obtenemos lo siguiente:
```
congrats here is your flag frequency is c over lambda agflcgtyue between us there was as i have already said somewhere the bond of the sea besides holding our hearts together through long periods of separation it had the effect of making us tolerant of each other s yarnsand even convictions the lawyerthe best of old fellowshad because of his many years and many virtues the only cushion on deck and was lying on the only rug the accountant had brought out already a box of dominoes and was toying
```
- En el primer renglón podemos ver la bandera.

## Bandera
frequency_is_c_over_lambda_agflcgtyue

## Notas Adicionales
En criptografía, el cifrado por sustitución es un método de cifrado por el que unidades de texto plano son sustituidas con texto cifrado siguiendo un sistema regular; las "unidades" pueden ser una sola letra (el caso más común), pares de letras, tríos de letras, mezclas de lo anterior, entre otros. El receptor descifra el texto realizando la sustitución inversa.

Los cifrados por sustitución son comparables a los cifrados por transposición. En un cifrado por transposición, las unidades del texto plano son cambiadas usando una ordenación diferente y normalmente bastante compleja, pero las unidades en sí mismas no son modificadas. Por el contrario, en un cifrado por sustitución, las unidades del texto plano mantienen el mismo orden, lo que hace es sustituir las propias unidades del texto plano.

## Referencias
https://es.wikipedia.org/wiki/Cifrado_por_sustituci%C3%B3n

https://www.boxentriq.com/code-breaking/cryptogram