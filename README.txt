Se tomó la idea partiendo de la tarea programada para la semana en la semana algorimia (JavaScript), con la finalidad de cohecionar todas las clases. 

La tarea asignada fue crear una pagina, con código HTML-CSS,  al que le añadimos Boostrap, para trabajar en base a diseño. 

Tomando la idea, del motor del barrio, trabajamos en base a una biblioteca, el cual presta y vende libros. 

Se decidió empezar a establecer los parametros de la pagina, a través de Google, Gemini. ¿Por qué? 1. tiempo de respuesta 2. Devolución del códico para la descripción de la pagina. 

Así desarrollamos la primera semana de IA trayecto 2 Usar una propuesta de interfaz, que incluya IA trayendo la experiencia de usuario.  (genere interacción). 

Generando como Tarea o reto un Chat, en HTML al que uno le puede preguntar y el responder, limitando la respuesta unicamente al contenido que tiene la biblioteca ficticia creada. 

No conecta a la API, puede verse en el contenido dentro de la carpeta Biblioteca. 

Para seguir, en la semana de IA, se empezó a hablar del desarrollo de una IA, el cual se le debía de definir o establecer "limites y sesgos". 

Dejando los parametros como: " Hola, soy Minerva, una Inteligencia Artificial (IA) y NO estás hablando con una persona real. NO te pediré datos personales; solo atiendo solicitudes de esta página y nuestros libros (comparativas, puntuaciones y búsquedas personalizadas según tu interés). "

Este se termino grabando inicialmente como "const MINERVA_SYSTEM_INSTRUCTION = `
Aviso de Transparencia: Hola, soy Minerva, una Inteligencia Artificial (IA) y NO estás hablando con una persona real. NO te pediré datos personales; solo atiendo solicitudes de esta página y nuestros libros (comparativas, puntuaciones y búsquedas personalizadas según tu interés).

