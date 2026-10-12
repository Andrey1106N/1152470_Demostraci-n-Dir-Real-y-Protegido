# 1152470_Demostraci-n-Dir-Real-y-Protegido
Laboratorio educativo para aprender segmentación x86: cálculo de direcciones en modo real y protegido, paso a paso, y reversing de descriptores de 64 bits.

Simulador interactivo para aprender cómo el procesador x86 traduce direcciones en modo real y en modo protegido, con un decodificador de descriptores de segmento (reversing).

Es una aplicación web estática: un solo archivo index.html, sin dependencias, sin servidor y sin instalación.




<img width="1913" height="955" alt="Captura de pantalla 2026-10-12 160435" src="https://github.com/user-attachments/assets/9e5189c3-d8df-4443-bc8e-f5bf0c6a5d96" />




Enlace:  https://andrey1106n.github.io/1152470_Demostraci-n-Dir-Real-y-Protegido/ 
Local: descarga index.html y ábrelo con doble clic en cualquier navegador moderno. Funciona sin conexión a internet.


## Ejemplos para probar

| Modo | Entrada | Resultado esperado |
|---|---|---|
| Real | `1A2B:0023` | `1A2D3h` |
| Real | `0000:0000` | `00000h` |
| Real | `FFFF:FFFF` | `10FFEFh` |
| Protegido | Descriptor `00CF9A000000FFFF`, selector `0008`, CS, offset `00001234` | `00001234h` (válida) |
| Protegido | Mismo descriptor, selector `0000` | Error: selector nulo |
| Protegido | Descriptor `00CF92000000FFFF`, selector `0010`, CS | Error: CS requiere un descriptor de código |
| Reversing | `0000000011001111100110100000000000000000000000001111111111111111` | Código plano, presente, DPL 0, G=1, D/B=1 |
| Reversing | Cualquier cadena de menos o más de 64 bits | Error de longitud |
