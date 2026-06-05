---
keywords: perfil del visitante;segmentar el perfil del visitante;
description: Aprenda a crear audiencias en  [!DNL Adobe Target]  para segmentar visitantes que cumplan parámetros de perfil específicos como visitante nuevo o recurrente, afinidad de la categoría y más.
title: ¿Puedo Segmentar Visitantes Que Cumplan Parámetros De Perfil Específicos?
feature: Audiences
exl-id: aca45b80-660d-4b8e-a0d7-84627b8fd77b
TQID: https://experienceleague.adobe.com/lGNJLzHHa7aBUY3ZzJUU-9I8aPNsZgye1zmnN2mGHc4
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 250
ht-degree: 36%

---

# Perfil del visitante

Cree audiencias en [!DNL Adobe Target] para segmentar visitantes que cumplan parámetros de perfil específicos.

1. En la interfaz [!DNL Target], haga clic en **[!UICONTROL Audiencias]** > **[!UICONTROL Crear audiencia]**.
1. Asigne un nombre a la audiencia y añada una descripción opcional.
1. Arrastre y suelte **[!UICONTROL Perfil del visitante]** en el panel del generador de audiencias.

1. Haga clic en **[!UICONTROL Seleccionar]** y, a continuación, elija una de estas opciones:

   ![imagen target_visitor_profile](assets/target_visitor_profile.png)

   Los parámetros de perfil de visitante se pasan a través del mbox (perfil). Puede segmentar visitantes nuevos o recurrentes, o bien incluir todos los usuarios.

   * [!UICONTROL Nuevo visitante]
   * [!UICONTROL Visitante que regresa]
   * [!UICONTROL En otras pruebas]
   * [!UICONTROL No Está En Otras Pruebas]
   * [!UICONTROL Primera página de la sesión]
   * [!UICONTROL No es la primera página de la sesión]
   * [!UICONTROL Afinidad de la categoría]

   Se crea un perfil de visitante en la memoria perimetral local para cada llamada a mbox con el nuevo `mboxPC`. Después de 30 minutos de inactividad, el perfil se guarda en la base de datos [!DNL Target] y es accesible desde otros perímetros.

   Cuando el visitante de un sitio inicia sesión en la mitad de la sesión y obtiene un `3rdpartyId`, todos los atributos de perfil cargados previamente y asociados a `3rdPartyId` están disponibles de inmediato.

   Puede segmentar parámetros personalizados de perfil y parámetros `user.`. Elija el parámetro que quiera usar para segmentar la actividad. Si el parámetro deseado no se muestra, un mbox no ha activado el parámetro.

1. (Opcional) Configure reglas adicionales para la audiencia.
1. Haga clic en **[!UICONTROL Finalizado]**.

## Vídeo de formación: Creación de audiencias ![Distintivo de información general](/help/main/assets/overview.png)

Este vídeo contiene información sobre el uso de las categorías de audiencias.

* Crear públicos
* Definir categorías de audiencias

>[!VIDEO](https://video.tv.adobe.com/v/17392)
