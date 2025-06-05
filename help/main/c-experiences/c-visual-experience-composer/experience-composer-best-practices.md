---
keywords: compositor de experiencias visuales;prácticas recomendadas del compositor de experiencias visuales;limitaciones del compositor de experiencias visuales;advertencias del compositor de experiencias visuales;prácticas recomendadas del vec;vec
description: Conozca las prácticas recomendadas para que sus experiencias funcionen según lo esperado al utilizar el [!UICONTROL Visual Experience Composer] (VEC).
title: ¿Cuáles son las prácticas recomendadas y las limitaciones de [!UICONTROL Visual Experience Composer]?
feature: Visual Experience Composer (VEC)
exl-id: cf51bfec-d7fa-4ec1-a5dc-35edefefd3e4
source-git-commit: 1f2c6bbabf0158672e5f926ffdf9662637cd8416
workflow-type: tm+mt
source-wordcount: '2435'
ht-degree: 37%

---

# Prácticas recomendadas y limitaciones de [!UICONTROL Visual Experience Composer]

Para garantizar que sus experiencias funcionen según lo previsto, siga las prácticas recomendadas al usar el [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC). Tenga en cuenta las sugerencias y limitaciones clave para maximizar el rendimiento y evitar problemas comunes.

## Prácticas recomendadas   {#section_86CF28C99CFF40329E4CBAFE4DD78BB4}

Las siguientes son las prácticas recomendadas al utilizar el VEC:

### Coloque la referencia de at.js en la parte superior de la sección `<head>` de su página.

+++Ver detalles
Si también usa [!UICONTROL Visitor API Service], coloque el script de la API de visitante encima de at.js.

+++

### Puede habilitar [!UICONTROL Enhanced Experience Composer] en la cuenta (habilitada para todas las actividades creadas en la cuenta) o en el nivel de actividad individual.

+++Ver detalles
Para habilitar [!UICONTROL Enhanced Experience Composer] en el nivel de cuenta, haga clic en [!UICONTROL [!UICONTROL Administration] > [!UICONTROL Visual Experience Composer]] y, a continuación, coloque el conmutador [!UICONTROL Enable Enhanced Experience Composer] en la posición Activado.

Para habilitar [!UICONTROL Enhanced Experience Composer] en el nivel de actividad mientras se crea una actividad en [!UICONTROL Visual Experience Composer], haga clic en [!UICONTROL Configure > [!UICONTROL Page Delivery]] y, a continuación, coloque el conmutador [!UICONTROL Enable Enhanced Experience Composer] en la posición Activado.

+++

### Puede realizar una lista de permitidos de ciertas direcciones IP si [!UICONTROL Enhanced Experience Composer] no se carga en las páginas seguras del sitio.

+++Ver detalles
Los problemas al cargar [!UICONTROL Enhanced Experience Composer] se pueden resolver mediante la inclusión en la lista de permitidos de las siguientes direcciones IP. Estas direcciones IP son para [!DNL Adobe] servidores usados para el proxy [!UICONTROL Enhanced Experience Composer]. Solo se requieren para edición de actividades. Los visitantes del sitio no necesitan estas direcciones IP incluidas en la lista de permitidos.

Para obtener más información, consulte [El EEC no cargará una dirección URL de control de calidad interna a la que no se puede acceder desde una dirección IP pública](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md) en *Resolución de problemas relacionados con el Compositor de experiencias mejorado*.

+++

### Utilice ID únicos para los elementos de nivel superior y cualquier otro elemento que pueda ser un buen candidato para pruebas o segmentación. 

+++Detalles
Todo lo que se encuentre inmediatamente dentro del elemento de cuerpo debe tener un ID único. Si se insertan nuevos elementos en el cuerpo y el código se desplaza, al menos podrá reconocer fácilmente los elementos principales.

