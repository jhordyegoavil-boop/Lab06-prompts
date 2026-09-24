# Bitacora de prompts
 
Laboratorio 06: Fundamentos de Ingenieria de Prompts.
 
Herramienta de IA usada: (escribe aqui cual usaste)

La IA uso si recompila informacion por lo que al hacer la pregunta nuevamente este me mando cual es la aplicacion y la tecnologia.
 
## Ejercicio 2: Tokens y ventana de contexto

| Texto | Caracteres | Tokens |
|-------|------------|--------|
| Los estudiantes programan en java. | 8 | 35 |
| The students program in java. | 7 | 30 |
| Desafortunadamente | 4 | 18 |
 
## Ejercicio 3: Temperatura


| Temperatura | % de BiblioTec | Nombres en los 5 intentos |
|---|---|---|
| 0 | 100.0% | BiblioTec, BiblioTec, BiblioTec, BiblioTec, BiblioTec |
| 0.5 | 65.3% | BiblioTec, BiblioTec, BiblioTec, BiblioTec, BiblioTec |
| 1 | 44.5% | PrestaLibro, BiblioTec, BiblioTec, BiblioTec, LibroYa |
| 1.8 | 32.2% | PrestaLibro, NubeDeTinta, PaginaLibre, NubeDeTinta, LibroYa |

El simulador se vuelve más creativo y varía las opciones elegidas en los intentos, reduciendo el porcentaje del nombre principal.
 
## Ejercicio 4: Prompt vago vs estructurado
 

| Criterio | Prompt vago | Prompt estructurado |
| :--- | :---: | :---: |
| Menciona el objetivo del sistema | No | Sí |
| Menciona a los usuarios principales | No | Sí |
| Tiene exactamente 3 funcionalidades | No | Sí |
| Esta en 3 parrafos | No | Sí |
| Lo usaria en un informe real | No | Sí |


## Ejercicio 5: Anatomia de un prompt
 

| Componente | Texto de mi prompt |
| :--- | :--- |
| Rol | Actua como desarrollador Java. |
| Instruccion | Crea un programa en Java ... usando una clase Producto con los atributos codigo, nombre, precio y stock. |
| Contexto | para gestionar los productos de una tienda. |
| Ejemplo | Usa este estilo para los metodos: getPrecio(), setPrecio(double precio). |
| Formato | Explica primero la estructura de la clase y luego presenta el codigo Java. |


## Ejercicio 6: Del prompt basico al profesional


| Qué revisar | Cumple (Sí / No) |
| :--- | :--- |
| ¿Está escrito en Java y usa Swing? | Sí |
| ¿Pide correo y contraseña? | Sí |
| ¿Explica el funcionamiento antes o después del código? | Sí |
| ¿El código está organizado en clases? | Sí |
| ¿Valida los datos que ingresa el usuario? | Sí |

```text
Prompt Profesional:
Actua como desarrollador Java. Crea un ejemplo de login para una
aplicacion de escritorio utilizando Swing. El usuario debe ingresar
correo y contrasena. Explica brevemente el funcionamiento y presenta
el codigo organizado por clases.
```
```text
Prompt Mejora:
Mejora el codigo anterior con estas restricciones: no uses librerias
externas, valida que el correo contenga @ y que la contrasena tenga
al menos 8 caracteres, y muestra los mensajes con JOptionPane.
```
- [Bitacora de prompts](/BITACORA.md)

