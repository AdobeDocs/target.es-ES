---
keywords: compositor de experiencias visuales;prácticas recomendadas del compositor de experiencias visuales;limitaciones del compositor de experiencias visuales;advertencias del compositor de experiencias visuales;prácticas recomendadas del vec;vec
description: Estas prácticas recomendadas pueden contribuir a que las experiencias funcionen correctamente. También hay otras sugerencias y limitaciones que debe tener en cuenta al usar el Compositor de experiencias visuales (VEC) en Adobe Target.
title: Prácticas recomendadas y limitaciones del Compositor de experiencias visuales
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '2472'
ht-degree: 95%

---


# Prácticas recomendadas y limitaciones del Compositor de experiencias visuales

Estas prácticas recomendadas pueden contribuir a que las experiencias funcionen correctamente. También hay otras sugerencias y limitaciones que debe tener en cuenta al usar el Compositor de experiencias visuales (VEC) en [!DNL Adobe Target].

Aplicando estas prácticas recomendadas se reduce la probabilidad de encontrar problemas inesperados en las experiencias que diseñe.

## Prácticas recomendadas {#section_86CF28C99CFF40329E4CBAFE4DD78BB4}

**En la versión 57 y posteriores de mbox.js, y en at.js, coloque la referencia de mbox.js o at.js en la parte superior de la sección `<head>` de la página.**

Si también usa el servicio de API de visitante, coloque el script de la API de visitante encima de mbox.js o at.js.

**En versiones de mbox.js anteriores a la 57, coloque el código de mbox.js lo más abajo posible en la sección `<head>` de la página.**

Coloque el código mbox.js al final de la sección `<head>` sin ninguna declaración adicional después de él. De no hacerlo así, cualquier etiqueta de script o vínculo se moverá a la sección `<body>`.

**Puede habilitar el Compositor de experiencias mejorado en la cuenta (se habilitará en todas las actividades de la cuenta) o en cada actividad por separado.**

Para habilitar el Compositor de experiencias mejorado en el nivel de cuenta, haga clic en [!UICONTROL Administración > Compositor de experiencias visuales] y coloque el conmutador en la posición Activado.

Para habilitar el Compositor de experiencias mejorado en una actividad al crearla en el Compositor de experiencias visuales, haga clic en [!UICONTROL Configurar > Dirección URL] y coloque el conmutador en la posición Activado.

**Puede realizar listas de permitidos en determinadas direcciones IP si el Compositor de experiencias visuales mejorado no se carga en páginas seguras del sitio.**

Los problemas al cargar el Compositor de experiencias visuales mejorado se pueden resolver mediante la inclusión en la lista de permitidos de las siguientes direcciones IP. Estas direcciones IP son para el servidor de Adobe y se usan para el proxy del Compositor de experiencias mejoradas. Solo se requieren para edición de actividades. Los visitantes al sitio no necesitan que estas direcciones IP estén incluidas en la lista de permitidos.

Estados Unidos: 52.55.99.45, 54.80.158.92 y 54.204.197.253

Europa, Oriente Medio y África (EMEA): 52.51.238.221, 52.210.199.44 y 54.72.56.50

Asia-Pacífico (APAC): 52.193.67.35, 54.199.198.109 y 54.199.241.57

**Utilice ID únicos para los elementos de nivel superior y cualquier otro elemento que pueda ser un buen candidato para pruebas o segmentación.**

Cualquier cosa que haya dentro del elemento del cuerpo debe tener un ID único. Si se insertan nuevos elementos en el cuerpo y el código se desplaza, al menos podrá reconocer fácilmente los elementos principales.

