---
description: El mbox de confirmación de pedido registra los detalles de los pedidos que se realizan en su sitio web y permite generar informes según los ingresos y los pedidos. El mbox de confirmación de pedido también puede realizar algoritmos de recomendaciones, como “Las personas que compraron el producto X también han comprado el producto Y”.
keywords: confirmación de pedido;orderConfirmPage
seo-description: El mbox de confirmación de pedido registra los detalles de los pedidos que se realizan en su sitio web y permite generar informes según los ingresos y los pedidos. El mbox de confirmación de pedido también puede realizar algoritmos de recomendaciones, como “Las personas que compraron el producto X también han comprado el producto Y”.
seo-title: 'Crear un mbox de confirmación de pedido: mbox.js'
solution: Target
subtopic: Primeros pasos
title: 'Crear un mbox de confirmación de pedido: mbox.js'
uuid: 001da2bd-2ccf-490b-ba84-ac9b9a2a5451
translation-type: tm+mt
source-git-commit: a2cdf35f37f2debdb4b6be13e2965989ee9a3f00

---


# Crear un mbox de confirmación de pedido: mbox.js{#create-an-order-confirmation-mbox-mbox-js}

El mbox de confirmación de pedido registra los detalles de los pedidos que se realizan en su sitio web y permite generar informes según los ingresos y los pedidos. El mbox de confirmación de pedido también puede realizar algoritmos de recomendaciones, como “Las personas que compraron el producto X también han comprado el producto Y”.

>[!NOTE]
>
>Si los usuarios realizan compras en su sitio web, le recomendamos que implemente un mbox de confirmación de pedido aunque use los informes de Analytics para Target (A4T).

>[!NOTE]
>
>También puede crear un mbox de confirmación de pedido para at.js utilizando el mismo método; sin embargo, se recomienda utilizar el método de [!DNL at.js]. Para obtener más información, consulte [Conversiones de seguimiento](../../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053).

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
| `productPurchasedId` (Opcional) | Lista de ID de productos comprados en el pedido, separados por comas. <br>Estos ID de productos se muestran en el informe de auditoría para admitir un análisis de informe adicional. |