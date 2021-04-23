---
keywords: periodo de tiempo;fecha de inicio;fecha de fin;fechas de inicio/fin;intervalo de tiempo;programación de Target;partición por semana;partición por día;partición
description: Aprenda a utilizar las fechas y horas de inicio y finalización para dirigirse a los usuarios que visitan el sitio durante un intervalo de tiempo específico. También puede establecer las opciones de Partición por semana y día .
title: ¿Puedo [!DNL Target] Visitantes que visitan mi sitio en momentos específicos?
feature: Audiencias
exl-id: 814d545d-baee-4f8b-a2ed-ed68fceaeb7f
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 89%

---

# Periodo de tiempo

Puede añadir fechas y horas de inicio y fin para dirigirse a los usuarios que visitan el sitio durante un periodo de tiempo determinado. También puede establecer opciones de Partición por semana y día para crear patrones recurrentes en la segmentación de audiencia.

Por ejemplo, con las [funciones de audiencias combinadas específicas](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5), puede dirigirse a las personas que gastan poco para mostrarles contenido específico durante los tres días anteriores al Black Friday y otro contenido después del Black Friday.

1. En la interfaz de [!DNL Target], haga clic en **[!UICONTROL Audiencias]** > **[!UICONTROL Crear audiencia]**.
1. Ponga un nombre a la audiencia.
1. Haga clic en **[!UICONTROL Agregar regla]** > **[!UICONTROL Periodo de tiempo]**.

   ![](assets/target_timeframe_dialog.png)

1. Indique las fechas y horas de inicio y fin de la audiencia.

   Deje en blanco la fecha de inicio para empezar a dirigirse a su audiencia siguiendo la programación de la actividad. Deje en blanco la fecha de fin para continuar dirigiéndose a su audiencia hasta la fecha y hora de fin de la actividad.

   También puede dejar en blanco tanto la fecha de inicio como la de fin. Esto le permite utilizar la misma audiencia en diferentes actividades (sin hacer ninguna copia de la audiencia), mientras controla las fechas de inicio y de fin en el nivel de actividad.

   >[!NOTE]
   >
   >La zona horaria de las fechas de inicio/fin aparece como GMT +/-NN:NN, donde NN:NN es la diferencia con respecto a la zona GMT. Refleja la zona horaria de la cuenta, no la del visitante. Por ejemplo, la zona horaria de California sería GMT -08:00.

1. (Condicional) Haga clic en **[!UICONTROL Partición por semana y día]** para establecer patrones recurrentes, incluyendo los días de las semanas y las horas.

   ![División por semana y día](assets/week_and_day_parting.png)

   Las opciones de Partición por semana y día se pueden usar, por ejemplo, para mostrar la opción “Chatear ahora” a los visitantes solo durante los días y las horas laborables de su centro de llamadas.

   Seleccione uno o varios días de la semana y luego defina las horas de inicio y fin. Haga clic en **[!UICONTROL Añadir más]** para especificar otros patrones si lo desea.

   >[!NOTE]
   >
   >La zona horaria de [!UICONTROL División por semana y día] aparece como GMT +/- NN:NN, donde NN:NN es la diferencia con respecto a la zona GMT, y refleja la zona horaria de la cuenta, no la del visitante. Por ejemplo, la zona horaria de California sería GMT -08:00.

1. (Opcional) Haga clic en **[!UICONTROL Agregar regla]** y configure reglas adicionales para la audiencia.

   Si quiere, puede repetir el paso 5 con cada regla.

1. Haga clic en **[!UICONTROL Guardar]**.

## Vídeo de formación: Creación de audiencias ![Distintivo de información general](/help/assets/overview.png)

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear audiencias
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)