Adobe Target no requiere el uso de ID, pero usarlos mejora la fiabilidad de las experiencias creadas con el Compositor de experiencias. Target usa selectores de CSS para modificar el contenido al entregar la experiencia. Cuando se modifica una experiencia, el Compositor de experiencias visuales ancla el selector en el antecesor más cercano con un atributo de ID distinto de nulo para el elemento HTML que se está modificando. Por ello, no se recomienda usar ningún mecanismo, ni siquiera las bibliotecas de JavaScript, que defina o modifique los atributos de ID de HTML. Aunque estos ID pueden estar disponibles para que el Compositor de experiencias de Target pueda crear actividades, si JavaScript modifica algún ID, el ID que se usó al crear la experiencia podría no estar disponible cuando se ejecute la experiencia. Si un ID no está disponible, el selector anclado al ID presenta un error.

**Asigne a las clases CSS nombres fáciles de identificar.**

Cuando se modifican clases CSS en el Compositor de experiencias visuales, resulta de gran ayuda que las clases se puedan identificar fácilmente gracias al uso de nombres de clase descriptivos. Esto le permite tener la certeza de que está modificando las clases CSS correctas y de que las páginas se mostrarán correctamente.

No utilice la propiedad `!important` de CSS al ocultar o eliminar elementos.

Si la propiedad 1!important1 de CSS está presente, las reglas CSS del sitio anularán los cambios realizados por target.js durante la entrega.

**Evite usar tablas HTML para los diseños de página.**

Target Standard y Premium usan JavaScript para dar formato a una página, pero en JavaScript resulta difícil modificar los diseños basados en tablas. Además, los diseños basados en tablas pueden mostrarse de distintas maneras según el navegador. Para obtener los mejores resultados, use CSS para crear diseños de página.

**Reduzca al máximo el uso de iFrames.**

Se recomienda reducir al máximo el uso de iFrames para simplificar la administración de las páginas y las pruebas. El Compositor de experiencias visuales puede aplicar algunas acciones dentro de un iFrame, pero hay determinadas acciones, como el cambio de tamaño, que no funcionan correctamente. Cuando las páginas usan varios iFrames, administrarlas y cambiar su tamaño resulta difícil. Por este motivo, probar páginas en las que se hace un uso intensivo de iFrames puede ser complicado.

**Intente organizar todas las modificaciones dinámicas de DOM tan pronto como DOM esté listo.**

Si no consigue aplicar las modificaciones antes de que target.js aplique la experiencia, la publicación de contenido podría verse dañada. Esto ocurre solamente cuando hay un cambio de DOM en la jerarquía de un elemento segmentado.

**Utilice únicamente texto sin formato o una etiqueta de imagen en los elementos de anclaje.**

`<a>Anchor Text</a>`

O

`<a href=""> <img src=""> </img> </a>`

**Evite los elementos de nivel de bloque dentro de un elemento en línea.**

Los elementos de nivel de bloque no deben usarse dentro de elementos en línea como anclaje, intervalo, etc. Si lo hace, provocará que los elementos en línea pierdan su alto y su ancho, y la herramienta de superposición del Compositor de experiencias visuales podría no funcionar correctamente.

**No use la etiqueta de base en su sitio web para resolver la dirección URL y los vínculos.**

El Compositor de experiencias visuales manipula el sitio web en segundo plano, utilizando un servidor proxy que actualiza los vínculos. Si añade una etiqueta de base, el navegador resolverá de nuevo las direcciones URL usadas por el servidor proxy y aparecerán dañadas.

**Si utiliza la acción Editar HTML para manipular la estructura de DOM, podrían dañarse los selectores.**

Por ejemplo, si ha realizado dos acciones:

* Ha agregado una clase al Elemento 1
* Ha editado el HTML del Elemento 1

Cada cambio crea un nuevo elemento en el Compositor de experiencias visuales. Como la segunda acción modifica al Elemento 1, si elimina el Elemento 1, la segunda acción ya no tiene nada para modificar. Por lo tanto, el cambio ya no funciona.

