---
keywords: periodo de tiempo;fecha de inicio;fecha de fin;fechas de inicio/fin;intervalo de tiempo;programación de Target;partición por semana;partición por día;partición
description: Aprenda a utilizar las fechas y horas de inicio y finalización para aproximarse a los usuarios que visitan el sitio durante un lapso de tiempo específico.
title: ¿Puedo segmentar visitantes que visitan mi sitio en momentos específicos?
feature: Audiences
exl-id: 814d545d-baee-4f8b-a2ed-ed68fceaeb7f
source-git-commit: 0e4698935b90cc0236abe6a47a6183c7fd2a7b20
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 35%

---

# [!UICONTROL Time Frame]

Puede añadir fechas y horas de inicio y finalización en [!DNL Adobe Target] para dirigirse a los usuarios que visiten el sitio durante un lapso de tiempo específico. También puede establecer opciones de Partición por semana y día para crear patrones recurrentes en la segmentación de audiencia.

Por ejemplo, con el [función de audiencias combinadas ad hoc](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5), puede dirigirse a las personas que gastan poco con contenido específico durante los tres días previos al Black Friday y otro contenido después del Black Friday.

1. En el [!DNL Target] interfaz, haga clic en **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Asigne un nombre a la audiencia y añada una descripción opcional.
1. Arrastrar y soltar **[!UICONTROL Time Frame]** en el panel de audience builder.

   ![imagen target_timeframe_dialog](assets/target_timeframe_dialog.png)

1. Especifique el [!UICONTROL Start] y [!UICONTROL End] fechas y horas para la audiencia.

   Deje en blanco la fecha de inicio para empezar a dirigirse a su audiencia siguiendo la programación de la actividad. Deje en blanco la fecha de fin para continuar dirigiéndose a su audiencia hasta la fecha y hora de fin de la actividad.

   También puede dejar en blanco tanto la fecha de inicio como la de fin. Esta funcionalidad permite utilizar la misma audiencia en varias actividades (sin realizar una copia de la audiencia) mientras controla las fechas de inicio y finalización en el nivel de actividad.

   >[!NOTE]
   >
   >Tenga en cuenta lo siguiente:
   >
   >* La zona horaria de las fechas de inicio/fin aparece como GMT +/-NN:NN, donde NN:NN es la diferencia con respecto a la zona GMT. Refleja la zona horaria de la cuenta, no la del visitante. Por ejemplo, la zona horaria de California sería GMT -08:00.
   >
   >* [!DNL Target] Las audiencias de hora no tienen en cuenta los cambios del horario de verano (DST). Debe volver a guardar las audiencias manualmente para tener en cuenta los cambios de DST.

1. (Condicional) Haga clic en **[!UICONTROL Set frequency]** para establecer patrones recurrentes, incluidos los días de las semanas y las horas.

   ![División por semana y día](assets/week_and_day_parting.png)

   Podría usar [!UICONTROL Frequency] opciones, por ejemplo, para mostrar una opción &quot;Chatear ahora&quot; a los visitantes solo durante los días y las horas laborables de su centro de llamadas.

   Seleccione uno o varios días de la semana y luego defina las horas de inicio y fin. Clic **[!UICONTROL Add frequency]** para especificar otros patrones si lo desea.

   >[!NOTE]
   >
   >La zona horaria de [!UICONTROL Week and Day Parting] aparece como GMT +/- NN:NN, donde NN:NN es la diferencia con respecto a la zona GMT, y refleja la zona horaria de la cuenta, no la del visitante. Por ejemplo, la zona horaria de California para el horario de verano del Pacífico sería GMT -07:00.

1. (Opcional) Configure reglas adicionales para la audiencia.

   Si lo desea, puede repetir el paso 5 con cada regla.

1. Haga clic en **[!UICONTROL Done]**.

## Vídeo de formación: Creación de audiencias ![Distintivo Información general](/help/main/assets/overview.png)

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear audiencias
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)
