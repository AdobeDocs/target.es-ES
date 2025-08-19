---
keywords: audiencia;inclinación;atributo de perfil;comparar;comparación;crear audiencia;creación de audiencia
description: Obtenga información sobre cómo definir una audiencia para comparar dos atributos de perfil.
title: ¿Puedo comparar dos atributos de perfil para usarlos en audiencias?
feature: Audiences
exl-id: 033e90f1-5a05-4fce-a520-68826860a908
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 51%

---

# Crear una audiencia de comparación de atributos de perfil

Defina una audiencia en [!DNL Adobe Target] para comparar dos atributos de perfil para su [biblioteca de audiencias](/help/main/c-target/c-audiences/audiences.md) o en una [audiencia solo de actividad](/help/main/c-target/creating-activity-only-audience.md). Mediante operadores como mayor que, menor que o igual a, defina una audiencia que compare de forma dinámica el valor de dos atributos de perfil diferentes.

>[!NOTE]
>
>Esta funcionalidad solo está disponible para la categoría [[!UICONTROL Visitor Profile]](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E).

## Información general {#section_303CBC78194D49A2A004945D425441E1}

Las audiencias están definidas por reglas que determinan quién se incluye o excluye de una actividad de [!DNL Target]. Una definición de audiencia puede incluir múltiples reglas, cada una de las cuales puede incluir múltiples parámetros. Si una de las reglas que incluye usa la categoría [!UICONTROL Visitor Profile], puede definir una regla basada en el valor específico de un atributo de perfil de visitante o comparar el valor de ese atributo con otro atributo de perfil de visitante.

Por ejemplo, supongamos que trabaja para una empresa de muebles y ha cargado dos puntuaciones de tendencia de clientes en [!DNL Target]:

* Probabilidad de comprar mobiliario de comedor en los próximos 90 días
* Probabilidad de comprar mobiliario de salón en los próximos 90 días

Podría crear una audiencia definida como que la inclinación a comprar mobiliario de comedor es mayor que la inclinación a comprar mobiliario de salón. [!DNL Target] compararía dinámicamente las puntuaciones de inclinación de los comedores y las salas de estar de un visitante específico para determinar si ese visitante cumple los requisitos para esta audiencia.

Para obtener más información, consulte [Métodos para obtener datos en Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=es){target=_blank}.

## Crear una audiencia de comparación de atributos de perfil {#section_7A62FD47D5C74C3EBC3417ACDBB85013}

1. Haga clic en **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Asigne un nombre a la audiencia y añada una descripción opcional.
1. Arrastre y suelte **[!UICONTROL Visitor Profile]** en el panel del generador de audiencias.
1. En la lista desplegable **[!UICONTROL Visitor Profile]**, elija un atributo:

   ![Puntuación de propensión 1](assets/propensity_score_1.png)

1. Elija un evaluador:

   ![Puntuación de propensión 2](assets/propensity_score_2.png)

1. En la lista desplegable **[!UICONTROL Choose Comparison Type]**, elija **[!UICONTROL Attribute]**.

   El tipo de comparación &quot;valor estático&quot; permite comparar el atributo de perfil del visitante con valores específicos.

   ![Puntuación de propensión 3](assets/propensity_score_3.png)

   >[!NOTE]
   >
   >Si utiliza una de las categorías predeterminadas de perfil del visitante (por ejemplo, Nuevo visitante o Visitante que regresa), solo puede elegir la opción del valor estático. Las opciones de comparación dinámica no están disponibles para las categorías predeterminadas. Otros ejemplos en los que las opciones de comparación dinámica no están disponibles son “Primera página de la sesión”, “No está en otras pruebas”, “No es primera página de la sesión” y “Afinidad de la categoría”.

1. Elija el atributo adicional que desee comparar con su atributo inicial.

   ![imagen propensity_score_4](assets/propensity_score_4.png)

1. Haga clic en **[!UICONTROL Done]**.

## Vídeo de formación ![Distintivo de información general](/help/main/assets/overview.png) {#section_3BB8DBF3418F4520B3E274B6F40AF8F3}

Vea el siguiente vídeo para obtener más información y ver un caso en el que podría utilizar esta función:

>[!VIDEO](https://video.tv.adobe.com/v/328109?captions=spa)
