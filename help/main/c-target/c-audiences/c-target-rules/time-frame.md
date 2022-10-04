---
keywords: periodo de tiempo;fecha de inicio;fecha de fin;fechas de inicio/fin;intervalo de tiempo;programación de Target;partición por semana;partición por día;partición
description: Aprenda a utilizar las fechas y horas de inicio y finalización para dirigirse a los usuarios que visitan el sitio durante un intervalo de tiempo específico.
title: ¿Puedo segmentar Visitantes que Visiten Mi Sitio En Tiempos Específicos?
feature: Audiences
exl-id: 814d545d-baee-4f8b-a2ed-ed68fceaeb7f
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 44%

---

# Periodo de tiempo

Puede agregar fechas y horas de inicio y finalización en [!DNL Adobe Target] para dirigirse a los usuarios que visiten el sitio durante un intervalo de tiempo específico. También puede establecer opciones de Partición por semana y día para crear patrones recurrentes en la segmentación de audiencia.

Por ejemplo, si se usa la variable [característica de audiencias combinadas y ad-hoc](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5), puede dirigirse a las personas que gastan poco para mostrarles contenido específico durante los tres días anteriores al Black Friday y otro contenido después del Black Friday.

1. En la interfaz de [!DNL Target], haga clic en **[!UICONTROL Audiencias]** > **[!UICONTROL Crear audiencia]**.
1. Asigne un nombre a la audiencia y añada una descripción opcional.
1. Arrastrar y soltar **[!UICONTROL Periodo de tiempo]** en el panel del generador de audiencias.

   ![imagen target_timeframe_dialog](assets/target_timeframe_dialog.png)

1. Especifique la variable [!UICONTROL Inicio] y [!UICONTROL Fin] fechas y horas para la audiencia.

   Deje en blanco la fecha de inicio para empezar a dirigirse a su audiencia siguiendo la programación de la actividad. Deje en blanco la fecha de fin para continuar dirigiéndose a su audiencia hasta la fecha y hora de fin de la actividad.

   También puede dejar en blanco tanto la fecha de inicio como la de fin. Esta funcionalidad le permite utilizar la misma audiencia en varias actividades (sin hacer una copia de la audiencia) mientras controla las fechas de inicio y finalización en el nivel de actividad.

   >[!NOTE]
   >
   >La zona horaria de las fechas de inicio/fin aparece como GMT +/-NN:NN, donde NN:NN es la diferencia con respecto a la zona GMT. Refleja la zona horaria de la cuenta, no la del visitante. Por ejemplo, la zona horaria de California sería GMT -08:00.

1. (Condicional) Haga clic en **[!UICONTROL Configurar frecuencia]** para establecer patrones recurrentes, incluidos los días de las semanas y las horas.

   ![División por semana y día](assets/week_and_day_parting.png)

   Puede usar [!UICONTROL Frecuencia] , por ejemplo, para mostrar la opción &quot;Chatear ahora&quot; a los visitantes solo durante los días y las horas laborables de su centro de llamadas.

   Seleccione uno o varios días de la semana y luego defina las horas de inicio y fin. Haga clic en **[!UICONTROL Agregar frecuencia]** para especificar otros patrones, según desee.

   >[!NOTE]
   >
   >La zona horaria de [!UICONTROL División por semana y día] aparece como GMT +/- NN:NN, donde NN:NN es la diferencia con respecto a la zona GMT, y refleja la zona horaria de la cuenta, no la del visitante. Por ejemplo, la zona horaria de California para la hora del Pacífico se mostraría como GMT -07:00.

1. (Opcional) Configure reglas adicionales para la audiencia.

   Si lo desea, puede repetir el paso 5 con cada regla.

1. Haga clic en **[!UICONTROL Finalizado]**.

## Vídeo de formación: Creación de audiencias ![Distintivo Información general](/help/main/assets/overview.png)

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear audiencias
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)
