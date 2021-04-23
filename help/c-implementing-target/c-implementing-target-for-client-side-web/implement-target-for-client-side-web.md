---
keywords: implementar;implementación;at.js;sdk web de adobe experience platform;sdk web de aep
description: Aprenda a implementar la biblioteca JavaScript de Adobe [!DNL Target] for client-side web using the Adobe Experience Platform Web SDK  (AEP Web SDK) or the [!DNL Target] at.js.
title: ¿Cómo puedo implementar [!DNL Target] para la web del lado del cliente?
feature: 'at.js '
role: Developer
exl-id: 34c1e39b-acae-4547-b67f-584bcd59913f
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 17%

---

# Información general: implementar [!DNL Target] para la web del lado del cliente

En una implementación del lado del cliente de [!DNL Adobe Target], [!DNL Target] envía las experiencias asociadas a una actividad directamente al explorador del cliente. El explorador decide qué experiencia mostrar y lo hace. Con una implementación del lado del cliente, se puede utilizar un editor WYSIWYG, el [Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) o una interfaz no visual, el [Compositor de experiencias basadas en formularios](/help/c-experiences/form-experience-composer.md), para crear experiencias de actividad y personalización.

Para implementar [!DNL Adobe Target] en el lado del cliente, debe utilizar una de las siguientes bibliotecas JavaScript:

* [SDK web de Adobe Experience Platform](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)
* [Biblioteca JavaScript de at.js de Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)

>[!IMPORTANT]
>
>**Fin de vida útil de mbox.js**: Desde el 31 de marzo de 2021,  [!DNL Adobe Target] no es compatible con la biblioteca mbox.js . Después del 31 de marzo de 2021, todas las llamadas realizadas desde mbox.js producirán errores y afectarán a las páginas que tengan actividades [!DNL Target] ejecutándose al servir contenido predeterminado. Recomendamos que todos los clientes migren a la versión más reciente de la nueva [!DNL Adobe Experience Platform Web SDK] o la biblioteca JavaScript at.js antes de esta fecha para evitar cualquier problema potencial con sus sitios.
>
>* **SDK** web de Adobe Experience Platform: El  [!UICONTROL SDK web de ] Adobe Experience Platform le permite interactuar con los distintos servicios de  [!DNL Experience Cloud] (incluido  [!DNL Target]) a través de la red Adobe Experience Edge. Si decide migrar al [!DNL Adobe Experience Platform Web SDK], consulte [Qué es el SDK web de Adobe Experience Platform](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) en la *Guía del SDK web*.
   >
   >
* **at.js**: La biblioteca JavaScript at.js proporciona muchas ventajas con respecto a mbox.js. Entre otros beneficios, at.js mejora los tiempos de carga de página en implementaciones web, mejora la seguridad y proporciona mejores opciones de implementación en aplicaciones de una sola página. Si decide migrar a at.js, consulte [Cómo funciona At.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) y [Adobe Target Skills Builder: Chat del desarrollador, migre mbox.js de Adobe Target a at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
>
>
Aunque actualmente se admite mbox.js (hasta el 31 de marzo de 2021), no se han proporcionado actualizaciones de características a esta biblioteca desde julio de 2017. Al trasladar a todos los clientes al [!UICONTROL Adobe Experience Platform Web SDK] o at.js, nuestros ingenieros y personal de asistencia técnica podrán proporcionarle nuevas funciones y ofrecerle el soporte que espera de Adobe.
