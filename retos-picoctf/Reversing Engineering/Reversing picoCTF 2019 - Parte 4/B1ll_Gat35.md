## Objetivo
Can you reverse this [Windows Binary](https://jupiter.challenges.picoctf.org/static/0ef5d0d6d552cd5e0bd60c2adbddaa94/win-exec-1.exe)?
## Solucion
```bash
uint __cdecl FUN_00407f60(char *param_1)

{

char *_Str;

size_t sVar1;

size_t sVar2;

local_8 UINT;

_Str = (char *)thunk_FUN_00407f40();

local_8 = 0;

while( true ) {

sVar1 = _strlen(param_1);

if(sVar1-1<=local_8){

devolverCONCAT31((int3)(sVar1-1>>8),1);

}

sVar1 = _strlen(param_1);

sVar2 = _strlen(_Str);

if(sVar1-1!=sVar2)break;

if (param_1[local_8] != _Str[local_8]) {

return (uint)(_Str + local_8) & 0xffffff00;

}

local_8 = local_8 + 1;

}

return sVar2 & 0xffffff00;

}
`thunk_FUN_00407f40()`parece obtener la clave. Esta función apunta a `thunkFUN_00407e30()`, que hace referencia a una variable global denominada`DAT_0047c280`con dirección`0x0047c280`. Los últimos 4 valores son el desplazamiento que queremos: `c280`.

A continuación, abrimos el programa en[Ollydbg](http://www.ollydbg.de/). Presioné "Ejecutar hasta volver (Ctrl + F9)" y escribí`1`en el programa. Luego, presioné "Pausar ejecución (F12)", presioné la tecla Enter y luego presioné "Ejecutar hasta regresar (Ctrl + F9)" hasta que apareció el mensaje para la tecla. Ahora hay dos opciones. Puede deshabilitar ASLR en el binario utilizando un método de[esta respuesta de StackOverflow](https://stackoverflow.com/questions/9560993/how-do-you-disable-aslr-address-space-layout-randomization-on-windows-7-x64)y luego presione CTRL + G y pegue el desplazamiento, `0xc280`, encontramos. Esto te llevará al valor de la clave. Sin embargo, la opción más fácil es simplemente usar las características de pasos de depuración y enumerar todas las cadenas

Para hacer la segunda opción, primero asegúrese de estar en el módulo win-exe (haga clic en "Mostrar ventana de módulos (Alt + E)" y elija`win-exe`para asegurarse) y luego`haga clic derecho en > Buscar > Todas las cadenas de texto referenciadas`como se muestra en la imagen a continuación.

Verá`que la clave es: 4253360`en`PUSH 0F3C280` (probablemente los dos primeros caracteres diferentes debido a ASLR)
Ahora simplemente escriba la tecla en el programa y presione enter para obtener la bandera. Asegúrese de ingresar`La clave es:` 4253360, no solo`4253360`

Input a number between 1 and 5 digits: 1

Initializing...

Enter the correct key to get the access codes: The key is: 4253360

Correct input. Printing flag: PICOCTF{These are the access codes to the vault: 1063340}

```

## Notas adicionales

## Referencias