Es decir, si agrega un elemento con texto y luego en una acción separada edita ese elemento con otro texto, el editor de código muestra ambas acciones como elementos separados. Cuando editó el elemento, creó un nuevo elemento que modifica al original que usted creó, y que contiene el texto editado. Si luego elimina el elemento original, el texto editado no podrá encontrar el elemento editado y no se mostrará. El segundo elemento permanece en la lista de elementos, pero no afecta a la página porque el elemento al que cambia ya no existe.

Consulte [Selectores de elementos utilizados en el Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337).

**Use las etiquetas `<b>` y `<i>` cuando aplique estilo en los elementos de texto con el editor de texto enriquecido.**

* Use `<b>` en vez de `<strong>` para el texto en negrita.
* Use `<i>` en vez de `<em>` para el texto en cursiva.

Puede que los resultados de las etiquetas `<strong>` y `<em>` no sean los previstos.

**Tenga cuidado al quitar campos de formulario.**

Es posible que sea obligatorio enviar algunos campos de formulario. Si quita esos campos, podría afectar a los envíos.

**No incluya `mboxCreate` dentro de scripts.**

Como `mboxCreate` usa `document.write`, no se recomienda incluir `mboxCreate` en scripts. En cambio, use `mboxDefine` y `mboxUpdate` con el mismo fin.

**No actualice ningún fragmento html usando Target Standard si requiere código de JavaScript para la inicialización.**

Cuando se realiza una acción (Editar HTML) en los componentes de una página (como controles deslizantes, carruseles, etc.), la entrega puede aparecer como fallida. El Compositor de experiencias visuales lleva a cabo la acción una vez que JavaScript ha creado una instancia del componente de página.

No obstante, cuando el contenido de la página se entrega a los visitantes, la acción se aplica antes de que se cree la instancia del componente. Por este motivo, es posible que las funciones del componente fallen en el momento de la entrega. La funcionalidad depende del tipo de script usado en la página para definir el componente.

Que la entrega funcione bien la primera vez que la pruebe no garantiza que seguirá funcionando. Podría darse una condición de carrera.

* Si se da, la entrega funcionará de forma intermitente.
* Si no se da, siempre funcionará.

Pruebe la página varias veces para asegurarse de que la entrega funciona bien.

**No use una etiqueta de base en el sitio web para resolver la dirección URL y los vínculos.**

Cuando usa el Compositor de experiencias mejorado, un servidor proxy manipula el sitio web entre bastidores y se encarga de actualizar todas las URL de los vínculos para que funcionen en el proxy. Si añade una etiqueta de base, todas estas URL las resuelve el navegador, de modo que aparecen como si estuvieran dañadas.

**El texto importante del sitio que se pueda usar para la segmentación debería conservarse en el código HTML dentro de un elemento.**

Por ejemplo, no puede segmentar el texto “Shopping Cart” (Carro de compras) en el VEC (Compositor de experiencias visuales) si su código es como este:

```html
<a href="https://www.botanicchoice.com/shop.axd/Cart"> 
   <img alt="Shopping Cart"src="/images/ico-cart.gif"></img> 
   Shopping Cart: 
   <span id="HeaderCartQtyTotal">
      0 
  </span> 
  Items 
  <span id="HeaderCartPriceTotal"></span> 
</a>
```

En este ejemplo, el elemento de anclaje completo se selecciona en el VEC, lo cual afecta negativamente a otros elementos si se efectúa una segmentación.

**No use las variables `top` ni `self` en código JavaScript.**

Cuando el Compositor de experiencias mejorado está habilitado, el valor de las variables superiores y automáticas se actualiza para deshabilitar la eliminación de iframes. Use un encabezado de opciones de X-frame para añadir la eliminación de iframes en lugar de códigos personalizados de JavaScript.

**Pruebe el sitio siempre si se añaden parámetros al cargar la página.**

Por ejemplo, para abrir www.abc.com, se usan los parámetros de URL siguientes:

`www.abc.com?mboxEdit=1&mboxDisable=1`

Estos parámetros habilitan la edición en un iframe.

