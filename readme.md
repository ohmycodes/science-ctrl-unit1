# Prompt de creación

- Fueron 5 Iteraciones

## Prompt inicial
Crea un juego interactivo que permita a un niño de 8 años estudiar los siguientes temas, en inglés.

1. Huesos y su función: Skull, Ribs, Spinal Column
2. Órganos y su función: Heart, lungs, stomach, brain
3. Articulaciones y su función
4. La importancia de la actividad física 

Realizar 5 preguntas para cada punto mencionado anteriormente donde el niño pueda seleccionar la opción correcta.

Lo que debe contener el juego:
- Utiliza imágenes de las partes del cuerpo para hacerlo más interactivo 
- Agrega el audio para conocer como se pronuncia en inglés
- Agregar una opción de ayuda



## Iteración 1

Incorpora los siguientes cambios
- Debajo de la palabra o frase en inglés agrega un poco más pequeña la traducción en español, recuerda que es para alguien de 8 años
- Al mostrar el resultado, da la opción de escuchar un audio con la opción correcta lo que permitirá aprender su sonido

## Iteración 2

En la iteración anterior sólo agregó traducción al título de la pregunta, la traducción debe aparecer también en la pregunta y en las alternativas.

Al mostrar el resultado el audio debe corresponder a la alternativa correcta.

## Iteración 3

En el identificador question-image utiliza fontawesome.com icons para que sea más educativo, en caso de que no exista un icono se usa el alt text

Actualmente no está la opción de sonido cuando el usuario selecciona la opción correcta, por lo que se debe agregar

Además de agregar la puntuación se debe incluir el número de la pregunta en la que está actualmente el jugador

## Iteración 4

Quitar el elemento con identificador help-button

Agregar la opción de sonido a la pregunta

# Pido que me cree un prompt para poder generar juego en Firebase


Crea una aplicación web interactiva completa (HTML, Tailwind CSS, JavaScript) que funcione como un juego educativo sobre el cuerpo humano para un niño de 8 años. La aplicación debe incluir:

1.  **Pantallas:**
    * **Inicio:** Título "¡Aprende sobre tu Cuerpo!", texto introductorio, iconos decorativos (`fas fa-child`, `fas fa-heartbeat`, `fas fa-brain`) y botón "Empezar Juego".
    * **Juego:** Muestra el progreso (Pregunta X / Y), la puntuación, el contenido de la pregunta actual y las opciones.
    * **Final:** Mensaje "¡Juego Terminado!", icono de trofeo (`fas fa-trophy`), puntuación final (Puntos / Total) y botón "Jugar de Nuevo".

2.  **Contenido Educativo:**
    * **Temas:** Huesos (Skull, Ribs, Spinal Column), Órganos (Heart, Lungs, Stomach, Brain), Articulaciones, Importancia de la Actividad Física.
    * **Preguntas:** 5 preguntas de opción múltiple por tema (20 en total). Las preguntas, opciones y términos deben estar en inglés, con su respectiva traducción al español mostrada debajo o junto al texto en inglés.

3.  **Funcionalidad del Juego:**
    * **Visualización Pregunta:**
        * Mostrar un icono de Font Awesome relevante para el término/tema (usar `fa_icon` del JSON de datos; si es `null`, mostrar el `term` como texto de fallback).
        * Mostrar el término clave en inglés (grande) y su traducción al español (más pequeña) debajo.
        * Botón de audio (`fas fa-volume-up`) junto al término para escuchar su pronunciación en inglés (Web Speech API, `en-US`).
        * Mostrar la pregunta en inglés (semibold) y su traducción al español debajo.
        * Botón de audio (`fas fa-volume-up`) junto a la pregunta en inglés para escucharla.
    * **Opciones:** 4 botones de opción múltiple por pregunta, mostrando el texto en inglés (arriba) y la traducción al español (debajo). Las opciones deben barajarse cada vez.
    * **Respuesta y Feedback:**
        * Al seleccionar una opción, deshabilitar todos los botones.
        * Marcar la opción seleccionada como correcta (fondo verde claro, borde verde) o incorrecta (fondo rojo claro, borde rojo).
        * Si es incorrecta, marcar también la opción correcta en verde.
        * Mostrar texto de feedback ("¡Correcto! 🎉" o "Incorrecto. Era: [Respuesta EN] ([Respuesta ES])").
        * Mostrar un botón de audio (`fas fa-volume-up`) junto al feedback para escuchar la pronunciación de la *respuesta correcta* en inglés.
        * Actualizar la puntuación si la respuesta es correcta.
    * **Navegación:** Botón "Siguiente Pregunta" que aparece después de responder. Al final, el botón lleva a la pantalla final. El botón "Jugar de Nuevo" reinicia el juego barajando las preguntas.
    * **Sin Ayuda:** No incluir botón de ayuda ni funcionalidad de pista.

4.  **Tecnología y Estilo:**
    * Usar HTML semántico, Tailwind CSS para todo el estilo (diseño limpio, responsivo, bordes redondeados, colores definidos para feedback) y JavaScript para la lógica del juego y la interacción con la Web Speech API.
    * Cargar Tailwind CSS y Font Awesome desde CDN.
    * Usar la fuente 'Inter'.
    * Asegurar transiciones suaves y animaciones de aparición (`fadeIn`).

5.  **Datos (Incrustar directamente en el script JS):**
    * Utilizar la siguiente estructura de datos JSON para las preguntas (incluir las 20 preguntas completas de la versión final):
        ```json
        [
          {
            topic: "Bones",
            fa_icon: "fas fa-brain", // o null
            term: "Skull",
            term_translation: "Cráneo",
            question_en: "What is the main job of the Skull?",
            question_es: "¿Cuál es la función principal del Cráneo?",
            options: [
              { en: "Protect the brain", es: "Proteger el cerebro" },
              { en: "Help you breathe", es: "Ayudarte a respirar" },
              { en: "Pump blood", es: "Bombear sangre" },
              { en: "Digest food", es: "Digerir comida" }
            ],
            answer_en: "Protect the brain",
            pronunciation_term: "Skull" // Pronunciación del término
          },
          // ... (resto de las 19 preguntas)
        ]
        ```
    * La pronunciación para el audio de la respuesta correcta se tomará directamente del texto `answer_en`. La pronunciación para el audio de la pregunta se tomará de `question_en`.

Genera el código completo y funcional en un solo archivo HTML.