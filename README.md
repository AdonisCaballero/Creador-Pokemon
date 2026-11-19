# Creador de Cartas de Pokémon

Pequeña web (un único archivo HTML, sin dependencias) para crear cartas de Pokémon personalizadas desde el navegador.

## Uso

1. Abre `CreadorPokemon.html` en tu navegador (doble clic).
2. Rellena el formulario: fase, nombre, puntos de vida, imagen, habilidades, debilidad y características.
3. Elige los dos colores del degradado de fondo de la carta.
4. Pulsa **Crear carta** y la carta aparecerá a la derecha (o debajo en móvil).

Los campos *Habilidad 2*, *Debilidad* y *Características* son opcionales; si los dejas vacíos no se muestran en la carta.

## Tecnologías

- HTML5
- CSS3 (flexbox y degradados)
- JavaScript (`FileReader` para previsualizar la imagen subida)

## Errores encontrados y sus soluciones

**Código inválido o incorrecto**
- **Degradado roto:** `linear-gradient (circle…)` tenía un espacio antes del paréntesis y `circle` no es válido en ese tipo de degradado, así que el navegador lo ignoraba. Se ha sustituido por un fondo semitransparente que sí funciona.
- **`font-style: bold`:** esa propiedad no admite `bold`. Se ha cambiado por `font-weight: bold`.
- **`<div>` sin cerrar:** la carta no cerraba correctamente su contenedor principal. Se ha corregido la estructura del HTML generado.
- **Etiqueta rota:** `for=" Caracteristicas"` tenía un espacio y no enlazaba con su campo. Ahora coincide con el `id`.

**Mala práctica**
- **IDs duplicados:** la carta reutilizaba los `id` del formulario (`nombre`, `ps-number`, `Habilidad`…). Se han eliminado de la carta, ya que un `id` debe ser único.
- **Posible inyección de HTML:** lo que se escribía en el formulario se insertaba tal cual con `innerHTML`. Ahora se escapa antes de mostrarlo.
- **Código sobrante:** se han quitado los scripts de estadísticas externos (estaban duplicados), el CSS que no se usaba y el estilo repetido de la carta.
- **Fondo dependiente de internet:** la imagen de fondo estaba enlazada desde otra web y podía dejar de cargar. Ahora el fondo es un degradado en CSS.

**Legibilidad y UX**
- **Texto demasiado pequeño:** había fuentes de 6 y 8 px. Ahora el texto más pequeño es de 11 px y los textos de la carta son oscuros sobre el color de fondo.
- **Formulario poco claro:** se han añadido placeholders, foco visible en los campos y colores por defecto.
- **Campos opcionales vacíos:** la habilidad 2, la debilidad y las características solo aparecen en la carta si se rellenan.
- **Pantalla inicial vacía:** ahora se muestra un mensaje que explica qué hacer.
- **Diseño no adaptable:** formulario y carta se colocan en columnas o en vertical según el ancho de la pantalla.

## Licencia

Proyecto educativo. Pokémon es una marca de Nintendo, Game Freak y Creatures Inc.; este proyecto no está afiliado a ellas.
