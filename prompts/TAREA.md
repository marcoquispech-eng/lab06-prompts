# Tarea: Mi prompt profesional

## Funcionalidad elegida

Registro de objetos perdidos en una aplicación de consola.

## Versión 1: prompt básico

```text
Crea un programa para registrar objetos perdidos.
```

**Resultado:** la IA creó un programa en Python con una base de datos SQLite y añadió funciones como cambiar el estado y eliminar objetos. Yo no había indicado el lenguaje, el almacenamiento ni esas funciones.

## Versión 2

```text
Mejora el programa anterior. Hazlo en Python para consola y enfócalo en registrar objetos perdidos de estudiantes. Incluye un menú para registrar, listar y buscar objetos. Para cada objeto guarda una descripción, el lugar y la fecha en que se perdió. Mantén los registros en una lista mientras se ejecuta el programa.
```

**Qué cambié y por qué:** precisé el lenguaje, los datos, las opciones del menú y cómo guardar los registros para evitar funciones y almacenamiento que no necesitaba.

**Qué mejoró:** la IA usó una lista de diccionarios en lugar de SQLite. El programa quedó más sencillo y su explicación me ayudó a entender cómo se guardan los objetos.

## Versión 3: prompt final

```text
Actúa como desarrollador de Python y docente para principiantes. Crea un programa de consola para registrar objetos perdidos de estudiantes. Debe tener un menú para registrar, listar, buscar objetos y salir. Guarda cada objeto en una lista de diccionarios con descripción, lugar y fecha; por ejemplo: descripción "Mochila negra", lugar "Biblioteca" y fecha "23/09/2026". Valida que los campos no estén vacíos y que la fecha tenga el formato DD/MM/AAAA. No uses librerías externas, archivos ni bases de datos. Explica brevemente cómo funciona la lista y después presenta el código completo en un solo bloque de Python.
```

**Qué cambié y por qué:** añadí un rol, un ejemplo, validaciones, restricciones y el orden de la respuesta para precisar el resultado.

**Qué mejoró:** la IA explicó la lista antes del código y agregó validaciones. El programa se ajustó mejor a lo solicitado, aunque no exige exactamente dos dígitos para el día y el mes. Revisé el código, pero no lo ejecuté.

## Componentes del prompt final

| Componente  | Texto de mi prompt final                                                                                                                           |
| ----------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| Rol         | Actúa como desarrollador de Python y docente para principiantes.                                                                                   |
| Instrucción | Debe tener un menú para registrar, listar, buscar objetos y salir. Guarda cada objeto en una lista de diccionarios con descripción, lugar y fecha; |
| Contexto    | Crea un programa de consola para registrar objetos perdidos de estudiantes.                                                                        |
| Ejemplo     | por ejemplo: descripción "Mochila negra", lugar "Biblioteca" y fecha "23/09/2026".                                                                 |
| Formato     | Explica brevemente cómo funciona la lista y después presenta el código completo en un solo bloque de Python.                                       |

## Evaluación del resultado

| Criterio                                            | ¿Cumple? | Observación                                  |
| --------------------------------------------------- | -------- | -------------------------------------------- |
| Está escrito en Python para consola                 | Sí       | Usa `input()` y un menú de texto.            |
| Permite registrar, listar y buscar objetos          | Sí       | Cada acción tiene su propia función.         |
| Guarda los objetos en una lista de diccionarios     | Sí       | Los agrega a `objetos_perdidos`.             |
| Evita campos vacíos y fechas inexistentes           | Sí       | Usa `pedir_campo()` y `datetime.strptime()`. |
| Exige exactamente DD/MM/AAAA                        | No       | Puede aceptar `1/1/2026`.                    |
| Evita archivos, bases de datos y librerías externas | Sí       | `datetime` es parte de Python.               |

## Errores que evité

- **Ser demasiado general:** en la versión 1 no indiqué el lenguaje ni cómo guardar los objetos. La IA eligió SQLite y añadió funciones que no necesitaba. En las siguientes versiones precisé esos requisitos.
- **No indicar el formato de la respuesta:** en el prompt final pedí una explicación breve antes del código y un solo bloque de Python. Así fue más fácil entender y revisar el resultado.
