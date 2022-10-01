# Insp3ct0r
## Objetivo
Kishor Balan tipped us off that the following code may need inspection: `https://jupiter.challenges.picoctf.org/problem/9670/` ([link](https://jupiter.challenges.picoctf.org/problem/9670/)) or http://jupiter.challenges.picoctf.org:9670

## Solucion
```bash
┌──(kali㉿kali)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/9670/

...
        <!-- Html is neat. Anyways have 1/3 of the flag: picoCTF{tru3_d3 -->
      </div>

    </div>

  </body>
</html>

┌──(kali㉿kali)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/9670/mycss.css
...
#tabintro { background-color: #ccc; }
#tababout { background-color: #ccc; }

/* You need CSS to make pretty pages. Heres part 2/3 of the flag: t3ct1ve_0r_ju5t */ 

┌──(kali㉿kali)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/9670/myjs.js

...
window.onload = function() {
    openTab('tabintro', this, '#222');
}

/* Javascript sure is neat. Anyways part 3/3 of the flag: _lucky?2e7b23e3} */

```
picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?2e7b23e3}

## Notas adicionales

## Referencias