Asegúrese de que el sitio web se carga según lo esperado después de añadir parámetros de este tipo.

**Compruebe si la página se abre correctamente en un iframe.**

Desactive las técnicas de eliminación de iframes en el sitio web y compruebe si se abre correctamente dentro de un iframe en una página ficticia. Por ejemplo:

```html
<!DOCTYPE 
<html> 
<html> 
<head> 
  <meta charset="utf-8"> 
  <meta name="viewport" content="width=device-width"> 
  <title>JS Bin</title> 
</head> 
<body> 
  <iframe src="https://www.homedepot.com"</iframe> 
</body> 
</html>
```

## Advertencias {#section_A0436B7B85BA467FA9DE13A9A40E6A6E}

Tenga en cuenta las siguientes advertencias cuando use el Compositor de experiencias visuales para diseñar su actividad.

**La función de mover no admite z-index.**

Dado que no hay ninguna funcionalidad z-index, el elemento movido no se puede mover encima de otro elemento. Consulte [Limitaciones](/help/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721) para más detalles.

**La reorganización de elementos afecta al rastreo de clics.**

Si se reorganiza un elemento que está marcado para rastreo de clics, cambiarán las rutas de los elementos reorganizados. Como resultado, se realizará el seguimiento de los clics del elemento que hay en la ubicación donde estaba el elemento original antes de ser reorganizado.

Esto ocurre porque tanto el código para entregar el contenido de la actividad como el código para realizar el seguimiento de clics se incluyen en una parte de código que se entrega a la página. Si va a otra página y configura el rastreo de clics, el código de contenido de la actividad y el código de rastreo de clics se entregan a dicha página. Si la página de seguimiento de clics tiene una estructura de página similar a la de la página donde se ejecuta la prueba, el contenido de la prueba también podría aparecer en la página de seguimiento de clics.

**Es posible que no se pueda insertar un elemento en un `<div>` que sea un mbox.**

Si un mbox contiene una oferta y el mbox se implementa de forma incorrecta, la inserción de un elemento puede aparecer como insertBefore y no como insertAfter.

**Cuando edite un elemento principal y secundario, empiece por el principal.**

Si cambia la acción de una imagen en un elemento y después edita el texto o el código HTML en el elemento principal correspondiente, puede que se encuentre con problemas de entrega. El mejor flujo de trabajo es editar el elemento principal antes de cambiar la imagen en el secundario.

**No se puede seleccionar un elemento de página que incluye un mbox como elemento secundario.**

Por ejemplo, si la página contiene:

