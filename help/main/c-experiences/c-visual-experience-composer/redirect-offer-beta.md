---
kewords: redirect;redirect url;send to different page
description: Aprenda a utilizar la opción Redireccionar a dirección URL del Adobe  [!DNL Target]  cuando desee enviar al visitante a una página diferente en lugar de mostrar contenido en la misma página.
title: ¿Puedo redirigir una página a una dirección URL diferente?
feature: Visual Experience Composer (VEC)
hide: true
hidefromtoc: true
source-git-commit: f968ec45f015fa0b195007f5790b9efb743c8b65
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 66%

---

# Redireccionar a una dirección URL

Utilice la opción [!UICONTROL Redirect to URL] en [!DNL Adobe Target] cuando desee enviar al visitante a una página diferente en lugar de mostrar contenido en la misma página.

Es posible que tenga dos páginas completamente distintas para probarlas, en lugar de simplemente cambiar partes de contenido dentro de una página. En este caso, la prueba A/B compara la página A con la B. Configure una campaña de prueba A/B con dos experiencias: una que apunte a la página A predeterminada y otra que redirija a la página B. En el menú Acción de experiencia, que aparece al hacer clic en la etiqueta de carta para la experiencia, elija **[!UICONTROL Redirect to URL]** y especifique la dirección URL de la página B. La oferta está configurada para redirigir al visitante a una página diferente.

La oferta de redireccionamiento ejecuta código JavaScript para redirigir el navegador. Utiliza el `window.location.replace();`método de modo que la página desde la cual se redirige al visitante no se almacene en el historial del explorador. Esto permite que el visitante siga usando el botón de retorno del navegador.

Las ofertas de redireccionamiento tienen ciertas limitaciones:

* Para redireccionar ofertas en actividades que utilizan A4T, su implementación debe satisfacer ciertos requisitos mínimos. Además, hay información importante que debe conocer. Para obtener más información, consulte las [preguntas más frecuentes de A4T sobre las ofertas de redireccionamiento](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
* Cuando use el Compositor de experiencias basado en formularios, las ofertas de redireccionamiento no se deberían usar en mboxes que formen parte de la página. Una alternativa de redireccionamiento solo se debería usar desde una etiqueta de script que forme parte de la etiqueta del HTML `<head>`. Debería usar siempre la creación automática y establecer la oferta de redireccionamiento para el mbox global.

>[!NOTE]
>
>Si se desea pasar el valor de referente de la página de aterrizaje, se recomienda usar una oferta HTML en lugar de una oferta de redireccionamiento.

Para crear una oferta de redireccionamiento:

1. Cree una experiencia.
1. Desde el fotograma [!UICONTROL Experiences], haga clic en el icono **[!UICONTROL More Actions]** ( ![icono Más acciones](/help/main/assets/icons/MoreSmallList.svg) ) para obtener la experiencia deseada.
1. Haga clic en **[!UICONTROL Redirect to URL]**.
1. En el cuadro de diálogo Redirigir a dirección URL, escriba la dirección URL.
1. Si lo desea, seleccione la opción para incluir los parámetros de consulta actuales.

   Si se selecciona esta opción, cualquier carácter después de ? en la dirección URL del visitante se adjuntará a la dirección URL de redirección cuando se redireccione.

1. (Opcional) Crear reglas adicionales.

   Las reglas adicionales pueden basarse en cualquiera de los siguientes aspectos:

   * Dirección URL
   * Dominio
   * Ruta
   * Fragmento hash (#)
   * Consulta
   * Parámetro de mbox

   Se pueden unir reglas adicionales a la dirección URL de la actividad con Y u O. Todas las reglas que agregue se evalúan entre sí con Y.

## Problemas conocidos

* Las actividades de redirección en las implementaciones de at.js hacen que la dirección URL de vista previa entre en bucle (la oferta se suministra repetidamente). Puede utilizar el [Modo de control de calidad](/help/main/c-activities/c-activity-qa/activity-qa.md) para llevar a cabo la vista previa y el control de calidad. Este problema no afecta al suministro real de la oferta. (TGT-23019)
