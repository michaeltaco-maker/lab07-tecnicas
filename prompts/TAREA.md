# Tarea: Mi prompt avanzado 

Mi prompt avanzado

## Tarea elegida 

Explicar un error de compilación

## Version 1: prompt basico 

```text
¿Por qué me sale este error en Java y cómo lo arreglo?
String texto;
System.out.println(texto.length());
```
Qué técnica se agregó: Ninguna (Prompt directo / básico).

Por qué: Sirve como punto de partida para evaluar la respuesta predeterminada del modelo sin contexto adicional.

Qué mejoró en la respuesta: La respuesta entregó una explicación técnica directa sobre el compilador de Java y propuso 3 opciones de solución (asignar valor, cadena vacía o null con validación). Sin embargo, carecía de estructura pedagógica y usaba un lenguaje muy técnico para un alumno principiante.

## Version 2 

```text
Actúa como un profesor de programación en Java paciente y didáctico.
Explica el error del siguiente código dividiendo tu respuesta en los siguientes pasos:
1. Identifica en qué línea ocurre el error y qué significa exactamente.
2. Explica la causa raíz del problema para un estudiante principiante.
3. Proporciona el código corregido con una breve explicación del cambio.

Código:
String texto;
System.out.println(texto.length());
```
Qué técnica se agregó: Role Prompting y Descomposición.

Por qué: Para guiar al modelo a tomar una postura docente y estructurar la respuesta paso a paso desde el problema hasta la solución.

Qué mejoró en la respuesta: El tono cambió a uno mucho más amigable e inclusivo ("¡Hola! Con mucho gusto..."). La respuesta se organizó claramente en los 3 pasos solicitados: ubicación del error en la línea 2, causa raíz conceptual de la variable vacía en memoria y el código corregido con su respectiva explicación.

## Version 3: prompt final 

```text
Actúa como un profesor de programación en Java para alumnos de primer semestre.

Tu objetivo es diagnosticar, explicar y enseñar a solucionar un error de compilación/ejecución común en Java.

1. Explica el significado del error y señala la línea exacta donde ocurre.
2. Explica la causa raíz usando una analogía sencilla de la vida real.
3. Muestra el código corregido.
4. Realiza una autocrítica de tu respuesta: evalúa qué malentendido o confusión frecuente suelen tener los principiantes sobre las variables no inicializadas y agrégalo al final bajo la etiqueta "(Agregado en Autocrítica)".

Estructura tu respuesta en Markdown usando las siguientes secciones:
1. Diagnóstico del Error
2. ¿Por qué ocurre? (Explicación sencilla)
3. Código Corregido
4. Malentendidos Comunes (Autocrítica)

[CÓDIGO A ANALIZAR]
String texto;
System.out.println(texto.length());
```
Qué técnica se agregó: Few-Shot / Ejemplo de Formato, Prompt Estructurado y Autocrítica.

Por qué: Para forzar una estructura de encabezados rígida en Markdown, incluir recursos didácticos (analogías) y obligar al modelo a evaluar qué conceptos suelen confundir más a los alumnos.

Qué mejoró en la respuesta: Logró un resultado altamente educativo: utilizó la analogía de la "caja vacía para llevar en un restaurante", incluyó la estructura completa de una clase Java en el código corregido y agregó la sección de autocrítica que aclaró temas clave como variables locales vs. atributos de clase y la diferencia entre null, "" y no inicializada.

## Tecnicas usadas en el prompt final 

| Parte del Prompt Final  | Técnica Aplicada |
|---------|-------------------------------|
| Actúa como un profesor de programación en Java para alumnos de primer semestre. | Role Prompting | 
| 1. Explica... 2. Causa raíz... 3. Código corregido... | Descomposición |
| 4. Realiza una autocrítica de tu respuesta... | Autocrítica | 
| Estructura tu respuesta en Markdown usando las siguientes secciones: ### 1... | Few-Shot / Ejemplo de Formato |
| [ROL Y CONTEXTO], [TAREA], [INSTRUCCIONES], [EJEMPLO DE FORMATO], [CÓDIGO] | Prompt Estructurado |


## Evaluacion del resultado 

| Qué revisar  | Cumple (Sí / No) |
|---------|-------------------------------|
| ¿Identifica la causa raíz del error? | SI | 
| ¿Muestra el código corregido funcional? ? | SI |
| ¿Usa un lenguaje didáctico según el rol? | SI | 
| ¿Indica qué aspectos agregó en la autocrítica? | SI |
| ¿La estructura es clara y fácil de leer? | SI |

## Por que elegi estas tecnicas

Elegí la combinación de Role Prompting, Descomposición, Prompt Estructurado, Few-Shot y Autocrítica porque en la enseñanza de programación el objetivo no es solo corregir el código, sino desarrollar pensamiento abstracto en el estudiante. El Role Prompting establece una postura empática y docente; la Descomposición desglosa el problema en pasos lógicos comprensibles; el Prompt Estructurado y el Few-Shot imponen una jerarquía visual clara basada en secciones Markdown; y finalmente, la Autocrítica es indispensable para abordar conceptos erróneos sutiles (como confundir null con una variable no declarada) que el modelo normalmente omitiría en un diagnóstico básico.