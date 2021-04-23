---
keywords: parámetros personalizados;parámetros personalizados de target;targetpageparams;segmentación de parámetros mbox
description: Aprenda a pasar parámetros personalizados a Adobe [!DNL Target] para usarlos en audiencias.
title: ¿Puedo  [!DNL Target] Visitantes en función de parámetros personalizados?
feature: Audiencias
exl-id: f0669888-6b9e-4738-9ed4-0418ea56fffa
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 85%

---

# Parámetros personalizados

Los parámetros personalizados son parámetros mbox. Si pasa algún parámetro mbox a mboxes, o usa la función targetPageParams, ese parámetro aparece aquí para su uso en audiencias.

Para obtener más información, consulte [Pasar parámetros a un mbox global](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md).

Al crear una audiencia personalizada basada en un parámetro de mbox, `mboxParameter` ya no le pide que especifique un valor para `mboxName`. El nombre del mbox es ahora opcional. Este cambio le permite usar parámetros de varios mboxes o hacer referencia a un parámetro que aún no se haya registrado en el perímetro.

1. En la interfaz de [!DNL Target], haga clic en **[!UICONTROL Audiencias]** > **[!UICONTROL Crear audiencia]**.
1. Ponga un nombre a la audiencia.
1. Haga clic en **[!UICONTROL Agregar regla]** > **[!UICONTROL Personalizado]**.

   Para seleccionar el parámetro deseado:

   * Cuando cree una nueva audiencia, seleccione un nombre de parámetro en la lista, empiece a escribir los primeros caracteres del nombre de parámetro deseado o escriba el nombre completo del parámetro.
   * Si recuerda el nombre del mbox pero no el del parámetro, utilice la casilla de verificación para filtrar en función de un mbox conocido que pase el parámetro deseado.

   Con ninguno de estos métodos existe vínculo entre el mbox y el parámetro. La audiencia funcionará sobre la base del parámetro en todos los mboxes que pasen dicho parámetro.

   Si edita una audiencia existente, el criterio de filtrado se muestra con el nombre de mbox que se suministró durante la creación.

1. Elija un evaluador:

   * Contiene (sin distinción de mayúsculas y minúsculas)
   * No contiene (sin distinción de mayúsculas y minúsculas)
   * Es igual a

   ![Audiencia de parámetros personalizados](/help/c-target/c-audiences/c-target-rules/assets/custom.png)

1. Introduzca cada valor en una línea nueva
1. (Opcional) Haga clic en **[!UICONTROL Agregar regla]** y configure reglas adicionales para la audiencia.
1. Haga clic en **[!UICONTROL Guardar]**.

La [tarjeta emergente de detalles de definición](/help/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) de la audiencia muestra el nombre del parámetro en la sección Reglas. No hay ninguna referencia al mbox utilizado para el filtrado.

>[!NOTE]
>
>Para audiencias personalizadas creadas antes de la versión 18.5.1 de Target (22 de mayo de 2018), los nombres de mbox no se mostrarán en la tarjeta emergente de definición de la audiencia. Debe volver a guardar la audiencia personalizada para obtener el nombre de mbox que se mostrará en la tarjeta.

## Consideraciones {#considerations}

* Las audiencias y actividades se evalúan para un mbox específico. Por ejemplo, si el mbox global pasa un determinado parámetro pero el mbox regional no, la actividad o la audiencia orientada a ese parámetro no será calificada para el mbox regional.
* La segmentación no se evalúa en parámetros de mbox internos, como mboxPC, mboxSession, mbox3rdPartyId, mboxMCSDID, mboxMCAVID, mboxMCGVID, mboxCount, mboxId y mboxVersion.

## Vídeo de formación: Creación de audiencias ![Distintivo del tutorial](/help/assets/tutorial.png)

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear audiencias
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)
