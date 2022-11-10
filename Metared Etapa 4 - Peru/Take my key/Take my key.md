# Take my key

## Objetivos
Suppose users Alice and Bob enter into a key agreement with p = 101 and g = 17. Suppose. Alice chooses x = 19 and Bob chooses y = 13. Determine the key they will share.


## Solución 
```bash
g^(x * y) mod p=14
```

## Notas adicionales 

Exite un metodo llamado algoritmo Deffie Hellman con la formula para resolver este problema 
https://es.wikipedia.org/wiki/Diffie-Hellman


https://protecciondatos-lopd.com/empresas/algoritmo-diffie-hellman/

Para dos partes _Alice_ y _Bob_, que intentan establecer una clave secreta, y un adversario _Mallory_, la versión básica es como sigue:

-   Se establecen un primo p {\displaystyle p} ![p](https://wikimedia.org/api/rest_v1/media/math/render/svg/81eac1e205430d1f40810df36a0edffdc367af36) y un generador g ∈ Z p ∗ {\displaystyle g\in \mathbf {Z} _{p}^{*}} ![g\in {\mathbf  {Z}}_{{p}}^{{*}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5fe0b1ae12a3a08332ba3b1255d518608fb7d811) ([3](https://es.wikipedia.org/wiki/Diffie-Hellman#cite_note-3)​). Estos son públicos, conocidos no solo por las partes _Alice_ y _Bob_ sino también por el adversario _Mallory_ .
-   _Alice_ escoge a ∈ Z p − 1 {\displaystyle a\in \mathbf {Z} _{p-1}} ![a\in {\mathbf  {Z}}_{{p-1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0a1710c4c3f013ec56df48236f2e44a9438c4571) al azar, calcula A = g a mod p {\displaystyle A=g^{a}\;{\bmod {\;}}p} ![A=g^{{a}}\;{\bmod  \;}p](https://wikimedia.org/api/rest_v1/media/math/render/svg/9a3e4d87e539867e6375524752bd4660f9ee6c8a) , y envía A {\displaystyle A} ![A](https://wikimedia.org/api/rest_v1/media/math/render/svg/7daff47fa58cdfd29dc333def748ff5fa4c923e3) a _Bob_
-   _Bob_ escoge b ∈ Z p − 1 {\displaystyle b\in \mathbf {Z} _{p-1}} ![b\in {\mathbf  {Z}}_{{p-1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6d594c70fe799f2c5b2c955f3a71d8204948f2a6) al azar, calcula B = g b mod p {\displaystyle B=g^{b}\;{\bmod {\;}}p} ![B=g^{{b}}\;{\bmod  \;}p](https://wikimedia.org/api/rest_v1/media/math/render/svg/d97a907f31083be2d6673549493ed62cff659d3f) , y envía B {\displaystyle B} ![B](https://wikimedia.org/api/rest_v1/media/math/render/svg/47136aad860d145f75f3eed3022df827cee94d7a) a _Alice_

Nótese que tanto A como B pueden calcular el valor K = g a ⋅ b mod p {\displaystyle K=g^{a\cdot b}\;{\bmod {\;}}p} ![K=g^{{a\cdot b}}\;{\bmod  \;}p](https://wikimedia.org/api/rest_v1/media/math/render/svg/6591046b7e66211cedebd29c66ebe8ef3f1b0ad5) . En efecto, lo podemos demostrar usando las [propiedades del grupo Z p ∗ {\displaystyle \mathbf {Z} _{p}^{*}} ![{\mathbf  {Z}}_{{p}}^{{*}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/29bbef70beb386889938b05f5049e1cf11d18a1b)](https://es.wikipedia.org/wiki/Aritm%C3%A9tica_modular#Clases_de_equivalencia_módulo_n "Aritmética modular") :