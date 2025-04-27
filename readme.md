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

## Iteración 5

El texto en español quedará oculto pero será visible cuando el usuario presione un icono de visualización y se debe indicar “ver en español”

El texto en español no estará disponible en la alternativa

El resultado mostrará siempre la opción correcta con su traducción al español y la opción de escuchar el sonido

## Iteración 6

Las alternativas mostrarán el texto en español cuando el mouse pase por encima de la opción

# Pido que me cree un prompt para poder generar juego en Firebase


Crea una aplicación web interactiva completa en un solo archivo HTML, utilizando Tailwind CSS y Font Awesome desde CDN, y JavaScript puro. La aplicación será un juego educativo sobre el cuerpo humano para niños de 8 años, con las siguientes características:

1.  **Estructura General:**
    * **Pantalla de Inicio:** Título "¡Aprende sobre tu Cuerpo!", texto introductorio, iconos decorativos (`fas fa-child`, `fas fa-heartbeat`, `fas fa-brain`) y botón "Empezar Juego".
    * **Pantalla de Juego:** Muestra el número de pregunta actual sobre el total (ej. "Pregunta 3 / 20"), la puntuación actual, el contenido interactivo de la pregunta y las opciones de respuesta.
    * **Pantalla Final:** Mensaje "¡Juego Terminado!", icono de trofeo (`fas fa-trophy`), puntuación final (Puntos / Total) y botón "Jugar de Nuevo".

2.  **Contenido Educativo:**
    * **Temas:** Huesos (Skull, Ribs, Spinal Column), Órganos (Heart, Lungs, Stomach, Brain), Articulaciones, Actividad Física.
    * **Preguntas:** 5 preguntas de opción múltiple por tema (20 en total). Utilizar la estructura de datos JSON proporcionada (ver punto 6).

3.  **Funcionalidad Detallada (Pantalla de Juego):**
    * **Visualización Principal:**
        * Mostrar un icono de Font Awesome grande (`fa_icon` del JSON; si es `null`, mostrar el `term` como texto).
        * Mostrar el término clave en inglés (`term`) seguido de un botón de audio (`fas fa-volume-up`) para escuchar su pronunciación (`pronunciation_term`) y un botón de ojo (`fas fa-eye`) para mostrar/ocultar la traducción al español (`term_translation`). La traducción estará oculta por defecto.
    * **Pregunta:**
        * Mostrar la pregunta en inglés (`question_en`) seguida de un botón de audio (`fas fa-volume-up`) para escucharla y un botón de ojo (`fas fa-eye`) para mostrar/ocultar la traducción al español (`question_es`). La traducción estará oculta por defecto.
    * **Opciones de Respuesta:**
        * Mostrar 4 botones con las opciones en inglés (`option.en`). Las opciones deben barajarse.
        * Al pasar el mouse (hover) sobre un botón de opción, debe aparecer debajo del texto en inglés la traducción al español (`option.es`) correspondiente a esa opción.
    * **Feedback:**
        * Al seleccionar una opción, deshabilitar todos los botones.
        * Marcar la opción seleccionada como correcta (verde) o incorrecta (rojo).
        * Mostrar un texto indicando "¡Correcto! 🎉" o "Incorrecto. La respuesta correcta es:".
        * Debajo de ese texto, mostrar *siempre* la respuesta correcta en inglés (`answer_en`) seguida de su traducción al español entre paréntesis y un botón de audio (`fas fa-volume-up`) para escuchar la pronunciación en inglés de la respuesta correcta.
    * **Navegación:** Botón "Siguiente Pregunta" que aparece tras responder. El botón "Jugar de Nuevo" reinicia el juego.
    * **Sin Ayuda:** No incluir ninguna funcionalidad de ayuda o pista.

4.  **Tecnología y Estilo:**
    * HTML semántico, Tailwind CSS para todo el estilo (diseño limpio, responsivo, bordes redondeados, colores específicos para feedback: verde `#dcfce7`, rojo `#fee2e2`).
    * Fuente 'Inter'.
    * Usar JavaScript para toda la lógica: barajar preguntas/opciones, manejar clics, actualizar UI, controlar visibilidad de traducciones, interactuar con Web Speech API (`speechSynthesis`, `en-US`) para todos los audios.
    * Incluir animaciones suaves de aparición (`fadeIn`).

5.  **Datos (Incrustar en JS):**
    * Utilizar la siguiente estructura de datos JSON para las preguntas (incluir las 20 preguntas completas):
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
            pronunciation_term: "Skull" // Pronunciación específica del término
          },
          // ... (resto de las 19 preguntas con su estructura completa)
        ]
        ```
    * El audio de la pregunta usará `question_en`. El audio de la respuesta correcta usará `answer_en`.

Genera el código completo y funcional en un único archivo HTML.