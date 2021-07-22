---
keywords: perfil del visitante;segmentar el perfil del visitante;
description: Aprenda a crear audiencias en [!DNL Adobe Target] para dirigirse a visitantes que cumplan parámetros de perfil específicos, como visitante nuevo o que regresa, afinidad de la categoría, etc.
title: ¿Puedo Dirigirme A Visitantes Que Cumplen Parámetros De Perfil Específicos?
feature: Audiencias
exl-id: aca45b80-660d-4b8e-a0d7-84627b8fd77b
source-git-commit: b46966a8dbb2ff6d2efbfb8f126783f750c2f08c
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 47%

---

# Perfil del visitante

Cree audiencias en [!DNL Adobe Target] para segmentar visitantes que cumplan parámetros de perfil específicos.

1. En la interfaz de [!DNL Target], haga clic en **[!UICONTROL Audiencias]** > **[!UICONTROL Crear audiencia]**.
1. Asigne un nombre a la audiencia y añada una descripción opcional.
1. Arrastre y suelte **[!UICONTROL Perfil del visitante]** en el panel del generador de audiencias.

1. Haga clic en **[!UICONTROL Seleccionar]** y, a continuación, elija una de estas opciones:

   ![](assets/target_visitor_profile.png)

   Los parámetros de perfil de visitante se pasan a través del mbox (perfil). Puede segmentar visitantes nuevos o recurrentes, o bien incluir todos los usuarios.

   * [!UICONTROL Nuevo visitante]
   * [!UICONTROL Visitante que regresa]
   * [!UICONTROL En otras pruebas]
   * [!UICONTROL No está en otras pruebas]
   * [!UICONTROL Primera página de la sesión]
   * [!UICONTROL No es primera página de la sesión]
   * [!UICONTROL Afinidad de la categoría]

   Se crea un perfil de visitante en la memoria perimetral local para cada llamada a mbox con el nuevo `mboxPC`. Después de 30 minutos de inactividad, el perfil se guarda en la base de datos [!DNL Target] y se puede acceder a él desde otros perímetros.

   Cuando el visitante de un sitio inicia sesión en la mitad de la sesión y obtiene un `3rdpartyId`, todos los atributos de perfil cargados previamente y asociados al `3rdPartyId` quedan disponibles de forma inmediata.

   Puede segmentar parámetros personalizados de perfil y parámetros `user.`. Elija el parámetro que quiera usar para segmentar la actividad. Si el parámetro deseado no se muestra, un mbox no lo ha activado.

1. (Opcional) Configure reglas adicionales para la audiencia.
1. Haga clic en **[!UICONTROL Finalizado]**.

## Vídeo de formación: Creación de audiencias ![Distintivo de información general](/help/assets/overview.png)

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear audiencias
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)
