# GraficosVectorialesSVG

Organización de código SVG:
<g>...</g>
Agrupa partes de nuestro código SVG de manera similar a un <div>, en HTML (son los layers). 
No tiene estilos visibles (no se le puede aplicar un fill y esperar que se pinte el fondo), 
pero los estilos que se le apliquen (fill, stroke, stroke-width...) afectan el contenido.
  
<defs>...</defs>
Contiene elementos que se definen, pero no se visualizan, al menos hasta que son
llamados en algún punto del SVG. Es el lugar habitual para indicar degradados,
patrones, máscaras, pero también path que se utilizarán más tarde de manera
combinada, como en un renderizado de texto sobre trazo.

<symbol id="..." viewBox="..."> </symbol>
Los símbolos son grupos de código reutilizable identificados con un id y que, de la
misma forma que con <defs>, no se visualizan en el mismo SVG si no son llamados
por otro elemento. Un <symbol> no necesita estar en un <defs>.
Un <symbol> puede tener su propio viewBox, lo cual lo hace perfecto para definir
iconos u otros elementos de manera independiente del <svg> donde se declaran. Eso
también permite que el <svg> donde se declaran tenga un display: none; si va
inline, dentro de una página HTML.
<use xlink:href="#idElemento" />
Permite reutilizar un elemento definido anteriormente (siempre y cuando esté
identificado con un id), sea éste un <symbol> o no. Se usa habitualmente en los
sistemas de iconos.

Consejos sobre exportación (Illustrator)
- Exporta en perfil SVG 1.1 (si lo pide, en las últimas versiones lo hace por defecto)
- No traces las fuentes (type: SVG) si puedes emplear una webfont
- No incrustes (embed) las imágenes, intenta gestionarlas como un recurso externo
- Indica que agrupe los estilos en un <style>
- Con un solo decimal debería ser suficiente precisión para la mayoría de dibujos

Plugin SVGO para Illustrator:
https://github.com/davidderaedt/SVG-NOW

Plugin SVGO para Sketch
https://github.com/BohemianCoding/svgo-compressor
