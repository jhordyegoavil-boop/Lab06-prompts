# Tarea: Mi prompt profesional
 
## Funcionalidad elegida

```text
Cálculo de Notas
``` 

## Version 1: prompt basico

```text
Actúa como un desarrollador experto en Python. Necesito que crees una función que reciba una lista de notas de un estudiante y calcule su promedio ponderado. La función debe retornar si el alumno aprobó o desaprobó considerando que la nota mínima de aprobación es 10.5. Devuelve solo el código de la función.
```
* **Qué cambió:** Ningún elemento previo, es el punto de partida básico.
* **Por qué:** Se lanzó una instrucción muy general y vaga esperando que la IA dedujera la lógica del negocio.
* **Qué mejoró en la respuesta:** La IA entregó un script de Python extremadamente genérico que solo sumaba y promediaba tres variables fijas. No contempla validaciones, manejo de peso de calificaciones ni interfaz de usuario.

 
## Version 2

```text
Actúa como un desarrollador experto en Python. Necesito que crees una función que reciba una lista de notas de un estudiante y calcule su promedio ponderado. La función debe retornar si el alumno aprobó o desaprobó considerando que la nota mínima de aprobación es 10.5. Devuelve solo el código de la función.
```
* **Qué cambió:** Se añadió un **Rol** claro ("desarrollador experto"), se especificó el **Contexto** y la lógica del negocio (promedio ponderado, nota mínima de 10.5) y se solicitó un **Formato** delimitado ("solo el código de la función").
* **Por qué:** Para evitar explicaciones teóricas innecesarias de la IA y asegurar que la lógica matemática del cálculo fuera la correcta según los estándares habituales de evaluación.
* **Qué mejoró en la respuesta:** El código entregado pasó a estar encapsulado en una función modular y limpia, ahorrando texto explicativo sobrante. Sin embargo, no maneja excepciones si la lista viene vacía ni procesa los datos en un formato de entrega visualmente cómodo para integrarse.

 
## Version 3: prompt final

```text
ROL
Actúa como un Ingeniero de Software de nivel Senior especialista en backend con Python.

INSTRUCCIÓN
Escribe un script modular en Python que calcule el promedio ponderado de un alumno. El script debe incluir una función principal que reciba un diccionario con las notas y sus respectivos pesos porcentuales. Debe validar que los pesos sumen exactamente 100% y que las notas estén en el rango de 0 a 20. Al final, debe determinar si el estado del alumno es "Aprobado" (nota mayor o igual a 10.5) o "Desaprobado".

CONTEXTO
Este script formará parte de un microservicio educativo local. El cálculo debe ser exacto y tolerantemente limpio frente a ingresos de datos erróneos.

RESTRICCIÓN
No uses librerías externas (como numpy o pandas). Resuelve todo utilizando únicamente las estructuras de datos nativas de Python.

EJEMPLOS
Ejemplo de entrada:
notas_usuario = {
    "Examen Parcial": {"nota": 12, "peso": 30},
    "Examen Final": {"nota": 15, "peso": 40},
    "Prácticas": {"nota": 11, "peso": 30}
}
Ejemplo de salida esperada:
{
    "promedio_final": 12.9,
    "estado": "Aprobado"
}

FORMATO
Devuelve la respuesta estructurada estrictamente en dos partes dentro de bloques de código separados:
1. El código de la solución completa en Python, debidamente documentado con docstrings.
2. Un bloque JSON de ejemplo que simule la salida de la función con los datos provistos.
No incluyas introducciones ni saludos antes del código.
```
* **Qué cambió:** Se integraron de forma explícita secciones delimitadas para los 5 componentes estructurales esenciales, se fijó una **Restricción** de arquitectura técnica estricta y se adjuntó un caso de **Ejemplo** (one-shot prompting).
* **Por qué:** Para garantizar la rigurosidad del código final, evitar sobrecarga de dependencias de terceros y estructurar el formato de salida para una integración automatizada directa.
* **Qué mejoró en la respuesta:** La IA generó un código robusto con bloques try-except, validación analítica de porcentajes y límites numéricos, entregando exactamente las estructuras esperadas sin texto informal decorativo.

---
 
## Componentes del prompt final

A continuación, se detalla cómo se distribuyen los cinco componentes requeridos dentro del prompt profesional configurado en la versión v3:

| Componente | Fragmento del Prompt Final |
| :--- | :--- |
| **Rol** | "Actúa como un Ingeniero de Software de nivel Senior especialista en backend con Python." |
| **Instrucción** | "Escribe un script modular en Python que calcule el promedio ponderado de un alumno. El script debe incluir una función principal que reciba un diccionario..." |
| **Contexto** | "Este script formará parte de un microservicio educativo local. El cálculo debe ser exacto y tolerantemente limpio..." |
| **Ejemplos** | Se incluyó la estructura de diccionario `notas_usuario` con pesos del 30%, 40%, 30% junto a la representación exacta de la salida esperada. |
| **Formato** | "Devuelve la respuesta estructurada estrictamente en dos partes dentro de bloques de código separados... 1. Código Python... 2. Bloque JSON..." |

---
 
## Evaluacion del resultado

| Criterio de Evaluación | Cumplimiento (Sí / No) | Observaciones |
| :--- | :--- | :--- |
| ¿El código funciona sin librerías externas? | **Sí** | Se resolvió usando solo diccionarios, bucles y condicionales nativos de Python. |
| ¿Valida correctamente que los pesos sumen 100%? | **Sí** | Lanza un error controlado (`ValueError`) si la suma de los porcentajes no es exacta. |
| ¿Separa el código Python del bloque JSON? | **Sí** | Organizó la respuesta estrictamente en los bloques Markdown independientes solicitados. |
| ¿Omitió introducciones informales y textos de relleno? | **Sí** | Inició directo con el código fuente técnico gracias a la instrucción explícita de formato. |

 
## Errores que evite

1. **Ambigüedad en las reglas de negocio (Ser demasiado general):** En la versión 1 la IA inventó las variables y la fórmula matemática. Se evitó en la versión final especificando los límites (rango 0-20, suma de pesos del 100% y nota de aprobación de 10.5).
2. **Generación de respuestas con texto basura (Falta de formato):** En las primeras iteraciones la IA añadía largas introducciones conversacionales ("¡Hola! Claro, aquí tienes el código..."). Se neutralizó en la versión final delimitando taxativamente los bloques de código y restringiendo explícitamente cualquier saludo inicial.

- [Tarea: mi prompt profesional](prompts/TAREA.md)