Reglas adicionales:
- Ayuda a descubrir libros de distintas partes, compartir reseñas, puntuaciones, comparativas y novedades.
- Recomienda libros según los gustos, géneros, ritmo o temas que el usuario mencione.
- Si el usuario ya tiene gustos o conversaciones previas registradas, apóyate en ellos de forma natural sin pedir datos personales sensibles.
- Mantén un tono amable, claro y centrado en literatura.
`;"


Pasamos a la maquetacióin de la pagina, esta se optimizó mediante un prompt y excalidraw 


Primer Prompt : una pagina web, en boostrap, se trata de una biblioteca.


Al ser ficticia, podemos poner un catalogo de 30 libros o mas, donde se pueda ver la portada del libro, la sinopsis, y un boton de adquirir.


Al darle a adquirir este despliega una segunda pagina, donde salen los botones, comprar, prestamo, y al darle a estos botones, salga la opción recoger en tienda o en punto fisico.


También crear una sección que se llame Cafe y lectura, donde se organiza un grupo de lectura, con un costo de $10.000 pesos la entrada, con una imagen background de gente leyendo o un grupo de lectura.


En el footer de la pagina, información de contacto, con dirección: Dirección: Cl. 16 #55-129, Guayabal, Medellín, Guayabal, Medellín, Antioquia , botones de whatsapp e instagram.


colores pastel, cremas, cafe claro, que insite a la calma.


Un boton desplegable de opciones por genero como: infantil, cultura, politica, mistico, religión, ciencia entre otros y que estos lleven a filtrar los libros mostrados. 

 ----- Respuesta: He creado la página web completa para Biblioteca Calma & Letras utilizando Bootstrap 5 y una paleta en tonos crema, beige suave y café claro. --- 

Prompt 2: Necesito agregar un boton flotante latelar de un chat, que al abrir el chat, este indique que es una IA, no esta hablando con una persona real y que indique no pedirá datos personales, solo atendará solicitudes de la pagina y los libros, comparativas, puntuación y busquedas personalizadas segun el interés . 

---- Respuesta: Novedades implementadas:

    Botón Flotante Lateral (Asistente IA): Ubicado fijo en el borde derecho de la pantalla con bordes redondeados y tonos café suave.

    Aviso de Transparencia y Privacidad: Tanto en la cabecera del chat como en el primer mensaje automático se indica claramente que:

        Es una Inteligencia Artificial (IA) y no una persona real.

        Nunca solicitará datos personales (nombres, teléfonos, correos o documentos).

        Atiende exclusivamente consultas sobre la página y el catálogo de 32 libros.

    Funciones Interactivas Conectadas al Catálogo:

        Puntuaciones: Cada libro cuenta con calificación en estrellas (4.6 a 5.0) visible tanto en las tarjetas del catálogo como al pedir los mejor valorados en el chat.

        Comparativas: Genera tablas comparativas lado a lado entre títulos del catálogo (por autor, género, puntuación, páginas y precio).

        Búsquedas por interés: Filtra y recomienda títulos según temas (naturaleza, calma, café, estrellas, filosofía, poesía, etc.) con acceso directo a la vista de adquisición. ---- 


Luego de manera interna al botón se le daría el nombre Minerva y sería marcado como "ZoNa Chat" para que este fuera facil de identificar en el codigo. 


De esta manera el chat, responde a preguntas basicas de la misma pagina, En cuanto a las preguntas que no entiende o no selecciona información de la pagina, repite constantemente la ultima pregunta. 


Para la Semana 2 Identificar impactos y responsabilidades asociados al diseño, despliegue y uso de sistemas de Inteligencia Artificial.

📦 Evidencia: Lista de decisiones de uso responsable aplicada al asistente.

Se habría cumplido con el reto inicial planteado, dado a que este ya daba información preventiva, y devuelve información acorde a lo solicido de la pagina.  

Quisimos darle mas apertura al chat, manteniendo sus restricciones, pero esta vez, recordando información y con posibilidad de busqueda no solo en la pagina, si no en google, para traer reseñas e información.  

Teniendo el Codgio pasamos a N8N para conectar la API , este nos devolvió los codigos bases, que se debía de implementar, con el Prompt 3 : 

You are helping build an interactive book chat assistant named Minerva for a fictional bookstore/literary website, integrated with the Google Gemini API.

Implement and enforce the following requirements:

1. Transparency Notice & Core Boundaries (System Instruction):
   - Always uphold this transparency notice: "Hello, I am Minerva, an Artificial Intelligence (AI) and you are NOT talking to a real person. I will NOT ask you for personal data; I only handle requests related to this page and our books (comparisons, ratings, and personalized searches based on your interests)."
   - Never ask for personal or sensitive information.
   - Keep responses focused on the website and books: book discovery across regions/sources, reviews, ratings, comparisons, new releases, and tailored recommendations.

2. Book Discovery, Reviews, Ratings & New Releases:
   - Use the Google Gemini API to retrieve book information, compare titles, share ratings and review summaries, and highlight new releases.
   - Enable or structure web search grounding / external lookup support where needed so recent releases and up-to-date book details can be retrieved accurately.
   - Keep Gemini API calls on a secure backend/server rather than exposing the API key in client-side code.

3. User Recognition, Last Conversation & Reading Preferences:
   - When a user enters their name or logs in, recognize them and restore their previous conversation history and stated reading preferences (such as favorite genres, authors, themes, pacing, or moods).
   - Store per-user profiles, conversation history, and reading preferences cleanly (e.g., in a database for production or structured local storage for prototyping), and pass prior conversation context into the Gemini API session so Minerva continues naturally from where they left off.

4. Personalized Recommendations:
   - Suggest books tailored to the tastes, genres, and interests the user shares or has previously saved, explaining why each recommendation fits what they like.

If I share my existing code asset next, integrate these features directly into my current project structure and explain any environment variables or setup steps needed.  ----- 

Devolviendo los codigos: const MINERVA_URL = 'https://calmayletras.app.n8n.cloud/webhook/minerva-chat';
async function minerva(payload) {
  const r = await fetch(MINERVA_URL, {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify(payload),
  });
  return r.json();
}
// Al iniciar sesión (usuario verificado):
//   const { profile, history } = await minerva({ username, display_name, action: 'load' });
//   -> pinta `history` en el chat; si hay historial, saluda retomando la conversación.
// Al enviar un mensaje:
//   const { reply, sources } = await minerva({ username, display_name, action: 'chat', message });


Este se implemetó pero daba error, dejando al chat respondiendo unicamente por los libros o preguntas claves, que devolvia el chat. 

Pasamos el codigo, por Lovable, en conjunto con la solicitud de la integración del chat, ya con la API diseñada y publicada de N8N y que a través del copiloto, este hiciera la integración adecuada y la publicación.  


https://minerva-cafe-library.lovable.app
