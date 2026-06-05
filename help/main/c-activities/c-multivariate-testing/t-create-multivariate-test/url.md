---
keywords: Pruebas multivariable;URL de actividad
description: Aprenda a especificar la dirección URL de la actividad que determina la página que se usa en la prueba y que se abre cuando se diseña la actividad [!UICONTROL Prueba multivariable] con [!DNL Adobe Target].
title: ¿Cuál es la dirección URL de actividad en una actividad de [!UICONTROL prueba multivariable] (MVT)?
feature: Multivariate Tests
exl-id: 336169ae-7c8b-4fd5-9b1c-0bd3e9524425
TQID: https://experienceleague.adobe.com/oQKwrlZ95XKEKSJIUiWqXXo9AJJzCb20gfS1rtwGImM
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 298
ht-degree: 38%

---

# Dirección URL de actividad

La dirección URL de actividad determina la página que se usa en la [!UICONTROL prueba multivariada] (MVT) y que se abre cuando se diseña la prueba en [!DNL Adobe Target].

1. Cuando se le pida durante la [creación de la actividad](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md), indique la dirección URL de la actividad. Escriba la dirección URL completa (incluido `https://`) y haga clic en **[!UICONTROL Crear]**.

   >[!NOTE]
   >
   >[!DNL Target] no diferencia entre los protocolos URL ([!DNL https] y [!DNL http]). Como resultado, [!DNL `https://www.adobe.com`] y [!DNL `http://www.adobe.com`] coinciden.

   De manera predeterminada, [!UICONTROL Compositor de experiencias visuales] (VEC) abre la página que se ha especificado en [Configuración del Compositor de experiencias visuales](/help/main/administrating-target/visual-experience-composer-set-up.md). Puede especificar una página diferente durante la creación de la actividad.

1. (Condicional) Para mostrar una página diferente después de que se abra el VEC, haga clic en el icono **[!UICONTROL Configurar]**, seleccione **[!UICONTROL Entrega de páginas]** y, a continuación, especifique la dirección URL.

1. (Condicional) Haga clic en **[!UICONTROL Agregar regla]** para agregar más páginas o secciones a la actividad.

   Las reglas adicionales pueden basarse en cualquiera de los siguientes aspectos:

   * [!UICONTROL  URL]
   * [!UICONTROL Dominio]
   * [!UICONTROL Ruta]
   * [!UICONTROL Fragmento almohadilla (#)]
   * [!UICONTROL Consulta]
   * [!UICONTROL Personalizado]

   Se pueden unir reglas adicionales a la dirección URL de la actividad con AND u OR. Todas las reglas que agregue se evalúan entre sí con AND.

   Haga clic en **[!UICONTROL Guardar]** cuando haya finalizado.

>[!NOTE]
>
>Si escribe una dirección URL de un sitio que no incluye el código JavaScript [!DNL Target], no podrá seleccionar elementos de página.
>
>De manera predeterminada, el VEC no permite realizar cambios en elementos que contengan JavaScript, como banners giratorios. Puede desactivar **[!UICONTROL Representar con JavaScript]** si quiere modificar estos elementos con el [!UICONTROL compositor de experiencias visuales].

>[!NOTE]
>
>Si cambia la dirección URL después de realizar cambios en una página para una o más experiencias, la experiencia se restablecerá con la nueva página y se perderán los cambios que haya realizado.
