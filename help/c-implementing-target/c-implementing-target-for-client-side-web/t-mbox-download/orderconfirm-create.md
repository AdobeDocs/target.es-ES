---
keywords: order confirmation;orderConfirmPage
description: El mbox de confirmación de pedido registra los detalles de los pedidos que se realizan en su sitio web y permite generar informes según los ingresos y los pedidos. El mbox de confirmación de pedido también puede realizar algoritmos de recomendaciones, como “Las personas que compraron el producto X también han comprado el producto Y”.
title: 'Crear un mbox de confirmación de pedido: mbox.js'
feature: null
translation-type: tm+mt
source-git-commit: ae44c57c7b8767915fbbce4271a4b1858dd07efd
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 69%

---


# Crear un mbox de confirmación de pedido: mbox.js

El mbox de confirmación de pedido registra los detalles de los pedidos que se realizan en su sitio web y permite generar informes según los ingresos y los pedidos. El mbox de confirmación de pedido también puede realizar algoritmos de recomendaciones, como “Las personas que compraron el producto X también han comprado el producto Y”.

>[!IMPORTANT]
>
>**Fin de vida útil** de mbox.js: El 31 de marzo de 2021 ya no  [!DNL Adobe Target] admitirá la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas realizadas desde mbox.js generarán errores e impactarán en las páginas que tengan [!DNL Target] actividades ejecutándose al proporcionar contenido predeterminado.
>
>Se recomienda que todos los clientes migren a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o a la biblioteca JavaScript at.js antes de esta fecha para evitar cualquier problema potencial con sus sitios. Para obtener más información, consulte [Información general: implemente Destinatario para la Web del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

>[!NOTE]
>
>* Si los usuarios realizan compras en su sitio web, le recomendamos que implemente un mbox de confirmación de pedido aunque use los informes de Analytics para Target (A4T).
   >
   >
* También puede crear un mbox de confirmación de pedido para at.js 1.** utilizando el mismo método; sin embargo, se prefiere el  [!DNL at.js] método. Para obtener más información, consulte [Conversiones de seguimiento](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053).
   >
   >
* Si está utilizando at.js 2.*x*, ya no  `mboxCreate` se admite. Para la confirmación de pedidos con at.js 2.*x*, utilice las siguientes API relacionadas con el seguimiento:  [trackEvent()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) y  [sendNotifications()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md).


1. En la página de detalles del pedido, inserte el script de mbox siguiendo el modelo que aparece a continuación.
1. Reemplace las PALABRAS EN MAYÚSCULAS por valores dinámicos o estáticos del catálogo.

   >[!NOTE]
   >
   >Utilice la delimitación por comas para separar varios ID de producto.

   **Consejo:** También puede pasar información de pedidos a cualquier mbox (no necesita llamarse `orderConfirmPage`). De igual modo, es posible pasar información de pedido a varios mbox dentro de la misma campaña.

   ```
   <div class="mboxDefault"> 
      <!-- CONTENT TO SHOW IF NO OFFERS AVAILABLE. --> 
   </div> 
   <script type="text/javascript">    
      mboxCreate('orderConfirmPage', 
      'productPurchasedId=PRODUCT ID FROM YOUR ORDER PAGE, PRODUCT ID2, PRODUCT ID3', 
      'orderTotal=ORDER TOTAL FROM YOUR ORDER PAGE', 
      'orderId=ORDER ID FROM YOUR ORDER PAGE'); 
   </script> 
   ```

El mbox de confirmación de pedido utiliza los siguientes parámetros:

| Parámetro | Descripción |
|--- |--- |
| `orderId` | Valor único para identificar un pedido de recuento de conversión.<br>El `orderId` debe ser único. Los pedidos duplicados se ignoran en los informes. |
| `orderTotal` | Valor monetario de la compra.<br>No pase el símbolo de moneda. Use un punto (no una coma) para indicar valores decimales. |
| `productPurchasedId` (Opcional) | Lista de ID de productos comprados en el pedido, separados por comas.<br>Estos ID de productos se muestran en el informe de auditoría para admitir un análisis de informe adicional. |