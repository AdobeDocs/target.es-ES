---
keywords: perfil del visitante;segmentar el perfil del visitante;
description: Aprenda a crear audiencias en  [!DNL Adobe Target]  para segmentar visitantes que cumplan parámetros de perfil específicos como visitante nuevo o recurrente, afinidad de la categoría y más.
title: ¿Puedo Segmentar Visitantes Que Cumplan Parámetros De Perfil Específicos?
feature: Audiences
exl-id: aca45b80-660d-4b8e-a0d7-84627b8fd77b
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 35%

---

# Perfil del visitante

Cree audiencias en [!DNL Adobe Target] para segmentar visitantes que cumplan parámetros de perfil específicos.

1. En la interfaz [!DNL Target], haga clic en **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Asigne un nombre a la audiencia y añada una descripción opcional.
1. Arrastre y suelte **[!UICONTROL Visitor Profile]** en el panel del generador de audiencias.

1. Haga clic en **[!UICONTROL Select]** y luego seleccione una de las siguientes opciones:

   ![imagen target_visitor_profile](assets/target_visitor_profile.png)

   Los parámetros de perfil de visitante se pasan a través del mbox (perfil). Puede segmentar visitantes nuevos o recurrentes, o bien incluir todos los usuarios.

   * [!UICONTROL New Visitor]
   * [!UICONTROL Returning Visitor]
   * [!UICONTROL In Other Tests]
   * [!UICONTROL Not In Other Tests]
   * [!UICONTROL First Page of Session]
   * [!UICONTROL Not First Page of Session]
   * [!UICONTROL Category Affinity]

   Se crea un perfil de visitante en la memoria perimetral local para cada llamada a mbox con el nuevo `mboxPC`. Después de 30 minutos de inactividad, el perfil se guarda en la base de datos [!DNL Target] y es accesible desde otros perímetros.

   Cuando el visitante de un sitio inicia sesión en la mitad de la sesión y obtiene un `3rdpartyId`, todos los atributos de perfil cargados previamente y asociados a `3rdPartyId` están disponibles de inmediato.

   Puede segmentar parámetros personalizados de perfil y parámetros `user.`. Elija el parámetro que quiera usar para segmentar la actividad. Si el parámetro deseado no se muestra, un mbox no ha activado el parámetro.

1. (Opcional) Configure reglas adicionales para la audiencia.
1. Haga clic en **[!UICONTROL Done]**.

## Vídeo de formación: Creación de audiencias ![Distintivo de información general](/help/main/assets/overview.png)

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear audiencias
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)
