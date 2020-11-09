---
keywords: Implementation;mbox.js non javascript;mbox;adbox
description: Utilice un adbox para enviar imágenes en una implementación fuera del sitio, mediante Adobe Target.
title: Creación de un adbox para una imagen mediante Adobe Target
feature: email implementation
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 77%

---


# Creación de un AdBox para una imagen{#create-an-adbox-for-an-image}

Use un adbox para enviar imágenes en una implementación fuera del sitio mediante Adobe Target.

Un AdBox es lo mismo que un mbox, con la diferencia de que se controla mediante una dirección URL en lugar de con JavaScript. Los AdBoxes se crean con una dirección URL de AdBox especial que carga un mbox de “publicidad” (o AdBox) en su cuenta de Adobe. Use este AdBox en lugar del mbox en las actividades. Use la URL de AdBox en vez de una referencia de imagen directa para correo electrónico y otras implementaciones no basadas en JavaScript.

Si desea obtener ayuda para decidir la configuración adecuada, consulte   [Implementaciones no basadas en JavaScript](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4).

1. Cree la dirección URL del AdBox:

   ```
   https://myClientCode.tt.omtrdc.net/m2/myClientCode/ubox/
   image?mbox=emailHeroImage123_320x200&
   mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fimg%2Flogo%2Egif
   ```

   * Donde `myClientCode` es el código de cliente de la empresa. El código de cliente de su compañía está por completo en minúscula y carece de caracteres especiales.

      Your client code is available at the top of the [!UICONTROL Administation > Implementation] page of the [!DNL Target] interface.

   * Donde `image` es el tipo de llamada. En este caso, se trata de una imagen.

   * Donde `emailHeroImage123_320x200` es el nombre del AdBox.

   * Donde `http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fimg%2Flogo%2Egif` es el contenido predeterminado del mbox. Debe ser una imagen.

      Debe tener codificación de dirección URL y ser una referencia absoluta. You can use the [HTML URL Encoding Reference](https://www.w3schools.com/tags/ref_urlencode.asp) to quickly encode your URLs.

1. Cree [Ofertas de redireccionamiento](/help/c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94) para cada imagen alternativa.

   >[!NOTE]
   >
   >Los AdBox se deben cargar con una oferta de redireccionamiento o con la oferta de contenido predeterminado. El resto de tipos de oferta no funcionará. Como el AdBox es una dirección URL, solo puede mostrar las direcciones URL que recibe, por lo que solo funciona la oferta de redireccionamiento.

1. Cree la actividad.

   Consulte [Implementaciones no basadas en JavaScript](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4) para saber cuál es la configuración apropiada para alcanzar sus metas.
1. Lleve a cabo un control de calidad en la actividad.

   Se recomienda crear una página ficticia y confirmar que todas las experiencias, el contenido predeterminado y los informes se comportan del modo esperado en todos los tipos de navegador y en cualquier entorno.

1. Inicie la actividad.
