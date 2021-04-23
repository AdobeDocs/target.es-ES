---
keywords: Implementación;mbox.js sin javascript;mbox;AdBox
description: Utilice un AdBox para ofrecer imágenes en una implementación externa mediante Adobe Target. Un AdBox es como un mbox, pero se controla mediante una dirección URL en lugar de JavaScript.
title: ¿Cómo se crea un AdBox para una imagen?
feature: Implementación del correo electrónico
role: Developer
exl-id: c66cfbc2-633a-46f2-8d9f-dbd18f7e880e
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 73%

---

# Creación de un AdBox para una imagen

Utilice un AdBox para ofrecer imágenes en una implementación externa mediante Adobe Target.

Un AdBox es lo mismo que un mbox, con la diferencia de que se controla mediante una dirección URL en lugar de con JavaScript. Los AdBoxes se crean con una dirección URL de AdBox especial que carga un mbox de “publicidad” (o AdBox) en su cuenta de Adobe. Use este AdBox en lugar del mbox en las actividades. Use la URL de AdBox en vez de una referencia de imagen directa para correo electrónico y otras implementaciones no basadas en JavaScript.

Si desea obtener ayuda para decidir la configuración adecuada, consulte   [Implementaciones no basadas en JavaScript](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4).

1. Cree la dirección URL del AdBox:

   ```
   https://myClientCode.tt.omtrdc.net/m2/myClientCode/ubox/
   image?mbox=emailHeroImage123_320x200&
   mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fimg%2Flogo%2Egif
   ```

   * Donde `myClientCode` es el código de cliente de la empresa. El código de cliente de su compañía está por completo en minúscula y carece de caracteres especiales.

      El código de cliente se encuentra disponible en la parte superior de la página [!UICONTROL Administration > Implementation] de la interfaz [!DNL Target].

   * Donde `image` es el tipo de llamada. En este caso, se trata de una imagen.

   * Donde `emailHeroImage123_320x200` es el nombre del AdBox.

   * Donde `http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fimg%2Flogo%2Egif` es el contenido predeterminado del mbox. Debe ser una imagen.

      Debe tener codificación de dirección URL y ser una referencia absoluta. Puede utilizar la [Referencia de codificación de la URL HTML](https://www.w3schools.com/tags/ref_urlencode.asp) para codificar rápidamente sus URL.

1. Cree [Ofertas de redireccionamiento](/help/c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94) para cada imagen alternativa.

   >[!NOTE]
   >
   >Los AdBox se deben cargar con una oferta de redireccionamiento o con la oferta de contenido predeterminado. El resto de tipos de oferta no funcionará. Como el AdBox es una dirección URL, solo puede mostrar las direcciones URL que recibe, por lo que solo funciona la oferta de redireccionamiento.

1. Cree la actividad.

   Consulte [Implementaciones no basadas en JavaScript](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4) para saber cuál es la configuración apropiada para alcanzar sus metas.
1. Lleve a cabo un control de calidad en la actividad.

   Se recomienda crear una página ficticia y confirmar que todas las experiencias, el contenido predeterminado y los informes se comportan del modo esperado en todos los tipos de navegador y en cualquier entorno.

1. Inicie la actividad.
