---
keywords: vec spa;react;angular;react.js;compositor de experiencias visuales para spa;opciones de compositor de experiencias visuales para spa;aplicaciones de una sola página;aplicación de una sola página;spa;opciones de experiencias móviles;vista de target
description: Aprenda a utilizar el VEC SPA en Adobe [!DNL Target] para crear pruebas y personalizar contenido en SPA de forma independiente sin tener que depender de un desarrollo continuo.
title: ¿Cómo utilizo el Compositor de experiencias visuales de una aplicación de una sola página (SPA VEC)?
feature: 'Compositor de experiencias visuales (VEC). '
exl-id: fd3dcfaa-e5c6-45a1-8229-9c206562e5b0
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '3700'
ht-degree: 91%

---

# Compositor de experiencias visuales para aplicaciones de una sola página (SPA)

En [!DNL Adobe Target], el [!UICONTROL Compositor de experiencias visuales] (VEC) ofrece a los especialistas en marketing una capacidad propia para crear actividades y personalizar experiencias que se pueden distribuir dinámicamente en aplicaciones de varias páginas tradicionales a través del mbox global de Adobe Target. Sin embargo, esto depende de la recuperación de ofertas en carga de página o llamadas al servidor subsiguientes, que introduce latencia, como se muestra en el diagrama siguiente. Este método no es adecuado con aplicaciones de una sola página (SPA) porque degrada la experiencia del usuario y el rendimiento de la aplicación.

![Ciclo de vida tradicional vs. ciclo vital de SPA](/help/c-experiences/assets/trad-vs-spa.png)

Con la versión más reciente, presentamos el VEC para las SPA. El VEC para aplicaciones de una sola página (SPA) permite que los comerciantes creen pruebas y personalicen el contenido de las SPA de forma independiente sin tener que depender de un desarrollo continuo. El VEC se puede utilizar para crear [pruebas A/B](/help/c-activities/t-test-ab/test-ab.md) y actividades de [segmentación de experiencias](/help/c-activities/t-experience-target/experience-target.md) (XT) en marcos populares, como React y Angular.

## Vistas de Adobe [!DNL Target] y aplicaciones de una sola página

El VEC de Adobe Target para SPA aprovecha un nuevo concepto llamado Vistas: un grupo lógico de elementos visuales que, juntos, constituyen una experiencia de SPA. Una SPA puede, por lo tanto, considerarse como una transición entre vistas (en lugar de las direcciones URL) según las interacciones del usuario. Una vista suele representar un sitio completo o elementos visuales agrupados dentro de un sitio.

Para explicar más sobre las vistas, vamos a navegar por este hipotético sitio de comercio electrónico en línea, implementado en React, y a explorar algunas de las vistas de ejemplo. Haga clic en los vínculos siguientes para abrir el sitio en una nueva pestaña del explorador.

