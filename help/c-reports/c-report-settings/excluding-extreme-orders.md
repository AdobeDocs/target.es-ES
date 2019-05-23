---
description: Puede excluir valores extremos para no afecten a los informes, de forma que algunos pedidos inusuales no afecten a los resultados de su actividad. Un ejemplo de pedido inusual puede ser el caso de un entrenador que compre uniformes para todo un equipo en lugar de compradores que compren uniformes de forma individual.
keywords: Target;informes;configuración de informes;pedidos extremos;valores extremos
seo-description: Puede excluir valores extremos para no afecten a los informes, de forma que algunos pedidos inusuales no afecten a los resultados de su actividad. Un ejemplo de pedido inusual puede ser el caso de un entrenador que compre uniformes para todo un equipo en lugar de compradores que compren uniformes de forma individual.
seo-title: Excluir valores extremos
solution: Target
title: Excluir valores extremos
topic: Premium
uuid: bb151b54-09ef-40b5-bc04-95c61b761f5a
translation-type: tm+mt
source-git-commit: 74a6f402bc0c9dae6f89cbdb632d7dbc53743593

---


# Excluir valores extremos{#exclude-extreme-values}

Puede excluir valores extremos para no afecten a los informes, de forma que algunos pedidos inusuales no afecten a los resultados de su actividad. Un ejemplo de pedido inusual puede ser el caso de un entrenador que compre uniformes para todo un equipo en lugar de compradores que compren uniformes de forma individual.

>[!NOTE]
>
>El indicador [!UICONTROL Excluir valores extremos] se aplica a las actividades con tipos de métrica de ingresos y participación.

Los valores extremos se marcan automáticamente en función de las reglas descritas a continuación. Puede alternar entre ver y excluir los valores extremos de los informes. Los valores extremos de una actividad se excluirán cuando la actividad se haya ejecutado durante una hora o cuando se hayan realizado 15 pedidos, lo que suceda antes.

Un valor se considera extremo si cuenta con más de 3 desviaciones estándares +/- del valor de pedido promedio según los datos del último mes (hasta el momento en el que se realizó el cálculo).

Por ejemplo, el filtro de valores extremos a menudo resulta útil cuando se usa RPV. RPV combina valor de pedido promedio y tasa de conversión, y a menudo expone la volatilidad de esas métricas. Si usa RPV y determina que los pedidos no parecen estar distribuidos normalmente, podría ver resultados más normales al aplicar el filtro de pedidos extremos.

Cuando se marca un valor como extremo, su valor se reemplaza por el valor de pedido promedio de la experiencia para el último mes, excluidos los extremos. El pedido se marca también como extremo en el informe Detalles del pedido y en la descarga en formato CSV para los resultados diarios.

**Para excluir valores extremos de los informes:**

1. Abra una actividad que incluya tipos de métrica de ingresos o participación y, después, haga clic en la pestaña **[!UICONTROL Informes]**.
1. Haga clic en el icono de engranaje para mostrar las opciones de [!UICONTROL Configuración de informes.]

   ![Resultado del paso](assets/exclude_extreme_values.png)

1. Active o desactive la opción **[!UICONTROL Excluir valores extremos]** según prefiera.
1. Haga clic en **[!UICONTROL Guardar configuración]**.