```html
<div> 
  <div class="mboxDefault" > 
  </div>
  <script>mboxCreate('myMbox'); 
</div>`
```

El div exterior no debe seleccionarse en una experiencia porque el mbox codificado de forma rígida en la página sigue haciendo una llamada a Target y recibe una respuesta. Esta respuesta interfiere con la respuesta destinada al elemento de página más grande.

**Las IP del proxy podrían bloquearse en el entorno de los clientes.**

Si usa el Compositor de experiencias mejorado en un sitio que no está activo, como un entorno de ensayo, podría ver errores de acceso denegado y tiempos de espera si el sitio bloquea los RIP.

**Al añadir varias páginas, el carril de la experiencia y el carril de la página se abren a la vez. Esto provoca una reducción en el ancho del Compositor de experiencias visuales para que se pueda mostrar el sitio en las optimizaciones. En consecuencia, los sitios ajustables pueden empezar a aparecer de forma distinta a la esperada en el espacio reducido.**

La solución es contraer el carril de la experiencia y el de la página haciendo clic en los iconos de los corchetes angulares izquierdos de la parte superior.

## Limitaciones {#section_F33C2EA27F2E417AA036BC199DD6C721}

**Función de mover**

Un elemento no se puede mover fuera de un contenedor que va seguido de una propiedad CSS.

**Solo las ofertas de intercambio están disponibles en mboxes.**

Las acciones como editar clase o reorganizar no están permitidas dentro de un mbox. El contenido de mbox se proporciona mediante mbox.js.

**No debe reorganizar y mover el mismo elemento.**

Si se ha movido un elemento a otra ubicación y selecciona el contenedor principal e intenta reorganizar los elementos secundarios, el elemento movido no se verá afectado y permanecerá donde está. Es posible que la reorganización no se muestre según lo esperado.

**La acción “Intercambiar imagen” no funciona en una imagen de un carrusel.**

Por ejemplo, si su página tiene un carrusel con seis imágenes y desea intercambiar una imagen por una segunda imagen del carrusel, la acción “Intercambiar imagen” no funcionará.

La solución es seleccionar el contenedor principal y usar la acción Editar HTML para modificar el HTML del carrusel y actualizar la fuente de la imagen deseada.

**No se puede cambiar el tamaño de las imágenes en un mbox.**

Si intercambia una imagen en un elemento mbox y luego intenta cambiar el tamaño de la imagen según el tamaño del elemento mbox, no podrá hacerlo.

**Después de intercambiar una imagen, no se puede seleccionar la acción Editar.**

Después de intercambiar una imagen, no se puede editar la dirección URL Scene7.

**No se pueden editar los elementos HTML con orígenes externos.**

Por ejemplo, las etiquetas HTML &lt;audio>, &lt;video>, &lt;embed>, &lt;iFrame> y &lt;frame>.

**El rastreo de clics no funciona para elementos de anclaje que contienen cualquier otra cosa que no sea texto sin formato o etiquetas de imagen.**

Por ejemplo, el rastreo de clics no funciona si el elemento contiene JavaScript.

**Las páginas deben aceptar parámetros de direcciones URL para que funcione el Compositor de experiencias visuales.**

Algunos sitios depuran todos los parámetros de direcciones URL para sus páginas. Sin embargo, el Compositor de experiencias visuales requiere esos parámetros.

**Al usar un script como parte del HTML, las variables y funciones a las que se accede desde fuera se deben declarar en el espacio de nombres de la ventana.**

El script se ejecuta dentro del ámbito de target.js después de cargarse la página. Por lo tanto, ninguna variable o función que se declare localmente será accesible desde fuera del bloque de scripts.

*Incorrecto:*

```html
<script> 
  var myVar = 123; 
  function myFunc() { 
    // 
  } 
</script>`
```

*Correcto:*

```html
<script> 
  window.myVar = 123; 
  window.myFunc = function() { 
    // 
  }; 
</script>
```

**Al insertar una imagen desde la biblioteca de contenido (Scene7) y editar el HTML, la dirección URL de la imagen se daña.**

Añada un elemento de anclaje dentro del div “customHeaderMessage” con un texto cualquiera, en este ejemplo, “Dummy text”:

```html
<a href="#"> 
<span> Dummy text </span>
</a>
```

Seleccione este div con la acción Insertar elemento para introducir una imagen como secundaria del div que contiene el texto “Dummy text”.

Tras la inserción, el aspecto es este:

```html
<a href="#">  
<span> Dummy text </span> 
<img src=""> This is inserted Image. </img> 
</a>
```

Elimine la etiqueta span de “Dummy text”.

**La acción customCode del Compositor de experiencias visuales no funciona con Internet Explorer 8.**

Debido a las limitaciones de IE8 para gestionar contenido de scripts, target.js no admite esta acción en IE8. La solución es que, si la página contiene jQuery y está expuesto globalmente en el objeto window, target.js puede entregar la acción customCode. Asegúrese de que window.jQuery es window.jQuery.fn.prepend están definidos.

**El rastreo de clics solo se admite en la página en la que se crean experiencias o en la página de redirección.**

Aunque el modo Examinar está disponible en Click Track VEC, no se puede usar para añadir el rastreo de clics en una página.
