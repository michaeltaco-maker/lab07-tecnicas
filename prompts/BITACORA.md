# Bitacora de tecnicas avanzadas 

Laboratorio 07: Tecnicas Avanzadas de Prompting. 
Herramienta de IA usada: (GEMINI) 

## Ejercicio 2: Zero-shot, one-shot y few-shot 

| Tipo | Aciertos (de 5) | Formato de la respuesta | Todas con el mismo formato (Si/No) |
|------|-----------------|-------------------------|------------------------------------|
| Zero-shot | 5 | Etiqueta + explicación entre paréntesis | Sí |
| One-shot | 5 | Lista numerada con texto -> Etiqueta | Sí |
| Few-shot | 5 | Texto entre comillas -> Etiqueta | Sí |

## Ejercicio 3: Chain of Thought 

| Pedido | Respuesta de la IA | Muestra los pasos (Si/No) | Correcta (Si/No) |
|--------|--------------------|---------------------------|------------------|
| Directo | 318.60 | No | Sí |
| Paso a paso | Muestra la explicación detallada por pasos (Paso 1 al Paso 4) calculando el descuento, el IGV y la multiplicación por las 3 unidades, finalizando con S/ 318,60 | Sí | Sí |

## Ejercicio 4: Role prompting 

| Versión | Vocabulario (sencillo/técnico) | Usa ejemplos o código | A quién le sirve más |
|---------|-------------------------------|-----------------------|----------------------|
| A. Sin rol | Intermedio | Sí (Código Python) | Estudiantes de programación general o principiantes |
| B. Rol docente | Sencillo | Sí (Diagrama ASCII y Código Python) | Personas sin conocimientos previos de programación |
| C. Rol senior | Técnico | Sí (Código Java) | Programadores con experiencia o desarrolladores Java |

## Ejercicio 5: Descomposicion 

Paso 1:
    Qué entregó la IA: La lista de los 5 requisitos principales estructurados para un sistema de inventario en Java (gestión de catálogo, control de stock/alertas, módulo de ventas, persistencia de datos e interfaz gráfica).

Paso 2:
    Qué entregó la IA: El diseño del diagrama de clases en Java estructurado en arquitectura MVC, detallando atributos con tipos de datos y métodos por capa (Dominio, Servicios, DAO y Presentación).

Paso 3:
    Qué entregó la IA: La implementación en código Java de la clase Producto con sus atributos privados, constructores, métodos getters/setters y métodos de utilidad como requiereReabastecimiento() y toString().

Paso 4:
    Qué entregó la IA: Una revisión de código que propuso 3 mejoras concretas de diseño y robustez para la clase Producto: validación de invariantes con IllegalArgumentException, métodos de negocio explícitos (disminuirStock y aumentarStock), e implementación de equals() y hashCode() basados en la identidad del producto.

Comparación de resultados (Descomposición paso a paso vs. Pedido de una sola vez):

    Resultado:

        Pedido directo de una sola vez ("Crea un sistema de inventario para una tienda"): 

            Al recibir una instrucción tan general y abierta, la IA entregó una respuesta panorámica y teórica. Presentó tres opciones genéricas (plantilla de Excel/Sheets, modelo de base de datos SQL simplificado y recomendaciones de softwares comerciales POS/ERP) y terminó devolviendo la pregunta para saber con qué tecnología se quería trabajar. No generó código funcional en un lenguaje específico ni una solución completa y lista para usar.
            
        Estrategia de descomposición paso a paso: 

            Permitió guiarlas especificaciones hacia un lenguaje claro (Java) y una arquitectura definida (MVC). Esto derivó en la creación progresiva de la arquitectura de clases, la implementación completa del código fuente de la entidad Producto y su posterior optimización con buenas prácticas de software (validaciones de datos, métodos de negocio y manejo de igualdad de objetos).

## Ejercicio 6: Prompt estructurado y autocritica

| Qué revisar  | Cumple (Sí / No) |
|---------|-------------------------------|
| ¿Tiene las 4 columnas pedidas? | SI | 
| ¿Incluye el bloqueo después de 3 intentos? | SI |
| ¿Incluye casos con campos vacíos? | SI | 
| ¿Indica qué casos agregó en la autocrítica? | SI |
| ¿Hay algún caso repetido o que no tenga sentido? | NO |

```text 
"<rol>Actua como analista de pruebas de software.</rol> 
<contexto>Login web con correo y contrasena. La cuenta se bloquea 
despues de 3 intentos fallidos.</contexto> 
<tarea>Piensa paso a paso que puede fallar y escribe 6 casos de prueba.</tarea> <formato>Tabla con las columnas: ID, escenario, datos de entrada, 
resultado esperado.</formato>"
 y "Revisa tu tabla: faltan casos limite como campos vacios, correo sin @ o contrasena con espacios? Agrega los que falten e indica cuales agregaste." 
```
