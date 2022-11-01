## Objetivo
In RSA d is a lot bigger than e, why don't we use d to encrypt instead of e? Connect with `nc jupiter.challenges.picoctf.org 57464`.

## Solucion
```bash
Python 3.10.5 (main, Jun  8 2022, 09:26:22) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> c = 25861239421820700466981385732041131228606163089119731467300837982578720857072118254839956178557671953219454179145323438095286390789167204372318923906066235522560678006513340316975777992473860621806885577355071852039745566858163489999207000716893941393361690454102094728602235667759968558688638556810206995930
>>> n = 89404554493309130666386711262945579149871714399672880195544212859936831103250843358482440109448093006032839656790192918994745418757994499798175684928983835933455321484967697884879578740816916950355906415288746993909992683841712926131132233756239932687981410866765444150714960330659843417025830222677478622091
>>> d = 38165787586543624954659215725520369682407814726942767737777750632199409856655764600763892563620997269172845187878896307348764706663295727922449320799825750953110708910234872420449284694887364429030967052575701122605086019289319582190590588055548458280118612632716908997474138335324132689002094771685029052825 
>>> m = pow(c,d,n)
>>> m
88233789673257225250866977474357962806785154639011261994411191832861340340329052522466068041936347178152177089495225977497460035895146070763211047845555867355318410750885193646144590447672130797461581821938239639190655369353327431100553441688756732079701374299269089762678495535659741489513659258771888049090
>>> long_to_bytes(88233789673257225250866977474357962806785154639011261994411191832861340340329052522466068041936347178152177089495225977497460035895146070763211047845555867355318410750885193646144590447672130797461581821938239639190655369353327431100553441688756732079701374299269089762678495535659741489513659258771888049090)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'long_to_bytes' is not defined
>>> from Crypto.Util.numbers import long_to_bytes
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ModuleNotFoundError: No module named 'Crypto.Util.numbers'
>>> from Crypto.Util.number import long_to_bytes
>>> long_to_bytes(88233789673257225250866977474357962806785154639011261994411191832861340340329052522466068041936347178152177089495225977497460035895146070763211047845555867355318410750885193646144590447672130797461581821938239639190655369353327431100553441688756732079701374299269089762678495535659741489513659258771888049090)
b'}\xa6*\x95\x1c\xdb\xd2=7\xf0|\x1fVnv\xb8\xc1+\r\xa6\xbf\x9aYD\xc5\xbb\x99\x91\xb5\x19|\xbc}\xb3\xba\xa1\xd0[[-AJ\x83:\x8eh\xb5_\xfeL\xd8\r\x065\xf2n\x06\x87\xa8<\x12\x08\xd3x\xb1#\xf2NXZw6\x01*,\xc4\xc2\xfe*\x96\x04/\xd7\xb4w3\x1eC*\x94\x9a\xa4\xf8\xd21\x87c\xee;y{+\xbc\xcb\x96\x00(L\x0b\xa3M:A0mb4\x0e\xf5B\x9ff\xdc2\xddv\x8b\xc2'
>>> e = 65537
>>> m = pow(c,e,n)
>>> long_to_bytes(m)
b'picoCTF{bad_1d3a5_2152720}'
>>> 


```
picoCTF{bad_1d3a5_2152720}
## Notas adicionales
![[Pasted image 20221030201229.png]]
## Referencias