# Metared International CTF 2022

## Descripcion

For María’s art class the teacher ask for a MASTERPIECE that combains history and feelings, so María decided to créate a painting that describes an event in history close to her heart and her roots. She decided to paint a piece of Yucatán that everyone can relate to, so she paint the kukulkan pirámide. María says that she hide a Little message in the painting but I guess the teacher never find it because María got an F. Help María to pass de class, find the message and send it to the teacher:3


## Pistas (Si hay)



## Solución

``` Bash

La imagen como tal no contiene nada pero utilizando el comando strings obtenemos un texto en base64 al cual pasamos 8 veces por cyberchef con lo cual tenemos la llave la cual es:

flagMX{R3TURN_TH3_J4GUARS_EYES}

┌──(kali㉿kali)-[~/Metared International CTF 2022/Maria's Art Class]
└─$ strings KUKULKAN.jpeg | grep FLAG
_I LOVE FLAGS :3 
.MY FAVOURITE WORD IS FLAG 
THIS IS NOT THE FLAG, KEEP LOOKING BRO! 
/ FLAG Un PAso mas  BRO{Vm0weGQxTnRVWGxXYTFwUFZsZG9WRmxVU2xOalJsSlZVMnhPVlUxV2NEQlVWbEpUWVdzeFYxTnNhRmRpVkZaUVZrUktTMUl5VGtsaVJtUk9ZbTFvZVZadE1YcGxSbGw0Vkc1V2FsSnNXazlXYlRWRFYxWmFkR1JIUmxSTlZYQjVWR3hhYjFSc1duTmpSVGxhWWxoU1RGWnNXbUZXVmtaMFVteHdWMkpJUWpaV1ZFa3hWREZhV0ZOclpHcFNWR3hZV1ZSS1VrMUdWWGRYYlVacVZtdHdlbGRyV210VWJGcDFVV3R3VjJGcmJ6QlZla1pYVmpGa2NsWnNTbGRTTTAwMQ==}   x
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/Metared International CTF 2022/Maria's Art Class]
└─$ strings KUKULKAN.jpeg | grep FLAG
_I LOVE FLAGS :3 
.MY FAVOURITE WORD IS FLAG 
THIS IS NOT THE FLAG, KEEP LOOKING BRO! 
/ FLAG Un PAso mas  BRO{Vm0weGQxTnRVWGxXYTFwUFZsZG9WRmxVU2xOalJsSlZVMnhPVlUxV2NEQlVWbEpUWVdzeFYxTnNhRmRpVkZaUVZrUktTMUl5VGtsaVJtUk9ZbTFvZVZadE1YcGxSbGw0Vkc1V2FsSnNXazlXYlRWRFYxWmFkR1JIUmxSTlZYQjVWR3hhYjFSc1duTmpSVGxhWWxoU1RGWnNXbUZXVmtaMFVteHdWMkpJUWpaV1ZFa3hWREZhV0ZOclpHcFNWR3hZV1ZSS1VrMUdWWGRYYlVacVZtdHdlbGRyV210VWJGcDFVV3R3VjJGcmJ6QlZla1pYVmpGa2NsWnNTbGRTTTAwMQ==}   x


```

## Referencias