---
keywords: compositor de experiencias visuales;prácticas recomendadas del compositor de experiencias visuales;limitaciones del compositor de experiencias visuales;advertencias del compositor de experiencias visuales;prácticas recomendadas del vec;vec
description: Conozca las prácticas recomendadas para que sus experiencias funcionen según lo esperado al usar el [!UICONTROL Compositor de experiencias visuales] (VEC).
title: ¿Cuáles son las prácticas recomendadas y limitaciones de [!UICONTROL Compositor de experiencias visuales]?
feature: Visual Experience Composer (VEC)
exl-id: cf51bfec-d7fa-4ec1-a5dc-35edefefd3e4
TQID: 'https://experienceleague.adobe.com/upZDSyuS9VqUmYskNXrlYazhwRHmZGBpSR-cR-qliRs'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '2420'
ht-degree: 7%
---
# Prácticas recomendadas y limitaciones de [!UICONTROL Compositor de experiencias visuales] {#vec-best-practices}

>[!BEGINSHADEBOX]

**En esta página:** Conozca las prácticas recomendadas, advertencias y limitaciones que debe tener en cuenta al crear experiencias en el **[!UICONTROL Compositor de experiencias visuales]** (VEC).

>[!ENDSHADEBOX]

Seguir estas prácticas ayuda a las experiencias creadas en [!DNL Adobe Target] **[!UICONTROL Compositor de experiencias visuales]** (VEC) a funcionar según lo previsto. Las advertencias y limitaciones describen comportamientos que pueden causar problemas comunes, por lo que conocerlos ayuda a evitar problemas y a mantener el rendimiento.

## Prácticas recomendadas {#best-practices}

Al utilizar el VEC, se aplican las siguientes prácticas.

### Habilitar [!UICONTROL Compositor de experiencias mejorado] {#enable-eec}

El **[!UICONTROL Compositor de experiencias mejorado]** se puede habilitar en la cuenta, lo cual lo habilita en todas las actividades creadas en la cuenta o en cada actividad por separado.

* **Nivel de cuenta:** Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Compositor de experiencias visuales]** y, a continuación, coloque el conmutador **[!UICONTROL Habilitar el compositor de experiencias mejorado]** en la posición Activado.
* **Nivel de actividad:** Al crear una actividad en el **[!UICONTROL Compositor de experiencias visuales]**, haga clic en **[!UICONTROL Configurar]** > **[!UICONTROL Entrega de páginas]** y, a continuación, active el conmutador **[!UICONTROL Habilitar el compositor de experiencias mejorado]** en la posición Activado.

### Configuración y carga de página

+++ Coloque la referencia de at.js en la parte superior de la sección `<head>` de la página.

Si también se usa el **[!UICONTROL servicio de API de visitante]**, coloque el script de la API de visitante encima de at.js.

+++

+++ Lista de permitidos direcciones IP si [!UICONTROL Enhanced Experience Composer] no se carga en páginas seguras del sitio.

