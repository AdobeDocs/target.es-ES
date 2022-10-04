---
keywords: audiencia;inclinación;atributo de perfil;comparar;comparación;crear audiencia;creación de audiencia
description: Aprenda a definir una audiencia para comparar dos atributos de perfil.
title: ¿Puedo comparar dos atributos de perfil para usarlos en las audiencias?
feature: Audiences
exl-id: 033e90f1-5a05-4fce-a520-68826860a908
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 59%

---

# Crear una audiencia de comparación de atributos de perfil

Defina una audiencia en [!DNL Adobe Target] para comparar dos atributos de perfil para su [Biblioteca de audiencias](/help/main/c-target/c-audiences/audiences.md) o en un [audiencia solo de actividad](/help/main/c-target/creating-activity-only-audience.md). Mediante operadores como mayor que, menor que o igual a, defina una audiencia que compare de forma dinámica el valor de dos atributos de perfil diferentes.

>[!NOTE]
>
>Esta funcionalidad solo está disponible para la categoría [[!UICONTROL Perfil de visitante]](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E).

## Información general {#section_303CBC78194D49A2A004945D425441E1}

Las audiencias están definidas por reglas que determinan quién se incluye o excluye de una actividad de [!DNL Target]. Una definición de audiencia puede incluir múltiples reglas, cada una de las cuales puede incluir múltiples parámetros. Si una de las reglas incluidas usa la variable [!UICONTROL Perfil del visitante] , puede definir una regla basada en el valor específico de un atributo de perfil del visitante o comparar el valor de dicho atributo con otro atributo de perfil del visitante.

Por ejemplo, supongamos que trabaja para una empresa de muebles y que ha cargado dos puntuaciones de inclinación del cliente en [!DNL Target]:

* Probabilidad de comprar mobiliario de comedor en los próximos 90 días
* Probabilidad de comprar mobiliario de salón en los próximos 90 días

Podría crear una audiencia definida como que la inclinación a comprar mobiliario de comedor es mayor que la inclinación a comprar mobiliario de salón. [!DNL Target]A continuación,  compara dinámicamente las puntuaciones de inclinación hacia comedor y salón de un visitante específico para determinar si el visitante entra o no en la audiencia.

Para obtener más información, consulte [Métodos para obtener los datos en Target](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/){target=_blank}.

## Crear una audiencia de comparación de atributos de perfil {#section_7A62FD47D5C74C3EBC3417ACDBB85013}

1. Haga clic en **[!UICONTROL Audiencias]** > **[!UICONTROL Crear audiencia]**.
1. Asigne un nombre a la audiencia y añada una descripción opcional.
1. Arrastrar y soltar **[!UICONTROL Perfil del visitante]** en el panel del generador de audiencias.
1. En la lista desplegable **[!UICONTROL Perfil del visitante]**, elija un atributo:

   ![Puntuación de propensión 1](assets/propensity_score_1.png)

1. Elija un evaluador:

   ![Puntuación de propensión 2](assets/propensity_score_2.png)

1. En la lista desplegable **[!UICONTROL Elegir tipo de comparación]**, seleccione **[!UICONTROL Atributo]**.

   El tipo de comparación &quot;valor estático&quot; le permite comparar su atributo de perfil del visitante con valores específicos.

   ![Puntuación de propensión 3](assets/propensity_score_3.png)

   >[!NOTE]
   >
   >Si utiliza una de las categorías predeterminadas de perfil del visitante (por ejemplo, Nuevo visitante o Visitante que regresa), solo puede elegir la opción de valor estático. Las opciones de comparación dinámica no están disponibles para las categorías predeterminadas. Otros ejemplos en los que las opciones de comparación dinámica no están disponibles son “Primera página de la sesión”, “No está en otras pruebas”, “No es primera página de la sesión” y “Afinidad de la categoría”.

1. Elija el atributo adicional que desee comparar con su atributo inicial.

   ![imagen propensity_score_4](assets/propensity_score_4.png)

1. Haga clic en **[!UICONTROL Finalizado]**.

## Vídeo de formación ![Distintivo Información general](/help/main/assets/overview.png) {#section_3BB8DBF3418F4520B3E274B6F40AF8F3}

Vea el siguiente vídeo para obtener más información y ver un caso en el que podría utilizar esta función:

>[!VIDEO](https://video.tv.adobe.com/v/23218/)
