# Bitácora de prompts

**Laboratorio 06:** Fundamentos de Ingeniería de Prompts  
**Herramienta de IA usada:** ChatGPT

## Ejercicio 2: Tokens y ventana de contexto

### Conteo de tokens

| Texto                              | Caracteres | Tokens |
| ---------------------------------- | ---------: | -----: |
| Los estudiantes programan en Java. |         34 |      7 |
| The students program in Java.      |         30 |      7 |
| desafortunadamente                 |         18 |      4 |

### Prueba de contexto entre chats

En el mismo chat, la IA recordó que mi aplicación se llama TiendaTec y usa Java Swing. En un chat nuevo también respondió correctamente, aunque no repetí esos datos. Es probable que haya usado la función de memoria o información de conversaciones anteriores.

## Ejercicio 3: Temperatura

### Variabilidad en las respuestas del chat

Envié el mismo prompt en tres chats nuevos. Los dos primeros propusieron CampusLibro, BiblioPréstamo y LibroU. El tercero propuso BiblioCampus, PréstamoU y LibroConecta. Las respuestas pueden variar, aunque a veces tambien pueden llegar a repetirse.

### Resultados del simulador en Java

| Temperatura | % de BiblioTec | Nombres en los 5 intentos                             |
| ----------- | -------------: | ----------------------------------------------------- |
| 0           |        100.0 % | BiblioTec, BiblioTec, BiblioTec, BiblioTec, BiblioTec |
| 0.5         |         65.3 % | PrestaLibro, BiblioTec, BiblioTec, LibroYa, BiblioTec |
| 1           |         44.5 % | BiblioTec, LibroYa, LibroYa, PaginaLibre, BiblioTec   |
| 1.8         |         32.2 % | BiblioTec, NubeDeTinta, BiblioTec, BiblioTec, LibroYa |

Al subir la temperatura, BiblioTec perdió probabilidad y salieron nombres más variados. Al repetir 1.8, los porcentajes fueron iguales, pero cambiaron los nombres elegidos, ya que el simulador solo puede escoger nombres de su lista.

## Ejercicio 4: Prompt vago vs. estructurado

### Comparación de resultados

| Criterio                            | Prompt vago             | Prompt estructurado                             |
| ----------------------------------- | ----------------------- | ----------------------------------------------- |
| Menciona el objetivo del sistema    | No de forma clara       | Sí                                              |
| Menciona a los usuarios principales | Sí                      | Sí                                              |
| Tiene exactamente 3 funcionalidades | No                      | Sí                                              |
| Está en 3 párrafos                  | No                      | Sí                                              |
| ¿Lo usaría en un informe real?      | No, necesitaría ajustes | Sí, seria adecuado para una descripción inicial |

### Observación

El prompt vago dio una respuesta útil, pero generica. El estructurado indicó qué incluir y cómo presentarlo, por eso se ajustó mejor a lo solicitado.

## Ejercicio 5: Anatomía de un prompt

### Componentes del prompt final

| Componente  | Texto de mi prompt                                                                                   |
| ----------- | ---------------------------------------------------------------------------------------------------- |
| Rol         | Actua como desarrollador Java.                                                                       |
| Instrucción | Crea un programa en Java usando una clase Producto con los atributos codigo, nombre, precio y stock. |
| Contexto    | Para gestionar los productos de una tienda.                                                          |
| Ejemplo     | Usa este estilo para los metodos: getPrecio(), setPrecio(double precio).                             |
| Formato     | Explica primero la estructura de la clase y luego presenta el codigo Java.                           |

### Cambios observados por nivel

- **Nivel 1:** La IA creó un programa «Hola, mundo».
- **Nivel 2, rol:** También creó un «Hola, mundo»; el rol no le indicó qué debía hacer el programa.
- **Nivel 3, contexto:** Generó un programa para gestionar productos de una tienda.
- **Nivel 4, instrucción:** Incluyó la clase `Producto` con los atributos solicitados.
- **Nivel 5, formato:** Explicó la estructura de la clase antes de mostrar el código.
- **Ejemplo añadido:** Usó métodos con el estilo indicado, como `getPrecio()` y `setPrecio(double precio)`.

### Observación

El contexto convirtió un ejemplo genérico en un programa para la tienda. Las indicaciones siguientes precisaron la clase, el orden de la respuesta y el estilo de los métodos.

## Ejercicio 6: Del prompt básico al profesional

### Comparación inicial

El prompt básico produjo un login sencillo en Java Swing. El profesional generó una respuesta organizada en las clases `Main`, `LoginFrame` y `LoginService`.

### Evaluación del prompt profesional

| Qué revisar                                            | Cumple (Sí / No)                                                                                      |
| ------------------------------------------------------ | ----------------------------------------------------------------------------------------------------- |
| ¿Está escrito en Java y usa Swing?                     | Sí                                                                                                    |
| ¿Pide correo y contraseña?                             | Sí                                                                                                    |
| ¿Explica el funcionamiento antes o después del código? | Sí, antes del código                                                                                  |
| ¿El código está organizado en clases?                  | Sí                                                                                                    |
| ¿Valida los datos que ingresa el usuario?              | Sí, compara las credenciales; todavía no valida el formato del correo ni la longitud de la contraseña |

### Iteración

Pedí la mejora en el mismo chat. La nueva respuesta añadió la comprobación de `@`, una contraseña de al menos 8 caracteres y mensajes con `JOptionPane`. No ejecuté el código, solo registré lo que mostró la IA.

### Prompt profesional y mejora enviados

```text
Actua como desarrollador Java. Crea un ejemplo de login para una aplicacion de escritorio utilizando Swing. El usuario debe ingresar correo y contrasena. Explica brevemente el funcionamiento y presenta el codigo organizado por clases.

Mejora el codigo anterior con estas restricciones: no uses librerias externas, valida que el correo contenga @ y que la contrasena tenga al menos 8 caracteres, y muestra los mensajes con JOptionPane.
```