**Vínculo:  [Sitio principal](https://target.enablementadobe.com/react/demo/#/)**

![página de inicio](/help/c-experiences/assets/home.png)

Si vamos a la página de inicio, podemos ver inmediatamente una imagen promocional de Pascua, así como los productos más recientes que venden en el sitio. En este caso, una vista puede definirse como toda la página de inicio. Es práctico tenerlo en cuenta porque se ampliará en la sección Implementación de vistas de Adobe Target, que se describe a continuación.

**Vínculo:  [Sitio del producto](https://target.enablementadobe.com/react/demo/#/products)**

![sitio del producto](/help/c-experiences/assets/product-site.png)

Como el producto nos interesa, decidimos hacer clic en el vínculo Productos. De manera similar a la página de inicio, se puede definir todo el sitio del producto como una vista. Podemos asignar el nombre “productos” a esta vista al igual que el nombre de la ruta en `https://target.enablementadobe.com/react/demo/#/products`.

![sitio del producto 2](/help/c-experiences/assets/product-site-2.png)

Al principio de esta sección, definimos Vistas como el sitio completo o incluso un grupo de elementos visuales en un determinado sitio. Como mencionamos antes, los cuatro productos mostrados en el sitio también pueden agruparse y considerarse como una vista. Si queremos, podemos ponerle el nombre “productos” a esta vista.

![sitio del producto 3](/help/c-experiences/assets/product-site-3.png)

Decidimos hacer clic en el botón Cargar más para explorar más productos en el sitio. En este caso, la dirección URL del sitio web no cambia. Sin embargo, aquí, una vista puede representar solamente la segunda fila de productos que se muestra arriba. El nombre de la vista puede ser “PRODUCTS-PAGE-2”.

**Vínculo:  [Cierre de compra](https://target.enablementadobe.com/react/demo/#/checkout)**

![página de salida](/help/c-experiences/assets/checkout.png)

Como nos gustaron algunos productos mostrados en el sitio, decidimos comprar un par. Ahora, en el sitio de compra se proporcionan algunas opciones para elegir el envío normal o el exprés. Como una vista puede ser cualquier grupo de elementos visuales en un sitio, podemos nombrar esta como “Ver preferencias de envío”.

Además, el concepto de Vistas puede ampliarse mucho más. Si los especialistas en marketing desean personalizar el contenido del sitio según las preferencias de envío que seleccione, se puede crear una vista para cada preferencia de entrega. En este caso, cuando seleccionamos Envío normal, la Vista puede llamarse “Envío normal”. Si se selecciona Envío exprés, la opción Vista puede llamarse “Envío exprés”.

Es posible que los especialistas en marketing deseen ejecutar una prueba A/B para ver si el cambio del color de azul a rojo cuando se selecciona la opción Envío exprés puede mejorar las conversiones en lugar de mantener el botón de color azul en ambas opciones de envío.

## Implementación de vistas de Adobe [!DNL Target]

Ahora que hemos cubierto lo que son las vistas de Adobe Target, podemos aprovechar este concepto en Target para permitir a los especialistas en marketing ejecutar pruebas A/B y XT en SPA a través del VEC. Esto requiere una configuración de desarrollador única. Veamos los pasos para configurarlo.

1. Instale at. js 2. x.

   En primer lugar, es necesario instalar at.js 2.x. Esta versión de at.js se desarrolló teniendo en cuenta las SPA. Las versiones anteriores de at.js y mbox.js no son compatibles con las vistas de Adobe Target y con el VEC para SPA.

   ![Cuadro de diálogo de detalles de implementación](/help/c-experiences/assets/imp-200.png)

   Descargue at.js 2 a través de la IU de Adobe Target ubicada en [!UICONTROL Administration > Implementation]. at.js 2.x también se puede implementar mediante [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md). Sin embargo, las extensiones de Adobe Target no están actualizadas actualmente y no son compatibles.

1. Implemente la función más reciente de at.js 2.x en sus sitios: [triggerView()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md).

   Después de definir las vistas de la SPA donde desea ejecutar una prueba A/B o XT, implemente la función de at.js 2.x `triggerView()` con las vistas transferidas como parámetro. Esto permite a los especialistas en marketing utilizar el VEC para diseñar y ejecutar las pruebas A/B y XT para esas vistas definidas. Si la función de `triggerView()` no está definida para estas vistas, el VEC no detectará las vistas y, por lo tanto, los especialistas en marketing no podrán utilizar el VEC para diseñar y ejecutar pruebas A/B y XT.

   **`adobe.target.triggerView(viewName, options)`**

   | Parámetro | Tipo | ¿Requerido? | Información general | Descripción |
   | --- | --- | --- | --- | --- |
   | Nombre de vista | Cadena | Sí | 1. No hay espacios al final.<br>2. No puede estar vacío.<br>3. El nombre de la vista debe ser único para todas las páginas.<br>4. **Advertencia**: el nombre de la vista no debe comenzar ni finalizar con “`/`”. Esto se debe a que el cliente generalmente extraería el nombre de la vista de la ruta de la URL. Para nosotros, “home” y “`/home`” son diferentes.<br>5. **Advertencia**: la misma vista no debe activarse varias veces con la opción `{page: true}`. | Pase cualquier nombre como tipo de cadena que desee que represente la vista. Este nombre de Vista se muestra en el panel [!UICONTROL Modificaciones] del VEC para que los especialistas en marketing creen acciones y ejecuten sus actividades A/B y XT. |
   | opciones | Objeto | No |  |  |
   | opciones > página | Booleano | No |  | **VERDADERO**: el valor predeterminado de la página es verdadero. Cuando `page=true`, las notificaciones se enviarán a los servidores de Edge para incrementar el recuento de impresiones.<br>**FALSO**: cuando `page=false`, las notificaciones no se enviarán para incrementar el recuento de impresiones. Debe utilizarse cuando desee volver a procesar un componente en una página con una oferta. |

   Veamos algunos ejemplos de casos de uso sobre la invocación de la función `triggerView()` en React para el SPA de comercio electrónico hipotético:

   **Vínculo:  [Sitio principal](https://target.enablementadobe.com/react/demo/#/)**

   ![home-react-1](/help/c-experiences/assets/react1.png)

   Como especialistas en marketing, si queremos ejecutar pruebas A/B en todo el sitio principal, es posible que queramos nombrar la vista “home” que puede extraerse de la dirección URL:

   ```javascript
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

   **Vínculo:  [Sitio de productos](https://target.enablementadobe.com/react/demo/#/products)**

   Veamos un ejemplo que es un poco más complicado. Digamos que como especialistas en marketing queremos personalizar la segunda fila de los productos cambiando el color de la etiqueta Precio a rojo después de que un usuario haga clic en el botón Cargar más.

   ![Reacción de productos](/help/c-experiences/assets/react4.png)

   ```javascript
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

   **Vínculo:  [Cierre de compra](https://target.enablementadobe.com/react/demo/#/checkout)**

   ![Reacción de finalización de compra](/help/c-experiences/assets/react6.png)

   Si los especialistas en marketing desean personalizar el contenido del sitio según las preferencias de envío que seleccione, se puede crear una vista para cada preferencia de entrega. En este caso, cuando seleccionamos Envío normal, la Vista puede llamarse “Envío normal”. Si se selecciona Envío exprés, la opción Vista puede llamarse “Envío exprés”.

   Es posible que los especialistas en marketing deseen ejecutar una prueba A/B para ver si el cambio del color de azul a rojo cuando se selecciona la opción Envío exprés puede mejorar las conversiones en lugar de mantener el botón de color azul en ambas opciones de envío.

   ```javascript
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

Al hacer clic en una acción se resalta el elemento del sitio donde se aplicará esta acción. Cada acción del VEC creada en una Vista tiene los iconos siguientes, como se muestra a continuación: Información, Editar, Clonar, Mover y Eliminar.

![Modificaciones](/help/c-experiences/assets/modifications.png)

La siguiente tabla describe cada acción:

| Página | Descripción |
| --- | --- |
| Información | Muestra los detalles de esta acción. |
| Editar | Permite editar las propiedades de esta acción directamente. |
| Clonar | Clona la acción a una o varias vistas del panel [!UICONTROL Modificaciones] o a una o varias vistas a las que ha llegado a través del VEC. La acción no tiene que incluirse necesariamente en el panel [!UICONTROL Modificaciones].<br>**Nota**: Después de realizar una operación de clonado, debe navegar a la vista en el VEC a través de [!UICONTROL Examinar] para ver si la acción clonada era una operación válida. Si la acción no se puede aplicar a la vista, aparecerá un error. |
| Mover | Mueve la acción a un Evento de carga de página o a cualquier otra Vista que ya se encuentre en el panel Modificaciones.<br>[!UICONTROL Evento de carga de página]: cualquier acción que corresponda al evento de carga de página se aplica en la carga inicial de la página web.<br>**Nota:** Después de realizar una operación Mover, debe navegar a la vista en el VEC a través de Examinar para comprobar si el desplazamiento era una operación válida. Si la acción no se puede aplicar a la vista, aparecerá un error |
| Eliminar | Elimina la acción. |

>[!NOTE]
>
>Puede realizar muchas acciones antes de que la página se cargue en el VEC, o incluso si la página no se puede cargar. Las acciones que no se pueden editar antes de que el sitio web cargue no aparecerán en la IU de.

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

El flujo de trabajo típico de at.js 2.x es cuando se carga su sitio, cuando todas las vistas y acciones se almacenan en caché para que las acciones subsiguientes del usuario en el sitio no desencadenen llamadas al servidor para recuperar ofertas. Si desea recuperar vistas según los datos de perfil más actualizados que puedan haberse actualizado, según las acciones de usuario subsiguientes, puede llamar a `getOffers()` y `applyOffers()` con los datos de perfil o usuario de audiencia más recientes.

Por ejemplo, imaginemos que es una compañía de telecomunicaciones y tiene una SPA que utiliza at.js 2.x. Como empresa, desea lograr los siguientes objetivos:

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
1. Como está utilizando at.js 2.x, pasa el parámetro “`loggedIn = false`” en la carga de página para recuperar todas las vistas presentes en actividades activas que cumplen con los requisitos cuando la audiencia tiene el parámetro “`loggedIn = false`”.
1. A continuación, at.js 2.x recupera la vista Inicio de sesión cerrada y la acción para mostrar la oferta “Primer mes gratis” y la almacena en la caché.
1. Cuando `triggerView(“Logged Out Home”)` se invoca, la oferta “Primer mes gratis” se recupera desde la caché y la oferta se muestra sin una llamada al servidor.
1. El usuario hace clic en “Iniciar sesión” y proporciona sus credenciales.
1. Como el sitio web es un SPA, no realiza una carga de página completa y enruta al usuario a `http://www.telecom.com/loggedIn/home`.

Ahora, aquí está el problema. El usuario inicia sesión y nos encontramos con `triggerView(“Logged In Home”)` porque hemos colocado este código en el cambio de ruta. Esto le indica a at.js 2.x que recupere la vista y las acciones de la caché, pero la única vista que existe en la caché es la página de inicio cerrada.

Entonces, ¿cómo podemos recuperar la Vista de inicio de sesión y mostrar la oferta “Usted es apto para un conseguir un teléfono gratuito”? Y, dado que todas las acciones subsiguientes del sitio serán desde una perspectiva de usuario registrado, ¿cómo puede asegurarse de que todas las acciones subsiguientes resulten en ofertas personalizadas para usuarios que iniciaron sesión?

Puede utilizar las nuevas funciones `getOffers()` y `applyOffers()` compatibles en at.js 2.x:

```javascript
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

En otras palabras, at.js 2.x es compatible con una manera de recuperar vistas, acciones y ofertas con los datos de audiencia más actuales bajo demanda.

**¿at.js 2.x es compatible con A4T para aplicaciones de una sola página?**

Sí, at.js 2.x es compatible con A4T para SPA a través de la función `triggerView()`, ya que ha implementado Adobe Analytics y el servicio de ID de visitante de Experience Cloud. Consulte el diagrama siguiente con descripciones paso a paso.

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
| [Segmentación automática](/help/c-activities/auto-target/auto-target-to-optimize.md) | No |
| [Personalización automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md) | No |
| [Recommendations](/help/c-recommendations/recommendations.md) | No |

**Si instalamos at.js 2.x e implementamos `triggerView()` en nuestras páginas, ¿cómo ejecutamos actividades A/B de la segmentación automática si el VEC de SPA no la admite?**

Si desea utilizar actividades A/B de Segmentación automática puede mover todas las acciones que se ejecutan al evento de Carga de página en el VEC. Pase el ratón sobre cada acción y haga clic en el botón [!UICONTROL Mover al evento de Carga de página]. Hecho esto, puede seleccionar Segmentación automática para el método de asignación de tráfico.

## Integraciones compatibles

| Integración | Compatible? |
| --- | --- |
| [Analytics for Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md) | Sí |
| [Audiencias de Experience Cloud](/help/c-integrating-target-with-mac/mmp.md) | Sí |
| [Atributos del cliente](/help/c-target/c-visitor-profile/working-with-customer-attributes.md) | Sí |
| [Fragmentos de experiencia de AEM](/help/c-experiences/c-manage-content/aem-experience-fragments.md) | Sí |

## Funciones compatibles.   {#supported-features}

| Función | Compatible? |
| --- | --- |
| [Workspaces y propiedades](/help/administrating-target/c-user-management/property-channel/property-channel.md) | Sí |
| [Vínculos de control de calidad](/help/c-activities/c-activity-qa/activity-qa.md) | Sí |
| [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md) | No |
| [Código personalizado](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) | Sí |
| [Opciones de VEC](/help/c-experiences/c-visual-experience-composer/viztarget-options.md) | Todas |
| [Seguimiento de clics](/help/c-activities/r-success-metrics/click-tracking.md) | Sí |
| [Entrega de varias actividades](/help/c-experiences/c-visual-experience-composer/multipage-activity.md) | Sí |

## Configuración de entrega de páginas para el VEC de SPA {#page-delivery-settings}

La configuración de [!UICONTROL Entrega de páginas] permite establecer reglas para determinar cuándo se debe calificar y ejecutar una actividad de Target para una audiencia determinada.

Para acceder a las opciones de [!UICONTROL Entrega de páginas] desde el flujo de trabajo de creación guiada de actividades del VEC, desde el paso **[!UICONTROL Experiencias]**, haga clic en **[!UICONTROL Configurar]** (icono de engranaje) > **[!UICONTROL Entrega de páginas]**.

![Cuadro de diálogo Opciones de Entrega de páginas](/help/c-experiences/assets/page-delivery.png)

Por ejemplo, según se define en la configuración [!UICONTROL Entrega de páginas] que se muestra arriba, una actividad de Target se califica y se ejecuta cuando un visitante aterriza directamente en `https://www.adobe.com` *o* cuando un visitante aterriza en cualquier dirección URL que contenga `https://www.adobe.com/products`. Esto funciona perfectamente para cualquier aplicación de varias páginas en la que cada interacción con la página invoca una recarga de página, para la cual at.js recupera las actividades que cumplen con la URL a la que va el usuario.

Sin embargo, como los SPA funcionan de forma diferente, la configuración de [!UICONTROL Entrega de páginas] debe estar plantearse de tal manera que todas las acciones deban aplicarse a las vistas tal como se define en la actividad del VEC de SPA.

### Ejemplo de uso

Analice este ejemplo de uso:

![Panel Modificaciones del VEC SPA](/help/c-experiences/assets/page-delivery-example.png)

Se han realizado los cambios siguientes:

* Se ha cambiado el color de fondo en la vista de Inicio, que se encuentra en la dirección URL: [/#/](https://target.enablementadobe.com/react/demo/#/)https://target.enablementadobe.com/react/demo/#/.
* Se ha cambiado el color del botón en la vista Productos, que se encuentra en la dirección URL: [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products).

Con el ejemplo anterior en mente, lo que sucedería cuando establecemos la configuración [!UICONTROL Entrega de páginas] para que solo incluya: [https://target.enablementadobe.com/react/demo/#/](https://target.enablementadobe.com/react/demo/#/) en un SPA con at.js 2.*x*?

![Cuadro de diálogo Entrega de páginas](/help/c-experiences/assets/spa-page-delivery.png)

La siguiente ilustración muestra el flujo de Target: carga de página en at.js 2.*x*:

![Flujo de Target: Solicitud de carga de página de at.js 2.0](/help/c-experiences/assets/page-load-request.png)

**Recorrido del usuario número 1**

* Un usuario navega directamente a [https://target.enablementadobe.com/react/demo/#/](https://target.enablementadobe.com/react/demo/#/).
* at.js 2.*x*  realiza una consulta a Edge para ver si hay alguna actividad que se deba ejecutar para la URL: [https://target.enablementadobe.com/react/demo/#/](https://target.enablementadobe.com/react/demo/#/).
* En el paso 6, Target Edge devuelve las acciones para la vista Inicio y Productos para que se almacenen en la caché del explorador.

**Resultado**: El usuario ve el color de fondo verde en la vista Inicio. Cuando el usuario navega a [](https://target.enablementadobe.com/react/demo/#/products)https://target.enablementadobe.com/react/demo/#/products, el color de fondo azul del botón se ve porque la acción se almacena en la caché del explorador en la vista Productos.

Nota: El usuario que navega a [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products) no déclencheur una carga de página.

**Recorrido del usuario número 2**

* Un usuario navega directamente a [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products).
* at.js 2.*x*  realiza una consulta a Edge para ver si hay alguna actividad que se deba ejecutar para la URL: [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products).
* No hay actividades cualificadas para [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products).
* Debido a que no hay actividades cualificadas, no hay acciones ni vistas que almacenar en caché para at.js 2.*x* para activarse.

**Resultado**: Aunque haya definido `triggerView()` para la vista Productos y haya realizado una acción en la vista Productos a través del SPA de VEC, no verá la acción esperada, ya que no creó ninguna regla que incluya [](https://target.enablementadobe.com/react/demo/#/products)https://target.enablementadobe.com/react/demo/#/products en la configuración de Entrega de páginas.

### Práctica recomendada

Puede ver que la administración del recorrido del usuario puede resultar bastante difícil, ya que los usuarios pueden aterrizar en cualquier URL de su SPA y navegar a cualquier otra página. Por lo tanto, es mejor especificar una regla de publicación de página que incluya la dirección URL base para que incluya todo el SPA. De este modo, no tiene que pensar en todos los recorridos y trayectos que un usuario podría desarrollar para llegar a una página en la que desee mostrar una prueba A/B o una actividad de segmentación de experiencias (XT).

Por ejemplo, para resolver el problema anterior, podemos especificar la dirección URL base en la configuración de Entrega de páginas de esta forma:

![Cuadro de diálogo Entrega de páginas](/help/c-experiences/assets/conclusion.png)

Esto garantiza que cuando un visitante aterrice en la SPA y navegue a la página principal o a la vista de página verá las acciones aplicadas.

Ahora, cada vez que agregue una acción a una Vista en el VEC de SPA, le mostraremos el siguiente mensaje emergente para recordarle que tenga en cuenta las reglas de [!UICONTROL Entrega de páginas].

![Mensaje de configuración de Entrega de páginas](/help/c-experiences/assets/pop-up-message.png)

Este mensaje aparece cuando agrega la primera acción a una Vista para cada nueva actividad que cree. Este mensaje garantiza que todos los miembros de su organización aprendan a aplicar correctamente estas reglas de [!UICONTROL Entrega de páginas].

## Vídeo de formación: Uso del VEC para SPA en Adobe Target

>[!VIDEO](https://video.tv.adobe.com/v/26249)

Consulte [Uso del Compositor de experiencias visuales para aplicaciones de una sola página (SPA VEC) en Adobe Target](https://helpx.adobe.com/target/kt/using/visual-experience-composer-for-single-page-applications-feature-video-use.html) para obtener más información.
