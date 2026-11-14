# Valentina Duarte · Humano digital

Pastelera ficticia de 32 años, de El Colorado, Formosa. Tiene su pastelería artesanal «Dulces Ideas», usa inteligencia artificial en su trabajo y está aprendiendo, a los golpes, que no todo lo técnicamente posible es éticamente correcto.

Es un personaje 3D que conversa por voz con estudiantes de Nivel Terciario. Explica temas de pastelería, inteligencia artificial y ética, cuenta su caso y responde preguntas. La figura mueve la boca con lo que dice, parpadea, mira, gesticula y se puede girar 360°.

> **Personaje ficticio.** No representa a ninguna persona real. Está pensada para trabajar en el aula, por ejemplo en un juicio simulado sobre el uso de datos personales.

## Qué hay en este paquete

| Archivo | Para qué sirve |
| --- | --- |
| `index.html` | La página completa (figura 3D, interfaz y conexión con el agente). Es lo único que se publica. |
| `README.md` | Esta guía. |
| `base-de-conocimiento.txt` | Lo que sabe el agente, con cada dato marcado como `DOCUMENTADO`, `ATRIBUIDO` o `GENERAL`. Es de consulta; no hace falta subirlo a la web. |
| `prompt-del-agente.txt` | Las instrucciones del agente, para consulta o para recrearlo. |

## Publicarla en GitHub Pages

1. Entrá a [github.com](https://github.com) y creá un repositorio **público** (por ejemplo `valentina`).
2. Tocá **Add file → Upload files** y arrastrá `index.html` y `README.md` (si querés, también los dos `.txt`). Tocá **Commit changes**.
3. Andá a **Settings → Pages**. En *Build and deployment* elegí **Deploy from a branch**, la rama **main** y la carpeta **/ (root)**. Tocá **Save**.
4. Esperá uno o dos minutos y abrí `https://TU_USUARIO.github.io/NOMBRE_DEL_REPO/`.
5. Tocá **Hablar** y permití el micrófono cuando el navegador lo pida.

Para actualizarla, subí un `index.html` nuevo con el mismo nombre.

## Cómo se usa

- **Hablar:** conversás con voz. También podés escribirle una pregunta.
- **Escucharlo sin conectarse:** una demostración con la voz del dispositivo, sin gastar créditos.
- **Arrastrar:** gira alrededor de la figura. **Rueda del mouse o pellizco:** acerca o aleja. **Dos dedos o botón derecho:** sube o baja la vista.
- **Ver la cara / Ver cuerpo completo:** cambia entre el plano entero y el primer plano, útil para mirar el movimiento de labios.
- **Volver al frente:** aparece cuando te alejás del encuadre inicial.
- **Teclado:** flechas para girar, `+` y `-` para acercar o alejar.

## El agente de voz (ElevenLabs)

- **ID del agente:** `agent_8201m7bgweakf5br4nfgxf0jxhwg`.
- **Tiene que ser público** para que la página pueda hablar con él: en ElevenLabs, en la pestaña *Security*, la autenticación va desactivada. Si usás una lista de dominios permitidos, agregá `TU_USUARIO.github.io`.
- **Voz:** «PAULA» (español argentino), de la biblioteca de voces. Si al probar suena otra voz, agregala a tu espacio: *Voices → Voice Library → PAULA → Add to my voices* y asignala en la pestaña *Voice* del agente.
- **Usar otro agente sin tocar el código:** `index.html?agente=TU_ID`.
- **Base de conocimiento y prompt:** están en los archivos `.txt`. Si cambiás el personaje, actualizalos también en ElevenLabs.

## Personalizar la figura

Al comienzo del `index.html` hay un bloque `const PERSONA = { ... }` con la apariencia: colores de piel, pelo, chaqueta, delantal (`delantal`), pantalón (`pantalon`) y calzado (`calzado`). Cambiando los códigos de color y guardando, la figura se actualiza.

Si tenés un modelo 3D propio en formato `.glb`, con esqueleto humanoide y expresiones faciales (por ejemplo `jawOpen`, `mouthFunnel`, `eyeBlinkLeft`), guardalo como `modelo.glb` junto al `index.html` y la página lo usa en lugar de la figura que trae.

## Importante antes de usarla

- **Necesita internet.** La voz viaja por ElevenLabs y la figura carga Three.js desde jsDelivr (`cdn.jsdelivr.net`). Si la red de tu institución bloquea ese dominio, la figura no se verá.
- **Abrila desde la dirección de GitHub Pages** o desde el archivo descargado en Chrome o Edge. La vista previa de archivos de otras aplicaciones suele bloquear las conexiones externas, y ahí no se ve.
- **Cada conversación consume créditos** de la cuenta de ElevenLabs.
- **Micrófono:** el navegador lo pide al tocar *Hablar*. Si lo bloqueaste, permitilo desde el candado de la barra de direcciones.
- **Privacidad:** el agente no pide datos personales y le avisa a quien conversa que no hace falta contárselos. Aun así, recomendá a los estudiantes no compartir datos propios ni de terceros en la conversación.
- **Contenido del personaje:** las referencias legales (Ley 25.326, Recomendación de la UNESCO sobre la ética de la IA de 2021) y los datos de pastelería que menciona son orientativos. Conviene verificarlos en las fuentes oficiales antes de usarlos como dato firme.

## Si algo no anda

| Problema | Qué hacer |
| --- | --- |
| Pantalla en blanco o sin figura | Abrila desde GitHub Pages, con internet, y probá en otra red por si bloquean `cdn.jsdelivr.net`. Verificá que el navegador tenga activada la aceleración por hardware. |
| Se ve solo el busto | Hubo un error al armar el cuerpo completo. Abrí la consola (F12) y buscá el aviso «No se pudo armar el cuerpo completo». |
| No responde al tocar *Hablar* | Revisá el permiso del micrófono, que el agente sea público y que haya créditos en ElevenLabs. |
| Suena una voz distinta | Agregá la voz PAULA a tu espacio de ElevenLabs, como se explica arriba. |
