---
keywords: perfil del visitante;segmentar el perfil del visitante;
description: Obtenga información sobre cómo crear audiencias en [!DNL Adobe Target] para segmentar visitantes que cumplan parámetros de perfil específicos como visitante nuevo o recurrente, afinidad de la categoría, etc.
title: ¿Puedo Segmentar Visitantes Que Cumplan Parámetros De Perfil Específicos?
feature: Audiences
exl-id: aca45b80-660d-4b8e-a0d7-84627b8fd77b
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 46%

---

# Perfil del visitante

Creación de audiencias en [!DNL Adobe Target] para segmentar visitantes que cumplan parámetros de perfil específicos.

1. En la interfaz de [!DNL Target], haga clic en **[!UICONTROL Audiencias]** > **[!UICONTROL Crear audiencia]**.
1. Asigne un nombre a la audiencia y añada una descripción opcional.
1. Arrastrar y soltar **[!UICONTROL Perfil del visitante]** en el panel de audience builder.

1. Haga clic en **[!UICONTROL Seleccionar]** y, a continuación, elija una de estas opciones:

   ![imagen target_visitor_profile](assets/target_visitor_profile.png)

   Los parámetros de perfil de visitante se pasan a través del mbox (perfil). Puede segmentar visitantes nuevos o recurrentes, o bien incluir todos los usuarios.

   * [!UICONTROL Nuevo visitante]
   * [!UICONTROL Visitante que regresa]
   * [!UICONTROL En otras pruebas]
   * [!UICONTROL No está en otras pruebas]
   * [!UICONTROL Primera página de la sesión]
   * [!UICONTROL No es primera página de la sesión]
   * [!UICONTROL Afinidad de la categoría]

   Se crea un perfil de visitante en la memoria perimetral local para cada llamada a mbox con el nuevo `mboxPC`. Después de 30 minutos de inactividad, el perfil se guarda en la [!DNL Target] y es accesible desde otros perímetros.

   Cuando el visitante de un sitio inicia sesión a mitad de la sesión y obtiene un `3rdpartyId`, todos los atributos de perfil cargados previamente y vinculados a `3rdPartyId` están disponibles inmediatamente.

   Puede segmentar parámetros personalizados de perfil y parámetros `user.`. Elija el parámetro que quiera usar para segmentar la actividad. Si el parámetro deseado no se muestra, un mbox no ha activado el parámetro.

1. (Opcional) Configure reglas adicionales para la audiencia.
1. Haga clic en **[!UICONTROL Finalizado]**.

## Vídeo de formación: Creación de audiencias ![Distintivo Información general](/help/main/assets/overview.png)

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear audiencias
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)