[!DNL Target] no requiere ID, pero el uso de ID aumenta la fiabilidad de las experiencias creadas con el compositor de experiencias. [!DNL Target] utiliza selectores CSS para modificar el contenido cuando se entrega la experiencia. Cuando edita una experiencia, [!UICONTROL Visual Experience Composer] ancla el selector al antecesor más cercano con un atributo de ID no nulo al elemento de HTML que se está modificando. Por ello, no se recomienda usar ningún mecanismo, ni siquiera las bibliotecas de JavaScript, que defina o modifique los atributos de ID de HTML. Aunque esos identificadores puedan estar disponibles para el compositor de experiencias visuales [!DNL Target] para la creación de actividades, si JavaScript modifica los identificadores, es posible que el identificador que se utilizó cuando se creó la experiencia no esté disponible cuando se ejecuta. Si un ID no está disponible, el selector anclado al ID presenta un error.

+++

### Asigne a las clases CSS nombres fáciles de identificar.

+++Detalles
Al editar clases CSS en [!DNL Visual Experience Composer], resulta útil facilitar la identificación de las clases mediante nombres de clase descriptivos. Esto le permite tener la certeza de que está modificando las clases CSS correctas y de que las páginas se mostrarán correctamente.

No utilice la propiedad `!important` de CSS al ocultar o eliminar elementos.

Si la propiedad CSS `!important` está presente, las reglas CSS del sitio anulan los cambios realizados por `target.js` durante la entrega.

+++

### Evite usar tablas HTML para los diseños de página.

+++Detalles
[!DNL Target] utiliza JavaScript para dar formato a una página. pero en JavaScript resulta difícil modificar los diseños basados en tablas. Además, los diseños basados en tablas pueden mostrarse de distintas maneras según el navegador. Para obtener los mejores resultados, use CSS para crear diseños de página.

+++

### Minimice el uso de iFrames.

+++Detalles
Se recomienda minimizar el uso de iFrames para simplificar la administración de páginas y pruebas. El Compositor de experiencias visuales puede aplicar algunas acciones dentro de un iFrame, pero algunas acciones, como el cambio de tamaño, no funcionan correctamente. Cuando las páginas usan varios iFrames, administrarlas y cambiar su tamaño resulta difícil. Por este motivo, probar páginas en las que se hace un uso intensivo de iFrames puede ser complicado.

+++

### Intente organizar todas las modificaciones dinámicas de DOM tan pronto como DOM esté listo.

+++Detalles
Si las modificaciones no se aplican antes de la aplicación de experiencia en `target.js`, la entrega de contenido podría romperse. Esto ocurre solamente cuando hay un cambio de DOM en la jerarquía de un elemento segmentado.

+++

### Utilice únicamente texto sin formato o una etiqueta de imagen en los elementos de anclaje.

+++Detalles
`<a>Anchor Text</a>`

O

`<a href=""> <img src=""> </img> </a>`

+++

### Evite los elementos de nivel de bloque dentro de un elemento en línea.

+++Detalles
Los elementos de nivel de bloque no deben utilizarse dentro de elementos en línea, como anclaje, extensión, etc. Si lo hace, los elementos en línea perderán su altura y anchura, por lo que es posible que la herramienta de superposición de [!UICONTROL Visual Experience Composer] no funcione según lo esperado.

+++

### No use la etiqueta de base en su sitio web para resolver la dirección URL y los vínculos.

+++Detalles
El VEC manipula el sitio web entre bastidores, utilizando un servidor proxy que actualiza los vínculos. Si añade una etiqueta de base, el navegador resolverá de nuevo las direcciones URL usadas por el servidor proxy y aparecerán dañadas.

+++

### Si utiliza la acción Editar HTML para manipular la estructura de DOM, podrían dañarse los selectores.

+++Detalles
Por ejemplo, si ha realizado dos acciones:

* Ha agregado una clase al Elemento 1
* Ha editado el HTML del Elemento 1

Cada cambio crea un nuevo elemento en el VEC. Como la segunda acción modifica al Elemento 1, si elimina el Elemento 1, la segunda acción ya no tiene nada para modificar. Por lo tanto, el cambio ya no funciona.

Es decir, si agrega un elemento con texto y luego en una acción separada edita ese elemento con otro texto, el editor de código muestra ambas acciones como elementos separados. Cuando editó el elemento, creó un nuevo elemento que modifica al original que usted creó, y que contiene el texto editado. Si luego elimina el elemento original, el texto editado no podrá encontrar el elemento editado y no se mostrará. El segundo elemento permanece en la lista de elementos, pero no afecta a la página porque el elemento al que cambia ya no existe.

