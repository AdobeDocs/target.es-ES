---
keywords: parámetros personalizados;parámetros personalizados de target;targetpageparams;segmentación de parámetros mbox
description: Obtenga información sobre cómo pasar parámetros personalizados a [!DNL Adobe Target] para su uso en audiencias.
title: ¿Puedo segmentar visitantes en función de parámetros personalizados?
feature: Audiences
exl-id: f0669888-6b9e-4738-9ed4-0418ea56fffa
source-git-commit: 1383088bb2f6be0432e6f140400d8723048c8530
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 43%

---

# Parámetros personalizados

Los parámetros personalizados son parámetros de mbox en [!DNL Adobe Target]. Si pasa algún parámetro de mbox a mboxes, o usa el `targetPageParams` función, esos parámetros aparecen aquí para su uso en audiencias.

Para obtener más información, consulte [Pase de parámetros a un mbox global](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/global-mbox/pass-parameters-to-global-mbox.html?lang=es){target=_blank}.

Al crear una audiencia personalizada basada en un parámetro de mbox, `mboxParameter` ya no le pide que especifique un valor para `mboxName`. El nombre del mbox es ahora opcional. Este cambio le permite usar parámetros de varios mboxes o hacer referencia a un parámetro que aún no se haya registrado en el perímetro.

1. En la interfaz de [!DNL Target], haga clic en **[!UICONTROL Audiencias]** > **[!UICONTROL Crear audiencia]**.
1. Asigne un nombre a la audiencia y añada una descripción opcional.
1. Arrastrar y soltar **[!UICONTROL Personalizado]** en el Generador de audiencias.

   Para seleccionar el parámetro deseado:

   * Al crear una audiencia, seleccione un nombre de parámetro en la lista, empiece a escribir los primeros caracteres del nombre de parámetro deseado o escriba el nombre completo del parámetro deseado.
   * Si recuerda el nombre del mbox, pero no el nombre del parámetro, utilice el [!UICONTROL Filtrar por] lista desplegable para filtrar un mbox conocido que pase el parámetro deseado.

   Con ninguno de estos métodos existe vínculo entre el mbox y el parámetro. La audiencia funciona según el parámetro en todos los mboxes que pasan dicho parámetro.

   >[!NOTE]
   >
   >El mbox que seleccione en la variable [!UICONTROL Filtrar por] la lista desplegable no se guarda al crear la actividad. Esta opción le permite filtrar los parámetros en función del mbox seleccionado.

   Si edita una audiencia existente, el criterio de filtrado se muestra con el nombre de mbox que se suministró durante la creación.

1. Elija un evaluador:

   * Contiene (sin distinción de mayúsculas y minúsculas)
   * No contiene (sin distinción de mayúsculas y minúsculas)
   * Es igual a
   * No es igual a
   * Es mayor que
   * Es mayor que o igual a
   * Es menor que
   * Es menor que o igual a
   * El parámetro está presente
   * El parámetro no está presente
   * El valor del parámetro está presente
   * El valor del parámetro no está presente
   * El parámetro o valor no está presente
   * Empiece por
   * Finaliza con

   ![Audiencia de parámetros personalizados](assets/custom.png)

1. Introduzca cada valor en una línea nueva
1. (Opcional) Configure reglas adicionales para la audiencia.
1. Haga clic en **[!UICONTROL Finalizado]**.

La [tarjeta emergente de detalles de definición](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) de la audiencia muestra el nombre del parámetro en la sección Reglas. **** No hay ninguna referencia al mbox utilizado para el filtrado.

>[!NOTE]
>
>Para audiencias personalizadas creadas antes de [!DNL Target] Versión 18.5.1 (22 de mayo de 2018), los nombres de mbox no se muestran en la tarjeta emergente de definición de la audiencia. Vuelva a guardar la audiencia personalizada para obtener el nombre de mbox que se mostrará en la tarjeta.

## Consideraciones {#considerations}

* Las audiencias y actividades se evalúan para un mbox específico. Por ejemplo, si el mbox global pasa un determinado parámetro pero el mbox regional no, la actividad o la audiencia orientada a ese parámetro no será calificada para el mbox regional.
* La segmentación no se evalúa en parámetros de mbox internos como mboxPC, mboxSession, mbox3rdPartyId, mboxMCSDID, mboxMCAVID, mboxMCGVID, mboxCount, mboxId y mboxVersion.

## Vídeo de formación: Creación de audiencias ![Distintivo de tutorial](/help/main/assets/tutorial.png)

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear audiencias
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)
