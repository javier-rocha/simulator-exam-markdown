# Simulador de Examen UNIR

Esta aplicación es una herramienta web autocontenida (funciona localmente sin servidor) diseñada para practicar exámenes tipo test a partir de archivos Markdown.

## Características

- **Ejecución Local**: No requiere instalación ni servidor web. Solo necesitas un navegador moderno.
- **Carga Dinámica**: Permite cargar múltiples archivos `.md` con preguntas desde tu ordenador.
- **Aleatoriedad**: Selecciona preguntas aleatorias del banco cargado según la cantidad deseada.
- **Resultados Inmediatos**: Muestra la puntuación y retroalimentación al finalizar.

## Cómo usar

1.  Descarga el archivo `simulator-exam-markdown.html` en tu ordenador.
2.  Abre el archivo HTML haciendo doble clic o arrastrándolo a tu navegador web (Chrome, Firefox, Edge, etc.).
3.  En la pantalla de inicio:
    *   Selecciona la cantidad de preguntas que deseas responder (5, 10, 15, 20, 30, 40).
    *   Haz clic en el botón **"📂 Cargar archivos .md locales"**.
    *   Selecciona uno o varios archivos `.md` que contengan las preguntas formateadas correctamente.
4.  Aparecerá una lista con los archivos cargados. Haz clic en el botón del archivo que quieras practicar para iniciar el examen.

## Formato de las Preguntas (Markdown)

Para que el simulador pueda leer las preguntas correctamente, los archivos `.md` deben seguir una estructura específica. El analizador (parser) busca patrones concretos para identificar el tema, el número de pregunta, el enunciado, las opciones y la respuesta correcta.

### Estructura requerida

Cada pregunta debe comenzar con un encabezado de nivel 3 (`###`) seguido estrictamente del formato `Tema X - Pregunta Y`.

```markdown
###Tema [Número] - Pregunta [Número]
[Enunciado de la pregunta]

- A. [Texto de la opción A]
- B. [Texto de la opción B]
- C. [Texto de la opción C]
- D. [Texto de la opción D]

**Respuesta correcta:** [Letra]

**Retroalimentación:** [Texto opcional de retroalimentación]

---
```

### Ejemplo Real

Copia y pega el siguiente contenido en un archivo de texto y guárdalo con extensión `.md` (ejemplo: `mi-examen.md`):

```markdown
###Tema 1 - Pregunta 1
¿Cuál es la definición más ajustada de proyecto?

- A. Un proyecto es un esfuerzo temporal realizado para producir un resultado.
- B. Un proyecto es un esfuerzo ilimitado en el tiempo realizado para producir un resultado.
- C. Un proyecto es un esfuerzo temporal realizado para producir un resultado dentro de un plazo y presupuesto establecido.
- D. Un proyecto es un esfuerzo temporal realizado para producir un resultado dentro de un plazo y presupuesto establecido, independientemente de la calidad obtenida.

**Respuesta correcta:** C

**Retroalimentación:** Un proyecto tiene un inicio y un fin definidos, y restricciones de alcance, tiempo y coste.

---

###Tema 1 - Pregunta 2
¿Qué elemento NO forma parte del triángulo de hierro?

- A. Alcance.
- B. Coste.
- C. Tiempo.
- D. Recursos Humanos.

**Respuesta correcta:** D

**Retroalimentación:** El triángulo de hierro tradicional consta de Alcance, Tiempo y Coste (o Calidad en algunas variantes), pero Recursos Humanos no es un vértice principal del modelo básico.

---
```

### Notas sobre el formato:
*   **Encabezado**: Debe ser exacto: `###Tema X - Pregunta Y`. El sistema usa esto para separar las preguntas.
*   **Opciones**: Deben ser listas con guiones seguidos de la letra, un punto y un espacio: `- A. Texto`.
*   **Respuesta**: Debe estar en negrita seguido de dos puntos: `**Respuesta correcta:** Letra`.
*   **Separador**: Se recomienda usar `---` entre preguntas para mayor legibilidad visual en editores de texto.