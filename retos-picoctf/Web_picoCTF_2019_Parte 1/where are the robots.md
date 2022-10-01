# where are the robots
## Objetivo
Can you find the robots? `https://jupiter.challenges.picoctf.org/problem/56830/` ([link](https://jupiter.challenges.picoctf.org/problem/56830/)) or http://jupiter.challenges.picoctf.org:56830

## Solucion
```bash
┌──(kali㉿kali)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/56830/                     <!doctype html>
<html>
  <head>
    <title>Welcome</title>
    <link href="https://fonts.googleapis.com/css?family=Monoton|Roboto" rel="stylesheet">
    <link rel="stylesheet" type="text/css" href="style.css">
  </head>

  <body>
    <div class="container">
      <header>
        <h1>Welcome</h1>
      </header>
      <div class="content">
        <p>Where are the robots?</p>
      </div>
      <footer></footer>
    </div>
  </body>
</html>

┌──(kali㉿kali)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/56830/robots.txt
User-agent: *
Disallow: /1bb4c.html

┌──(kali㉿kali)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/56830/robots.txt/1bb4c.html
User-agent: *
Disallow: /1bb4c.html

┌──(kali㉿kali)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/56830/1bb4c.html           <!doctype html>
<html>
  <head>
    <title>Where are the robots</title>
    <link href="https://fonts.googleapis.com/css?family=Monoton|Roboto" rel="stylesheet">
    <link rel="stylesheet" type="text/css" href="style.css">
  </head>
  <body>
    <div class="container">

      <div class="content">
        <p>Guess you found the robots<br />
          <flag>picoCTF{ca1cu1at1ng_Mach1n3s_1bb4c}</flag></p>
      </div>
      <footer></footer>
  </body>
</html>

┌──(kali㉿kali)-[~]
└─$  

```
picoCTF{ca1cu1at1ng_Mach1n3s_1bb4c}

## Notas adicionales

## Referencias