Consulte [Selectores de elementos utilizados en [!UICONTROL Visual Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337).

+++

### Utilice las etiquetas `<b>` y `<i>` al aplicar estilo a los elementos de texto con el editor de texto enriquecido.

+++Detalles
* Use `<b>` en vez de `<strong>` para el texto en negrita.
* Use `<i>` en vez de `<em>` para el texto en cursiva.

Puede que los resultados de las etiquetas `<strong>` y `<em>` no sean los previstos.

+++

### Tenga cuidado al quitar campos de formulario.

+++Detalles
Algunos campos de formulario pueden ser obligatorios para el envío. Si quita esos campos, podría afectar a los envíos.

+++

### No incluya `mboxCreate` dentro de los scripts.

+++Detalles
Dado que `mboxCreate` usa `document.write`, no se recomienda incluir `mboxCreate` en los scripts. En cambio, use `mboxDefine` y `mboxUpdate` con el mismo fin.

+++

### No actualice ningún fragmento de HTML usando [!DNL Target] si requiere código de JavaScript para la inicialización.


+++Detalles
Cuando se realiza una acción (Editar HTML) en componentes de la página (como reguladores, carruseles, etc.), la entrega puede aparecer dañado. El VEC realiza la acción después de que JavaScript haya creado una instancia del componente de página.

No obstante, cuando el contenido de la página se entrega a los visitantes, la acción se aplica antes de que se cree la instancia del componente. Por este motivo, es posible que las funciones del componente fallen en el momento de la entrega. La funcionalidad depende del tipo de script usado en la página para definir el componente.

Que la entrega funcione bien la primera vez que la pruebe no garantiza que seguirá funcionando. Podría darse una condición de carrera.

* Si hay una condición de carrera, la entrega funciona de forma intermitente.
* Si no hay ninguna condición de carrera, la entrega siempre funciona.

Pruebe la página varias veces para asegurarse de que la entrega funciona bien.

+++

### No use una etiqueta de base en el sitio web para resolver la dirección URL y los vínculos.

+++Detalles
Cuando usa [!UICONTROL Enhanced Experience Composer], un servidor proxy manipula el sitio web entre bastidores y actualiza todas las direcciones URL de los vínculos para que funcionen en el proxy. Si agrega una etiqueta base, el explorador resuelve todas estas direcciones URL, por lo que parecen rotas.

+++

### El texto importante del sitio que se pueda usar para la segmentación debería conservarse en el código HTML dentro de un elemento.

+++Detalles
Por ejemplo, no puede segmentar el texto &quot;Shopping Cart&quot; (Carro de compras) en el VEC (Compositor de experiencias visuales) si su código es como este:

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

En este ejemplo, todo el elemento de anclaje se selecciona en el VEC, lo que afecta negativamente a otros elementos si se realiza el direccionamiento.

+++

### No use las variables `top` o `self` en el código JavaScript.

+++Detalles
Cuando [!UICONTROL Enhanced Experience Composer] está habilitado, el valor de las variables superiores y automáticas se actualiza para deshabilitar la eliminación de iframes. Use un encabezado de opciones de X-frame para añadir la eliminación de iframes en lugar de códigos personalizados de JavaScript.

+++

### Pruebe el sitio siempre si se añaden parámetros al cargar la página.

+++Detalles
Por ejemplo, para abrir `www.abc.com`, se usan los siguientes parámetros de URL:

`www.abc.com?mboxEdit=1&mboxDisable=1`

Estos parámetros habilitan la edición en un iframe.

Asegúrese de que el sitio web se carga según lo esperado después de añadir parámetros de este tipo.

+++

### Compruebe si la página se abre correctamente en un iframe.

+++Detalles
Desactive las técnicas de eliminación de iframes en el sitio web y compruebe si el sitio web se abre como se espera dentro de un iframe en una página ficticia. Por ejemplo:

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

+++

## Advertencias  {#section_A0436B7B85BA467FA9DE13A9A40E6A6E}

Tenga en cuenta las siguientes advertencias al usar [!UICONTROL Visual Experience Composer] para diseñar la actividad.

### La característica [!UICONTROL Move] no admite z-index.

+++Detalles
Dado que no hay ninguna funcionalidad z-index, el elemento movido no se puede mover encima de otro elemento. Consulte [Limitaciones](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721) para más detalles.

+++

### La reorganización de elementos afecta al rastreo de clics.

+++Detalles
Si se reorganiza un elemento marcado para el rastreo de clics, las rutas de los elementos reorganizados cambian. Como resultado, se realizará el seguimiento de los clics del elemento que hay en la ubicación donde estaba el elemento original antes de ser reorganizado.

Esto ocurre porque tanto el código para entregar el contenido de la actividad como el código para realizar el seguimiento de clics se incluyen en una parte de código que se entrega a la página. Si va a otra página y configura el rastreo de clics, el código de contenido de la actividad y el código de rastreo de clics se entregan a dicha página. Si la página de seguimiento de clics tiene una estructura de página similar a la de la página donde se ejecuta la prueba, el contenido de la prueba también podría aparecer en la página de seguimiento de clics.

+++

### Es posible que no se pueda insertar un elemento en un(a) `<div>` que sea un mbox.

+++Detalles
Si un mbox contiene una oferta, la inserción de un elemento puede aparecer como `insertBefore` y no como `insertAfter`, si el mbox se implementa incorrectamente.

+++

### Cuando edite un elemento principal y secundario, empiece por el principal.

+++Detalles
Si intercambia una acción de imagen por un elemento y luego edita el texto o HTML en su elemento principal, pueden producirse problemas de envío. El mejor flujo de trabajo es editar el elemento principal antes de cambiar la imagen en el secundario.

+++

### No se puede seleccionar un elemento de página que incluye un mbox como elemento secundario.

+++Detalles
Por ejemplo, si la página contiene:

```html
<div> 
  <div class="mboxDefault" > 
  </div>
  <script>mboxCreate('myMbox'); 
</div>`
```

El div externo no debe seleccionarse en una experiencia porque el mbox codificado en la página sigue realizando una llamada a [!DNL Target] y recibe una respuesta. Esta respuesta interfiere con la respuesta destinada al elemento de página más grande.

+++

### Las IP del proxy pueden bloquearse en el entorno de los clientes.

+++Detalles
Si usa [!UICONTROL Enhanced Experienced Composer] en un sitio que no está activo, como un entorno de ensayo, podría ver errores de acceso denegado y tiempos de espera si el sitio bloquea los RIP.

+++

## Limitaciones   {#section_F33C2EA27F2E417AA036BC199DD6C721}

Tenga en cuenta las siguientes limitaciones al trabajar con el VEC:

### Controlar la compatibilidad del VEC con [!DNL Chrome] cambios en la directiva de extensión. {#ext}

+++Detalles
Debido a las directivas de manifiesto [V3 actualizadas en Google Chrome](https://developer.chrome.com/docs/extensions/develop/migrate/what-is-mv3){target=_blank}, las extensiones ya no pueden modificar el DOM original antes de que el explorador lo analice. Como resultado, ciertos scripts de seguridad, como las implementaciones de eliminación de iframes, pueden bloquear la carga de páginas en el VEC.

Para garantizar la compatibilidad, estos scripts deben deshabilitarse de forma condicional cuando la página se cargue dentro del iframe [!DNL Target]. Este proceso se puede realizar de forma segura comprobando la presencia del objeto `window.adobeVecExtension`, que [!DNL Target] inserta durante la carga del VEC.

Los siguientes fragmentos de código son ejemplos de código de eliminación de iframes que pueden provocar que la página web no se cargue en el VEC:

`window.top.location = window.self.location;`

`top.location.href = self.location.href;`

Se puede utilizar una comprobación simple para comprobar si una página web está incrustada dentro de [!DNL Target]. A un fragmento de código le debería gustar esto:

```
if(!window.adobeVecExtension) {
    // additional security logic
}
```

+++

### No se puede mover un elemento fuera de un contenedor seguido de una propiedad CSS.

+++Detalles
Un elemento no se puede mover fuera de un contenedor que va seguido de una propiedad CSS.

+++

### No puede seleccionar el elemento [!UICONTROL Button] para reorganizar.

+++Detalles
[!UICONTROL Button] elementos no pueden seleccionarse directamente para su reorganización. Para habilitar la reorganización, coloque los botones dentro de un contenedor más grande.

+++

### Solo las ofertas de intercambio están disponibles en mboxes.

+++Detalles
No se permiten acciones como [!UICONTROL Edit Class] y [!UICONTROL Rearrange] dentro de un mbox.

+++

### No debe reorganizar y mover el mismo elemento.

+++Detalles
Si un elemento se ha movido a otra ubicación y selecciona el contenedor principal e intenta reorganizar los elementos secundarios, el elemento movido no se verá afectado y permanecerá donde está. Es posible que la reorganización no se muestre según lo esperado.

+++

### La acción [!UICONTROL Change Image] no funciona en una imagen de un carrusel.

+++Detalles
Si, por ejemplo, su página contiene un carrusel con seis imágenes y desea intercambiar una imagen por una segunda imagen del carrusel, la acción [!UICONTROL Change Image] no funciona.

La solución consiste en seleccionar el contenedor principal y utilizar la acción [!UICONTROL Edit HTML] para editar el HTML del carrusel y actualizar el origen de la imagen de la imagen deseada.

+++

### No se puede cambiar el tamaño de las imágenes en un mbox.

+++Detalles
Si intercambia una imagen en un elemento mbox y luego intenta cambiar el tamaño de la imagen según el tamaño del elemento mbox, no podrá hacerlo.

+++

### Después de intercambiar una imagen, no se puede seleccionar la acción [!UICONTROL Edit].

+++Detalles
Después de intercambiar la imagen, no se puede editar la dirección URL de Scene7.

+++

### Los elementos de HTML con un origen externo no se pueden editar.

+++Detalles
Por ejemplo: Vídeo, etiquetas de audio, incrustar, iFrames, fotogramas.

+++

### El rastreo de clics no funciona para elementos de anclaje que contienen cualquier otra cosa que no sea texto sin formato o etiquetas de imagen.

+++Detalles
Por ejemplo, el rastreo de clics no funciona si el elemento contiene JavaScript.

+++

### Las páginas deben aceptar parámetros de URL para que funcione el VEC.

+++Detalles
Algunos sitios eliminan cualquier parámetro de URL de sus páginas. Sin embargo, el VEC requiere esos parámetros.

+++

### Al utilizar un script como parte de HTML, las variables y funciones a las que se accede desde fuera se deben declarar en el área de nombres de la ventana.

+++Detalles
El script se ejecuta dentro del ámbito de `target.js` después de que se cargue la página. Por lo tanto, ninguna variable o función que se declare localmente será accesible desde fuera del bloque de scripts.

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

+++

### Al insertar una imagen de la biblioteca [!UICONTROL Content] (Scene7) y editar HTML, se interrumpe la dirección URL de la imagen.

+++Detalles
Añada un elemento de anclaje dentro del div &quot;customHeaderMessage&quot; con un texto cualquiera, en este ejemplo, &quot;Dummy text&quot;:

```html
<a href="#"> 
<span> Dummy text </span>
</a>
```

Seleccione este div con la acción [!UICONTROL Insert Element] para insertar una imagen como secundaria de este div con texto &quot;Dummy text&quot;.

Tras la inserción, el aspecto es este:

```html
<a href="#">  
<span> Dummy text </span> 
<img src=""> This is inserted Image. </img> 
</a>
```

Elimine la etiqueta span de “Dummy text”.

+++

### La acción `customCode` del VEC no funciona con [!DNL Internet Explorer] 8.

+++Detalles
Debido a las limitaciones de IE8 para administrar contenido de scripts, `target.js` no admite esta acción en IE8. Como solución alternativa, si la página contiene jQuery y está expuesto globalmente en el objeto window, `target.js` puede utilizar la acción `customCode`. Asegúrese de que `window.jQuery` y `window.jQuery.fn.prepend` estén definidos.

+++

### El rastreo de clics solo se admite en la página en la que se crean experiencias o en la página de redirección.

+++Detalles
Aunque el modo [!UICONTROL Browse] está disponible para el rastreo de clics en el VEC, el modo [!UICONTROL Browse] no se puede usar para agregar el rastreo de clics en una página.

+++