La inclusión en la lista de permitidos de las direcciones IP de los servidores [!DNL Adobe] utilizados para el proxy **[!UICONTROL Enhanced Experience Composer]** resuelve los problemas de carga. Estas direcciones IP solo son necesarias para la edición de actividades. Los visitantes del sitio no los necesitan incluidos en la lista de permitidos. Las direcciones IP se enumeran en [El EEC no cargará una dirección URL de control de calidad interna a la que no se puede obtener acceso en direcciones IP públicas](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md#eec-ip-addresses) en *Resolución de problemas relacionados con el Compositor de experiencias mejorado*.

+++

+++ No utilice la etiqueta de base en el sitio web para resolver direcciones URL y vínculos.

El VEC, incluido el **[!UICONTROL Compositor de experiencias mejorado]**, manipula el sitio web entre bastidores a través de un servidor proxy que actualiza todas las URL de vínculos para que funcionen en el proxy. Si se añade una etiqueta base, el explorador resuelve estas direcciones URL de nuevo, por lo que parecen rotas.

+++

+++ No use las variables `top` o `self` en el código JavaScript.

Cuando el **[!UICONTROL Compositor de experiencias mejorado]** está habilitado, los valores de las variables `top` y `self` se actualizan para deshabilitar la eliminación de iframes. Utilice un encabezado Opciones de X-Frame para agregar la eliminación de iframes en lugar del código personalizado de JavaScript.

+++

+++ Pruebe siempre el sitio web si se añaden parámetros cuando se carga la página.

Por ejemplo, los siguientes parámetros de URL se usan para abrir `www.abc.com` y editarlo en un iframe:

`www.abc.com?mboxEdit=1&mboxDisable=1`

Asegúrese de que el sitio web se carga según lo esperado después de agregar parámetros como estos.

+++

+++ Asegúrese de que la página se abre según lo esperado en un iframe.

Desactive las técnicas de eliminación de iframes en el sitio web y compruebe si el sitio web se abre como se espera en un iframe en una página ficticia. Por ejemplo:

```html
<!DOCTYPE html>
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

### Marcado de página

+++ Utilice ID únicos para los elementos de nivel superior y para cualquier otro elemento que sea un buen candidato para pruebas o segmentación.

Todo lo que se encuentre inmediatamente dentro del elemento body debe tener un ID único, de modo que al menos los elementos principales sean fáciles de reconocer cuando se inserten nuevos elementos en el cuerpo y el código se mueva.

[!DNL Target] no requiere ID, pero los ID aumentan la fiabilidad de las experiencias creadas con el compositor de experiencias. [!DNL Target] utiliza selectores CSS para modificar el contenido cuando se entrega la experiencia. Cuando se edita una experiencia, **[!UICONTROL Compositor de experiencias visuales]** ancla el selector al antecesor más cercano del elemento de HTML modificado que tiene un atributo de ID no nulo. Por lo tanto, no es aconsejable utilizar ningún mecanismo, incluidas las bibliotecas de JavaScript, que establezca o modifique atributos de ID de HTML. Es posible que estos ID estén disponibles para el compositor de experiencias cuando se cree la actividad, pero si JavaScript los modifica, es posible que el ID utilizado durante la creación no esté disponible cuando se ejecute la experiencia. Si no hay ningún ID disponible, se produce un error en el selector anclado a dicho ID.

+++

+++ Utilice nombres de clase CSS descriptivos.

Los nombres de clase descriptivos facilitan la identificación de las clases cuando se editan en **[!UICONTROL Compositor de experiencias visuales]**. Esto ayuda a garantizar que se editan las clases CSS correctas y que las páginas aparecen según lo esperado.

+++

+++ No utilice la propiedad CSS `!important` al ocultar o quitar elementos.

Si la propiedad CSS `!important` está presente, las reglas CSS del sitio anulan los cambios que `target.js` realiza durante la entrega.

+++

+++ Evite las tablas de HTML para los diseños de página.

[!DNL Target] utiliza JavaScript para dar formato a una página, y los diseños basados en tablas son difíciles de modificar con JavaScript. Es posible que los diseños basados en tablas no se muestren igual en todos los exploradores. Para obtener los mejores resultados, use CSS para crear diseños de página.

+++

+++ Minimice el uso de iFrames.

Minimizar los iFrames simplifica la administración de páginas y pruebas. El **[!UICONTROL Compositor de experiencias visuales]** puede aplicar algunas acciones dentro de un iFrame, pero algunas acciones, como cambiar el tamaño, no funcionan correctamente. Las páginas que utilizan varios iFrames son difíciles de administrar y cambiar de tamaño, por lo que la prueba de páginas con muchos iFrames puede crear problemas.

+++

+++ Utilice únicamente texto sin formato o una etiqueta de imagen en los elementos de anclaje.

Un elemento de anclaje contiene texto sin formato:

`<a>Anchor Text</a>`

o una etiqueta de imagen:

`<a href=""> <img src=""> </img> </a>`

+++

+++ Evite los elementos de nivel de bloque dentro de un elemento en línea.

Los elementos de nivel de bloque no deben utilizarse dentro de elementos en línea, como elementos de anclaje y span. Si lo hace, los elementos en línea perderán altura y anchura, por lo que la herramienta de superposición de **[!UICONTROL Compositor de experiencias visuales]** podría no funcionar como se esperaba.

+++

+++ Tenga cuidado al quitar campos de formulario.

Algunos campos de formulario pueden ser obligatorios para el envío, por lo que eliminarlos podría afectar a los envíos.

+++

+++ Mantenga el texto importante que pueda utilizarse para la segmentación en el código HTML dentro de un elemento.

Por ejemplo, el texto &quot;Shopping Cart&quot; (Carro de compras) no puede estar dirigido en el VEC (Compositor de experiencias visuales) si el código es como el siguiente:

```html
<a href="https://www.botanicchoice.com/shop.axd/Cart">
   <img alt="Shopping Cart" src="/images/ico-cart.gif"></img>
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

### Edición y envío

+++ Organice todas las modificaciones dinámicas de DOM tan pronto como DOM esté listo.

Si las modificaciones no se aplican antes de que `target.js` aplique la experiencia, podría interrumpirse la entrega de contenido. Esto ocurre solamente cuando hay un cambio de DOM en la jerarquía de un elemento segmentado.

+++

+++ El uso de Editar HTML para manipular la estructura del DOM puede romper los selectores.

Por ejemplo, se realizan dos acciones:

* Se agrega una clase al elemento 1.
* Se edita el HTML del elemento 1.

Cada cambio crea un nuevo elemento en el VEC. La segunda acción modifica al Elemento 1, por lo que si se elimina el Elemento 1, la segunda acción ya no tiene nada que modificar y el cambio ya no funciona.

Del mismo modo, si se añade un elemento con texto y una acción independiente y, a continuación, edita ese elemento con texto diferente, el editor de código muestra ambas acciones como elementos independientes. La edición crea un nuevo elemento que modifica el original y contiene el texto editado. Si a continuación se elimina el elemento original, el texto editado no encontrará el elemento que desea modificar y no se mostrará. El segundo elemento permanece en la lista de elementos, pero no tiene efecto en la página porque el elemento al que cambia ya no existe.

Consulte [Selectores de elementos utilizados en el **[!UICONTROL Compositor de experiencias visuales]**](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#vec-selectors).

+++

+++ Utilice las etiquetas `<b>` y `<i>` al aplicar estilo a los elementos de texto con el editor de texto enriquecido.

* Use `<b>` en vez de `<strong>` para el texto en negrita.
* Use `<i>` en vez de `<em>` para el texto en cursiva.

Las etiquetas `<strong>` y `<em>` pueden producir resultados inesperados.

+++

+++ No incluya `mboxCreate` dentro de los scripts.

`mboxCreate` usa `document.write`, por lo que no se recomienda incluirlo en scripts. Use `mboxDefine` y `mboxUpdate` con el mismo propósito.

+++

+++ No actualice ningún fragmento de HTML con [!DNL Target] si el fragmento requiere código JavaScript para su inicialización.

Cuando se realiza una acción (Editar HTML) en componentes de la página, como reguladores y carruseles, la entrega puede aparecer dañado. El VEC realiza la acción después de que JavaScript haya creado una instancia del componente de página. Sin embargo, cuando el contenido de la página se envía a los visitantes, la acción se aplica antes de que se cree una instancia del componente. Como resultado, la funcionalidad del componente puede o no romperse en el momento de la entrega, según la secuencia de comandos que defina el componente en la página.

Una prueba de envío que funcione la primera vez no garantiza que la entrega siga funcionando, ya que podría existir una condición de carrera:

* Si hay una condición de carrera, la entrega funciona de forma intermitente.
* Si no hay ninguna condición de carrera, la entrega siempre funciona.

Pruebe la página varias veces para asegurarse de que el envío funciona según lo esperado.

+++

## Advertencias {#caveats}

Se aplican las siguientes advertencias al usar **[!UICONTROL Compositor de experiencias visuales]** para diseñar una actividad.

+++ La característica [!UICONTROL Move] no admite z-index.

Sin la funcionalidad z-index, un elemento movido no se puede colocar encima de otro elemento. Consulte [Limitaciones](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721) para más detalles.

+++

+++ La reorganización de elementos afecta al rastreo de clics.

Si se reorganiza un elemento marcado para el rastreo de clics, las rutas de los elementos reorganizados cambian. Como resultado, los clics se rastrean en el elemento de la ubicación donde estaba el elemento original antes de que se reorganizara.

Esto ocurre porque el código que envía el contenido de la actividad y el código que realiza un seguimiento de los clics se incluyen en un fragmento de código que se envía a la página. Si se navega a una página diferente y se configura un rastreo de clics allí, ambos fragmentos de código se entregan a esa página. Si la página de rastreo de clics tiene una estructura de página similar a la de la página donde se ejecuta la prueba, el contenido de la prueba también podría aparecer en la página de rastreo de clics.

+++

+++ Es posible que no se pueda insertar un elemento en un(a) `<div>` que sea un mbox.

Si un mbox contiene una oferta y el mbox se implementa incorrectamente, un elemento insertado podría aparecer como `insertBefore` y no como `insertAfter`.

+++

+++ Cuando edite un elemento principal y un elemento secundario, edite primero el elemento principal.

Si se intercambia una acción de imagen en un elemento y se edita el texto o el HTML de su elemento principal, pueden producirse problemas de entrega. El mejor flujo de trabajo es editar el elemento principal antes de cambiar la imagen en el secundario.

+++

+++ No seleccione un elemento de página que incluya un mbox como elemento secundario.

Por ejemplo, si la página contiene el siguiente código:

```html
<div>
  <div class="mboxDefault" >
  </div>
  <script>mboxCreate('myMbox');
</script>
</div>
```

El div externo no debe seleccionarse en una experiencia, ya que el mbox codificado en la página sigue realizando una llamada a [!DNL Target] y recibe una respuesta. Esta respuesta interfiere con la respuesta destinada al elemento de página más grande.

+++

+++ Es posible que las direcciones IP del proxy estén bloqueadas en el entorno del cliente.

Si el **[!UICONTROL Compositor de experiencias mejorado]** se usa en un sitio que no está activo, como un entorno de ensayo, podrían producirse errores de acceso denegado y tiempos de espera si el sitio bloquea las direcciones IP del proxy.

+++

## Limitaciones {#section_F33C2EA27F2E417AA036BC199DD6C721}

Se aplican las siguientes limitaciones al trabajar con el VEC.

### Requisitos de página

+++ Controlar la compatibilidad del VEC con [!DNL Chrome] cambios de directiva de extensión.

En las directivas de manifiesto [V3 actualizadas en Google Chrome](https://developer.chrome.com/docs/extensions/develop/migrate/what-is-mv3){target=_blank}, las extensiones ya no pueden modificar el DOM original antes de que el explorador lo analice. Como resultado, ciertos scripts de seguridad, como las implementaciones de eliminación de iframes, podrían bloquear la carga de páginas en el VEC.

Para garantizar la compatibilidad, deshabilite de forma condicional estos scripts cuando la página se cargue dentro del iframe [!DNL Target]. Esto se puede hacer de forma segura comprobando la presencia del objeto `window.adobeVecExtension`, que [!DNL Target] inserta mientras se carga el VEC.

Los siguientes fragmentos de código son ejemplos de código de eliminación de iframes que pueden evitar que una página web se cargue en el VEC:

`window.top.location = window.self.location;`

`top.location.href = self.location.href;`

Una simple comprobación puede verificar si una página web está incrustada dentro de [!DNL Target]. El fragmento de código tiene este aspecto:

```
if(!window.adobeVecExtension) {
    // additional security logic
}
```

+++

+++ Las páginas deben aceptar parámetros de URL para que funcione el VEC.

Algunos sitios eliminan cualquier parámetro de URL de sus páginas, pero el VEC requiere esos parámetros.

+++

+++ Cuando se utiliza un script como parte de HTML, declare las variables y funciones a las que se accede desde fuera en el área de nombres de la ventana.

El script se ejecuta dentro del ámbito de `target.js` después de que se cargue la página, por lo que no se puede acceder a ninguna variable o función declarada localmente desde fuera del bloque de script.

*Incorrecto:*

```html
<script>
  var myVar = 123;
  function myFunc() {
    //
  }
</script>
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

+++ La acción `customCode` del VEC no funciona con [!DNL Internet Explorer] 8.

`target.js` no admite esta acción en IE8 debido a las limitaciones de IE8 al administrar contenido de script. Como solución alternativa, si la página contiene jQuery y jQuery está expuesto globalmente en el objeto window, `target.js` puede entregar la acción `customCode`. Asegúrese de que `window.jQuery` y `window.jQuery.fn.prepend` estén definidos.

+++

### Reorganización y mboxes

**No se puede mover un elemento fuera de un contenedor que va seguido de una propiedad CSS.**

+++ No se puede seleccionar el elemento [!UICONTROL Button] para reorganizar.

Los elementos **[!UICONTROL Button]** no se pueden seleccionar directamente para reorganizar. Para habilitar la reorganización, coloque los botones dentro de un contenedor más grande.

+++

+++ No reorganice ni mueva el mismo elemento.

Si un elemento se ha movido a otra ubicación y, a continuación, se selecciona el contenedor principal para reorganizar los elementos secundarios, el elemento movido no se ve afectado y permanece donde está. Es posible que la reorganización no se muestre según lo esperado.

+++

+++ Solo las ofertas de intercambio están disponibles en mboxes.

No se permiten acciones como **[!UICONTROL Editar clase]** y **[!UICONTROL Reorganizar]** dentro de un mbox.

+++

### Imágenes

+++ La acción [!UICONTROL Cambiar imagen] no funciona en una imagen de un carrusel.

Por ejemplo, si la página contiene un carrusel con seis imágenes y una imagen se va a intercambiar por la segunda imagen del carrusel, la acción **[!UICONTROL Cambiar imagen]** no funciona.

Como solución alternativa, seleccione el contenedor principal y use la acción **[!UICONTROL Editar HTML]** para editar el HTML del carrusel y actualizar el origen de la imagen de la imagen deseada.

+++

+++ No se puede cambiar el tamaño de las imágenes en un mbox.

Si una imagen se intercambia en un elemento mbox y luego se cambia su tamaño según el tamaño del elemento mbox, no se permite el cambio de tamaño.

+++

+++ Después de intercambiar una imagen, no se puede seleccionar la acción [!UICONTROL Editar].

Una vez intercambiada la imagen, la dirección URL de Scene7 no se puede editar.

+++

+++ Al insertar una imagen desde la biblioteca [!UICONTROL Content] (Scene7) y editar el HTML, se interrumpe la dirección URL de la imagen.

Agregue un elemento de anclaje dentro del div `customHeaderMessage` con un texto ficticio:

```html
<a href="#">
<span> Dummy text </span>
</a>
```

Seleccione este div con la acción **[!UICONTROL Insertar elemento]** para insertar una imagen como secundaria del texto ficticio.

Una vez insertada la imagen, el código tiene este aspecto:

```html
<a href="#">
<span> Dummy text </span>
<img src=""> This is inserted Image. </img>
</a>
```

Elimine la etiqueta span de “Dummy text”.

+++

### Rastreo de clics y contenido externo

+++ El rastreo de clics no funciona para elementos de anclaje que contienen cualquier otra cosa que no sea texto sin formato o etiquetas de imagen.

Por ejemplo, el rastreo de clics no funciona si el elemento contiene JavaScript.

+++

+++ El rastreo de clics solo se admite en la página en la que se crean experiencias o en la página de redirección.

Aunque el modo **[!UICONTROL Examinar]** está disponible para el rastreo de clics en el VEC, el modo **[!UICONTROL Examinar]** no se puede usar para agregar el rastreo de clics en una página.

+++

+++ Los elementos de HTML con un origen externo no se pueden editar.

Por ejemplo: vídeo, etiquetas de audio, incrustar, iFrames y fotogramas.

+++
