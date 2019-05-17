---
description: El Compositor de experiencias visuales (VEC) para aplicaciones de una sola página (SPA) permite que los comerciantes creen pruebas y personalicen el contenido de las SPA de forma independiente sin tener que esperar desarrollo continuo. El VEC puede usarse para crear actividades en los marcos más populares, como React y Angular.
keywords: vec spa;react;angular;react.js;compositor de experiencias visuales para spa;opciones de compositor de experiencias visuales para spa;aplicaciones de una sola página;aplicación de una sola página;spa;opciones de experiencias móviles;vista de target
seo-description: El Compositor de experiencias visuales (VEC) para aplicaciones de una sola página (SPA) en Adobe Target permite que los expertos en marketing creen pruebas y personalicen el contenido de las SPA de forma independiente sin tener que depender del desarrollo continuo. El VEC puede usarse para crear actividades en los marcos más populares, como React y Angular.
seo-title: Compositor de experiencias visuales para aplicaciones de una sola página (SPA)
solution: Target
title: Compositor de experiencias visuales para aplicaciones de una sola página (SPA)
topic: Standard
uuid: 4dcd6d9c-b2e3-4759-a2e0-3696c572faba
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Compositor de experiencias visuales para aplicaciones de una sola página (SPA){#single-page-app-spa-visual-experience-composer}

En [!DNL Adobe Target], el [!UICONTROL Compositor de experiencias visuales] (VEC) ofrece a los especialistas en marketing una capacidad propia para crear actividades y personalizar experiencias que se pueden distribuir dinámicamente en aplicaciones de varias páginas tradicionales a través del mbox global de Adobe Target. Sin embargo, esto depende de la recuperación de ofertas en carga de página o llamadas al servidor subsiguientes, que introduce latencia, como se muestra en el diagrama siguiente. Este método no es adecuado con aplicaciones de una sola página (SPA) porque degrada la experiencia del usuario y el rendimiento de la aplicación.

![Ciclo de vida tradicional vs. ciclo vital de SPA](/help/c-experiences/assets/trad-vs-spa.png)

Con la versión más reciente, presentamos el VEC para las SPA. El VEC para aplicaciones de una sola página (SPA) permite que los comerciantes creen pruebas y personalicen el contenido de las SPA de forma independiente sin tener que depender de un desarrollo continuo. El VEC se puede utilizar para crear [pruebas A/B](/help/c-activities/t-test-ab/test-ab.md) y actividades de [segmentación de experiencias](/help/c-activities/t-experience-target/experience-target.md) (XT) en marcos populares, como React y Angular.

## Vistas de Adobe Target y Aplicaciones de una sola página

El VEC de Adobe Target para SPA aprovecha un nuevo concepto llamado Vistas: un grupo lógico de elementos visuales que, juntos, constituyen una experiencia de SPA. Una SPA puede, por lo tanto, considerarse como una transición entre vistas (en lugar de las direcciones URL) según las interacciones del usuario. Una vista suele representar un sitio completo o elementos visuales agrupados dentro de un sitio.

Para explicar más sobre las vistas, vamos a navegar por este hipotético sitio de comercio electrónico en línea, implementado en React, y a explorar algunas de las vistas de ejemplo. Haga clic en los vínculos siguientes para abrir el sitio en una nueva pestaña del explorador.

**Vínculo:[Sitio principal](https://target.enablementadobe.com/react/demo/#/)**

![página de inicio](/help/c-experiences/assets/home.png)

Si vamos a la página de inicio, podemos ver inmediatamente una imagen promocional de Pascua, así como los productos más recientes que venden en el sitio. En este caso, una vista puede definirse como toda la página de inicio. Es práctico tenerlo en cuenta porque se ampliará en la sección Implementación de vistas de Adobe Target, que se describe a continuación.

**Vínculo:[Sitio de productos](https://target.enablementadobe.com/react/demo/#/products)**

![sitio del producto](/help/c-experiences/assets/product-site.png)

Como el producto nos interesa, decidimos hacer clic en el vínculo Productos. De manera similar a la página de inicio, se puede definir todo el sitio del producto como una vista. Podemos asignar el nombre “productos” a esta vista al igual que el nombre de la ruta en `https://target.enablementadobe.com/react/demo/#/products`.

![sitio del producto 2](/help/c-experiences/assets/product-site-2.png)

Al principio de esta sección, definimos Vistas como el sitio completo o incluso un grupo de elementos visuales en un determinado sitio. Como mencionamos antes, los cuatro productos mostrados en el sitio también pueden agruparse y considerarse como una vista. Si queremos, podemos ponerle el nombre “productos” a esta vista.

![sitio del producto 3](/help/c-experiences/assets/product-site-3.png)

Decidimos hacer clic en el botón Cargar más para explorar más productos en el sitio. En este caso, la dirección URL del sitio web no cambia. Sin embargo, aquí, una vista puede representar solamente la segunda fila de productos que se muestra arriba. El nombre de la vista puede ser “PRODUCTS-PAGE-2”.

**Vínculo:[Cierre de compra](https://target.enablementadobe.com/react/demo/#/checkout)**

![página de salida](/help/c-experiences/assets/checkout.png)

Como nos gustaron algunos productos mostrados en el sitio, decidimos comprar un par. Ahora, en el sitio de compra se proporcionan algunas opciones para elegir el envío normal o el exprés. Como una vista puede ser cualquier grupo de elementos visuales en un sitio, podemos nombrar esta como “Ver preferencias de envío”.

Además, el concepto de Vistas puede ampliarse mucho más. Si los especialistas en marketing desean personalizar el contenido del sitio según las preferencias de envío que seleccione, se puede crear una vista para cada preferencia de entrega. En este caso, cuando seleccionamos Envío normal, la Vista puede llamarse “Envío normal”. Si se selecciona Envío exprés, la opción Vista puede llamarse “Envío exprés”.

Es posible que los especialistas en marketing deseen ejecutar una prueba A/B para ver si el cambio del color de azul a rojo cuando se selecciona la opción Envío exprés puede mejorar las conversiones en lugar de mantener el botón de color azul en ambas opciones de envío.

## Implementación de Vistas de Adobe Target

Ahora que hemos cubierto lo que son las vistas de Adobe Target, podemos aprovechar este concepto en Target para permitir a los especialistas en marketing ejecutar pruebas A/B y XT en SPA a través del VEC. Esto requiere una configuración de desarrollador única. Veamos los pasos para configurarlo.

1. Instale at. js 2. x.

   Primero, necesitamos instalar at. js 2. x. Esta versión de at. js se desarrolló con los spas en mente. Las versiones anteriores de at.js y mbox.js no son compatibles con las vistas de Adobe Target y con el VEC para SPA.

   ![Cuadro de diálogo de detalles de implementación](/help/c-experiences/assets/imp-200.png)

   Descargue at. js 2. x a través de la IU de Adobe Target ubicada en [!UICONTROL Configuración &gt; Implementación]. at. js 2. x también se puede implementar mediante [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md). Sin embargo, las extensiones de Adobe Target no están actualizadas actualmente y no son compatibles.

1. Implementar la función más reciente de at. js 2. x: [Triggerview ()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md) en sus sitios.

   Después de definir las vistas de la SPA donde desee ejecutar una prueba A/B o XT, implemente la `triggerView()` función at. js 2. x con las vistas pasadas como parámetro. Esto permite a los especialistas en marketing utilizar el VEC para diseñar y ejecutar las pruebas A/B y XT para esas vistas definidas. Si la función de `triggerView()` no está definida para estas vistas, el VEC no detectará las vistas y, por lo tanto, los especialistas en marketing no podrán utilizar el VEC para diseñar y ejecutar pruebas A/B y XT.

   **`adobe.target.triggerView(viewName, options)`**

   | Parámetro | Tipo | ¿Requerido? | Información general | Descripción |
   | --- | --- | --- | --- | --- |
   | Nombre de vista | Cadena | Sí | 1. No hay espacios al final.<br>2. No puede estar vacío.<br>3. El nombre de la vista debe ser único para todas las páginas.<br>4. **Advertencia**: el nombre de la vista no debe comenzar ni finalizar con “`/`”. Esto se debe a que el cliente generalmente extraería el nombre de la vista de la ruta de la URL. Para nosotros, “home” y “`/home`” son diferentes.<br>5. **Advertencia**: la misma vista no debe activarse varias veces con la opción `{page: true}`. | Pase cualquier nombre como tipo de cadena que desee que represente la vista. Este nombre de Vista se muestra en el panel [!UICONTROL Modificaciones] del VEC para que los especialistas en marketing creen acciones y ejecuten sus actividades A/B y XT. |
   | opciones | Objeto | No |
   | opciones &gt; página | Booleano | No | **VERDADERO**: el valor predeterminado de la página es verdadero. Cuando `page=true`, las notificaciones se enviarán a los servidores de Edge para incrementar el recuento de impresiones.<br>**FALSO**: cuando `page=false`, las notificaciones no se enviarán para incrementar el recuento de impresiones. Debe utilizarse cuando desee volver a procesar un componente en una página con una oferta. |

   Veamos algunos ejemplos de casos de uso sobre la invocación de la función `triggerView()` en React para el SPA de comercio electrónico hipotético:

   **Vínculo:[Sitio principal](https://target.enablementadobe.com/react/demo/#/)**

   ![home-react-1](/help/c-experiences/assets/react1.png)

   Como especialistas en marketing, si queremos ejecutar pruebas A/B en todo el sitio principal, es posible que queramos nombrar la vista “home” que puede extraerse de la dirección URL:

   ```
   function targetView() {
     var viewName = window.location.hash; // or use window.location.pathName if router works on path and not hash
   
     viewName = viewName || 'home'; // view name cannot be empty
   
     // Sanitize viewName to get rid of any trailing symbols derived from URL
     if (viewName.startsWith('#') || viewName.startsWith('/')) {
       viewName = viewName.substr(1);
     }
   
     // Validate if the Target Libraries are available on your website
     if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
       adobe.target.triggerView(viewName);
     }
   }
   
   // react router v4
   const history = syncHistoryWithStore(createBrowserHistory(), store);
   history.listen(targetView);
   
   // react router v3
   <Router history={hashHistory} onUpdate={targetView} >
   ```

   **Vínculo:[Sitio de productos](https://target.enablementadobe.com/react/demo/#/products)**

   Veamos un ejemplo que es un poco más complicado. Digamos que como especialistas en marketing queremos personalizar la segunda fila de los productos cambiando el color de la etiqueta Precio a rojo después de que un usuario haga clic en el botón Cargar más.

   ![Reacción de productos](/help/c-experiences/assets/react4.png)

   ```
   function targetView(viewName) {
     // Validate if the Target Libraries are available on your website
     if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
       adobe.target.triggerView(viewName);
     }
   }
   
   class Products extends Component {
     render() {
       return (
         <button type="button" onClick={this.handleLoadMoreClicked}>Load more</button>
       );
     }
   
     handleLoadMoreClicked() {
       var page = this.state.page + 1; // assuming page number is derived from component’s state
       this.setState({page: page});
       targetView('PRODUCTS-PAGE-' + page);
     }
   }
   ```

   **Vínculo:[Cierre de compra](https://target.enablementadobe.com/react/demo/#/checkout)**

   ![Reacción de finalización de compra](/help/c-experiences/assets/react6.png)

   Si los especialistas en marketing desean personalizar el contenido del sitio según las preferencias de envío que seleccione, se puede crear una vista para cada preferencia de entrega. En este caso, cuando seleccionamos Envío normal, la Vista puede llamarse “Envío normal”. Si se selecciona Envío exprés, la opción Vista puede llamarse “Envío exprés”.

   Es posible que los especialistas en marketing deseen ejecutar una prueba A/B para ver si el cambio del color de azul a rojo cuando se selecciona la opción Envío exprés puede mejorar las conversiones en lugar de mantener el botón de color azul en ambas opciones de envío.

   ```
   function targetView(viewName) {
     // Validate if the Target Libraries are available on your website
     if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
       adobe.target.triggerView(viewName);
     }
   }
   
   class Checkout extends Component {
     render() {
       return (
         <div onChange={this.onDeliveryPreferenceChanged}>
           <label>
             <input type="radio" id="normal" name="deliveryPreference" value={"Normal Delivery"} defaultChecked={true}/>
             <span> Normal Delivery (7-10 business days)</span>
           </label>
   
           <label>
             <input type="radio" id="express" name="deliveryPreference" value={"Express Delivery"}/>
             <span> Express Delivery* (2-3 business days)</span>
           </label>
         </div>
       );
     }
     onDeliveryPreferenceChanged(evt) {
       var selectedPreferenceValue = evt.target.value;
       targetView(selectedPreferenceValue);
     }
   }
   ```

1. Inicie actividades A/B o XT a través del VEC.

   Cuando `adobe.target.triggerView()` se implementa en el SPA con los nombres de vista pasados como parámetros, el VEC podrá detectar estas vistas y permitir a los usuarios crear acciones y modificaciones para las actividades A/B o XT.

   >[!NOTE]
   >
   >El VEC para los SPA es realmente el mismo VEC que utiliza en las páginas web normales, pero algunas funcionalidades adicionales están disponibles al abrir una aplicación de página única implementada con `triggerView()`.

Existen dos mejoras principales en el panel [Modificaciones](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) y en las Acciones del VEC que permiten al VEC funcionar bien con SPA.

**Panel de modificaciones**

El panel [!UICONTROL Modificaciones], como se muestra a continuación, captura las acciones creadas para una vista en particular. Observe que todas las acciones de una vista se agrupan debajo de Ver.

**Acciones**

Al hacer clic en una acción se resalta el elemento del sitio donde se aplicará esta acción. Cada acción de VEC creada dentro de una vista tiene cuatro iconos tal como se muestra más abajo: Información, Editar, Mover a “Carga de página” y Eliminar.

![Panel de modificaciones](/help/c-experiences/assets/modifications.png)

La siguiente tabla describe cada acción:

| Página | Descripción |
| --- | --- |
| Información | Muestra los detalles de esta acción. |
| Editar | Permite editar las propiedades de esta acción directamente. |
| Mover a “Carga de página” | Mueve la acción al evento de carga de página. Estas acciones suelen aplicarse al HTML estático de la SPA que se utiliza en todas las páginas, como el encabezado y el pie de página. |
| Eliminar | Elimina la acción. |

**Ejemplo 1**

Veamos el ejemplo anterior, en el que hemos creado una vista de la página Inicio. Nuestro objetivo para esta vista es doble:

1. Cambie el botón Agregar al carro y el botón “Me gusta” por un color azul más claro. Esto debería suceder en una “Carga de página”, ya que estamos cambiando componentes del encabezado.
1. Cambie la etiqueta “Productos más recientes para 2019” por “Productos de prueba para 2019” con el color del texto cambiado a morado.

Para ejecutar estos objetivos, en el VEC, haga clic en [!UICONTROL Componer] y aplique dichos cambios en la vista Inicio.

![Ejemplo 1](/help/c-experiences/assets/example1.png)

**Ejemplo 2**

Veamos el ejemplo anterior, donde hemos creado la vista “PRODUCTS-PAGE-2”. Nuestro objetivo es cambiar la etiqueta “Precio” por “Precio de venta” con el color de la etiqueta rojo.

1. Haga clic en [!UICONTROL Examinar] y, a continuación, en el vínculo [!UICONTROL Productos] del encabezado.
1. Haga clic en [!UICONTROL Cargar más] una vez para llegar a la segunda fila de productos.
1. Haga clic en [!UICONTROL Componer].
1. Aplique acciones para cambiar la etiqueta de texto a “Precio de venta” y a color a rojo.

![Ejemplo 2](/help/c-experiences/assets/example2.png)

**Ejemplo 3**

Por último, como se mencionó anteriormente, las vistas pueden definirse a nivel granular. Las vistas pueden ser un estado o incluso una opción de un botón de radio. Anteriormente creamos vistas como CHECKOUT-EXPRESS y CHECKOUT-NORMAL. Nuestro objetivo es cambiar el color del botón a rojo para la vista CHECKOUT-EXPRESS.

1. Haga clic en [!UICONTROL Examinar].
1. Agregue un par de productos al carrito de la compra.
1. En la esquina superior derecha, haga clic en el icono del carrito de la compra.
1. Haga clic en Finalizar compra.
1. Haga clic en el botón de opción Envío exprés.
1. Haga clic en [!UICONTROL Componer].
1. Cambie el botón “Pagar” y nómbrelo “Completar pedido” y cambie el color a rojo.

![Ejemplo 3](/help/c-experiences/assets/example3.png)

>[!NOTE]
>
>La vista CHECKOUT-EXPRESS no aparecerá en el panel de modificación hasta que haga clic en el botón de opción Envío Exprés. Esto se debe a que la función `triggerView()` se activa cuando se selecciona el botón de opción Envío exprés y esto solo sucede cuando el VEC sabe que hay una vista para mostrar en el panel de modificación.

## Inmersión en at.js y las SPA

**¿Cómo puedo recuperar vistas para los datos de audiencia más recientes mediante acciones después de la carga inicial de la página en mi SPA?**

El flujo de trabajo típico de at. js 2. x es cuando se carga el sitio, todas las vistas y acciones se almacenan en caché para que las acciones subsiguientes del usuario en el sitio no desencadenen llamadas al servidor para recuperar ofertas. Si desea recuperar vistas según los datos de perfil más actualizados que puedan haberse actualizado, según las acciones de usuario subsiguientes, puede llamar a `getOffers()` y `applyOffers()` con los datos de perfil o usuario de audiencia más recientes.

Por ejemplo: considere que es una empresa de telecomunicaciones y tiene un SPA que usa at. js 2. x. Como negocio, desea lograr los siguientes objetivos:

* Para un usuario anónimo o con sesión cerrada: mostrar la última promoción de la empresa, como una oferta de “Primer mes gratis” en `http://www.telecom.com/home`.
* Para un usuario que ha iniciado sesión: mostrar una oferta promocional de actualización para usuarios cuyos contratos están surgiendo, como “Tiene derecho a un teléfono gratis” en `http://www.telecom.com/loggedIn/home`.

Ahora, los desarrolladores asignan nombres a las vistas y llaman a `triggerView()` de la siguiente manera:

* Para `http://www.telecom.com/home` el nombre de vista es “Logged Out Home”
   * Se invoca a `triggerView(“Logged Out Home”)`.
* Para `http://www.telecom.com/loggedIn/home`, el nombre de la vista es “Logged In Home”
   * Al cambiar la ruta, se invoca a `triggerView(“Logged In Home”)`.

A continuación, los especialistas en marketing ejecutan las siguientes actividades A/B a través del VEC:

* Actividad A/B con la oferta “Primer mes gratis” para audiencias con el parámetro “`loggedIn= false`” que se mostrará en `http://www.telecom.com/home`, donde el nombre de la vista es Logged Out Home.
* Actividad A/B con la oferta “Tiene derecho a un teléfono gratis” para audiencias con el parámetro “`loggedIn=true`” que se mostrará en `http://www.telecom.com/loggedIn/home`, donde el nombre de la vista es Oferta principal con sesión iniciada.

Ahora, veamos el flujo de este usuario:

1. Un usuario que ha iniciado sesión anónima aterriza en su página.
1. Como usa at. js 2. x, pasa el parámetro «`loggedIn = false`» en la carga de página para recuperar todas las vistas presentes en actividades activas que califican cuando la audiencia tiene parámetro «`loggedIn = false`».
1. A continuación, at. js 2. x recupera la vista Inicio de sesión cerrada y la acción para mostrar la oferta «Primera mes gratis» y la almacena en la caché.
1. Cuando `triggerView(“Logged Out Home”)` se invoca, la oferta “Primer mes gratis” se recupera desde la caché y la oferta se muestra sin una llamada al servidor.
1. El usuario hace clic en “Iniciar sesión” y proporciona sus credenciales.
1. Como el sitio web es un SPA, no realiza una carga de página completa y enruta al usuario a `http://www.telecom.com/loggedIn/home`.

Ahora, aquí está el problema. El usuario inicia sesión y nos encontramos con `triggerView(“Logged In Home”)` porque hemos colocado este código en el cambio de ruta. Esto indica a at. js 2. x que recupere la vista y las acciones de la caché, pero la única vista que existe en la caché es la página de inicio cerrada.

Entonces, ¿cómo podemos recuperar la Vista de inicio de sesión y mostrar la oferta “Usted es apto para un conseguir un teléfono gratuito”? Y, dado que todas las acciones subsiguientes del sitio serán desde una perspectiva de usuario registrado, ¿cómo puede asegurarse de que todas las acciones subsiguientes resulten en ofertas personalizadas para usuarios que iniciaron sesión?

Puede utilizar las nuevas `getOffers()``applyOffers()` funciones y funciones admitidas en at. js 2. x:

```
adobe.target.getOffers({
  request: {
  prefetch: {
    "views": [
      {
        "parameters": {
          "loggedIn": true
        },
      }
    ]
  },
});
```

Pase la respuesta `getOffers()` a `applyOffers()` y ahora todas las vistas y acciones asociadas con “loggedin = true” actualizarán la caché at.js.

En otras palabras, at. js 2. x es compatible con una forma de recuperar vistas, acciones y ofertas con los datos de audiencia más actualizados en forma a petición.

**¿at. js 2. x admite A 4 T para aplicaciones de una sola página?**

Sí, at. js 2. x admite A 4 T para SPA a través de la `triggerView()` función, ya que se ha implementado Adobe Analytics y el servicio de ID de visitante de Experience Cloud. Consulte el diagrama siguiente con descripciones paso a paso.

![Flujo de destino](/help/c-experiences/assets/atjs-spa-flow.png)

| Paso   | Descripción |
| --- | --- |
| 1 | `triggerView()` es llamado en la SPA para procesar una vista y aplicar acciones para modificar elementos visuales asociados a la vista. |
| 2 | El contenido dirigido para la vista se lee desde la caché. |
| 3 | El contenido dirigido se muestra lo más rápido posible y sin parpadeo del contenido predeterminado. |
| 4 | La solicitud de notificación se envía al Almacén de perfiles de Target para contar al visitante en la actividad e incrementar las métricas. |
| 5 | Los datos de Analytics se envían a los servidores de recopilación de datos. |
| 6 | Se comparan los datos de Target con los datos de Analytics mediante el SDID y se procesan en el almacén de informes de Analytics. Por lo tanto, los datos de Analytics se pueden visualizar tanto en Analytics como en Target mediante los informes de A4T. |

>[!NOTE]
>Si no desea enviar notificaciones a Adobe Analytics para el recuento de impresiones cada vez que se activa una vista, pase la función `{page: false}` a `triggerView()` para que el recuento de impresiones no aumente cuando una vista se active varias veces para un componente que se vuelve a procesar constantemente. Por ejemplo:
>
>`adobe.target.triggerView(“PRODUCTS-PAGE-2”, {page:false})`

## Actividades compatibles

| Tipo de actividad | Compatible? |
| --- | --- |
| [Prueba A/B](/help/c-activities/t-test-ab/test-ab.md) | Sí |
| [Recommendations como una oferta de](/help/c-recommendations/recommendations-as-an-offer.md)<br> en pruebas A/B y actividades de Segmentación de experiencias (XT) | Sí |
| [Asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Sí |
| [Segmentación de experiencias](/help/c-activities/t-experience-target/experience-target.md) | Sí |
| [Prueba multivariable](/help/c-activities/c-multivariate-testing/multivariate-testing.md) | No |
| [Segmentación automática](/help/c-activities/auto-target-to-optimize.md) | No |
| [Personalización automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md) | No |
| [Recommendations](/help/c-recommendations/recommendations.md) | No |

**Si instalamos at. js 2. x e implementamos`triggerView()`en nuestros sitios,¿cómo ejecutamos actividades A/B de segmentación automática porque el VEC de SPA no admite la segmentación automática?**

Si desea utilizar actividades A/B de Segmentación automática puede mover todas las acciones que se ejecutan al evento de Carga de página en el VEC. Pase el ratón sobre cada acción y haga clic en el botón [!UICONTROL Mover al evento de Carga de página]. Hecho esto, puede seleccionar Segmentación automática para el método de asignación de tráfico.

## Integraciones compatibles

| Integración | Compatible? |
| --- | --- |
| [Analytics for Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md) | Sí |
| [Audiencias de Experience Cloud](/help/c-integrating-target-with-mac/mmp.md) | Sí |
| [Atributos del cliente](/help/c-target/c-visitor-profile/working-with-customer-attributes.md) | Sí |
| [Fragmentos de experiencia de AEM](/help/c-experiences/c-manage-content/aem-experience-fragments.md) | Sí |

## Funciones compatibles {#supported-features}

| Función | Compatible? |
| --- | --- |
| [Workspaces y propiedades](/help/administrating-target/c-user-management/property-channel/property-channel.md) | Sí |
| [Vínculos de control de calidad](/help/c-activities/c-activity-qa/activity-qa.md) | Sí |
| [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md) | No |
| [Código personalizado  ](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) | Sí |
| [Opciones de VEC](/help/c-experiences/c-visual-experience-composer/viztarget-options.md) | Todas |
| [Seguimiento de clics](/help/c-activities/r-success-metrics/click-tracking.md) | Sí |
| [Entrega de varias actividades](/help/c-experiences/c-visual-experience-composer/multipage-activity.md) | Sí |

## Vídeo de formación: Uso del VEC para SPA en Adobe Target

>[!VIDEO](https://video.tv.adobe.com/v/26249)

Consulte [Uso del Compositor de experiencias visuales para una aplicación de una sola página (SPA VEC) en Adobe Target](https://helpx.adobe.com/target/kt/using/visual-experience-composer-for-single-page-applications-feature-video-use.html) para obtener más información.
