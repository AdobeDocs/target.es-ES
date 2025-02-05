---
keywords: Target;informes;configuración de informes;pedidos extremos;valores extremos
description: Aprenda a excluir los valores extremos para que no afecten a los informes en el Adobe  [!DNL Target] , de modo que algunos pedidos inusuales no afecten a los resultados de la actividad.
title: ¿Cómo se excluyen los valores extremos en los informes?
feature: Reports
exl-id: fd2d0c18-62c0-41e0-800c-b2ae123f0e74
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 64%

---

# Excluir valores extremos

Puede excluir los valores extremos de los informes que se ven afectados en [!DNL Adobe Target], de modo que algunos pedidos inusuales no afecten a los resultados de la actividad. Un ejemplo de pedido inusual puede ser el caso de un entrenador que compre uniformes para todo un equipo en lugar de compradores que compren uniformes de forma individual.

>[!NOTE]
>
>El indicador [!UICONTROL Exclude Extreme Values] se aplica solamente a las actividades con [!UICONTROL Revenue] y [!UICONTROL Engagement] tipos de métrica.

Los valores extremos se marcan automáticamente en función de las reglas descritas a continuación. Puede alternar entre ver y excluir los valores extremos de los informes. Los valores extremos de una actividad se excluirán cuando la actividad se haya ejecutado durante una hora o cuando se hayan realizado 15 pedidos, lo que suceda antes.

Un valor se considera extremo si cuenta con más de 3 desviaciones estándares +/- del valor de pedido promedio según los datos del último mes (hasta el momento en el que se realizó el cálculo).

Por ejemplo, el filtro de valores extremos a menudo resulta útil cuando se usa RPV. RPV combina valor de pedido promedio y tasa de conversión, y a menudo expone la volatilidad de esas métricas. Si usa RPV y determina que los pedidos no parecen estar distribuidos normalmente, podría ver resultados más normales al aplicar el filtro de pedidos extremos.

Cuando se marca un valor como extremo, su valor se reemplaza por el valor de pedido promedio de la experiencia para el último mes, excluidos los extremos. El orden también se marca como extremo en el informe [!UICONTROL Order Details] y en la descarga CSV para obtener resultados diarios.

**Para excluir valores extremos de los informes:**

1. Abra una actividad que incluya [!UICONTROL Revenue] o [!UICONTROL Engagement] tipos de métrica y luego haga clic en la ficha **[!UICONTROL Reports]**.
1. Haga clic en el icono Configuración de informes ( ![icono Configuración de informes](/help/main/assets/icons/Setting.svg) ) para mostrar el cuadro de diálogo **[!UICONTROL Settings]**.

1. Deslice el botón de alternancia **[!UICONTROL Exclude Extreme Values]** a la posición &quot;activado&quot; u &quot;desactivado&quot;, según desee.
1. Haga clic en **[!UICONTROL Save]**.
