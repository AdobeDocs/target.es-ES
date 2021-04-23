---
keywords: Target;informes;configuración de informes;pedidos extremos;valores extremos
description: Aprenda a excluir valores extremos para que no afecten a los informes de Adobe [!DNL Target] de modo que algunos pedidos inusuales no afecten a los resultados de la actividad.
title: ¿Cómo se excluyen los valores extremos en los informes?
feature: Informes
exl-id: fd2d0c18-62c0-41e0-800c-b2ae123f0e74
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 72%

---

# Excluir valores extremos

Puede excluir valores extremos para que no afecten a los informes de [!DNL Adobe Target] de modo que algunos pedidos inusuales no afecten a los resultados de su actividad. Un ejemplo de pedido inusual puede ser el caso de un entrenador que compre uniformes para todo un equipo en lugar de compradores que compren uniformes de forma individual.

>[!NOTE]
>
>El indicador [!UICONTROL Excluir valores extremos] se aplica a las actividades con tipos de métrica de ingresos y participación.

Los valores extremos se marcan automáticamente en función de las reglas descritas a continuación. Puede alternar entre ver y excluir los valores extremos de los informes. Los valores extremos de una actividad se excluirán cuando la actividad se haya ejecutado durante una hora o cuando se hayan realizado 15 pedidos, lo que suceda antes.

Un valor se considera extremo si cuenta con más de 3 desviaciones estándares +/- del valor de pedido promedio según los datos del último mes (hasta el momento en el que se realizó el cálculo).

Por ejemplo, el filtro de valores extremos a menudo resulta útil cuando se usa RPV. RPV combina valor de pedido promedio y tasa de conversión, y a menudo expone la volatilidad de esas métricas. Si usa RPV y determina que los pedidos no parecen estar distribuidos normalmente, podría ver resultados más normales al aplicar el filtro de pedidos extremos.

Cuando se marca un valor como extremo, su valor se reemplaza por el valor de pedido promedio de la experiencia para el último mes, excluidos los extremos. El pedido también se marca como extremo en el informe [!UICONTROL Detalles del pedido] y en la descarga de CSV para resultados diarios.

**Para excluir valores extremos de los informes:**

1. Abra una actividad que incluya tipos de métrica de ingresos o participación y, después, haga clic en la pestaña **[!UICONTROL Informes]**.
1. Haga clic en el icono de engranaje para mostrar el cuadro de diálogo **[!UICONTROL Settings]**.

   ![Resultado del paso](assets/exclude_extreme_values.png)

1. Deslice la opción **[!UICONTROL Excluir valores extremos]** hasta la posición &quot;activada&quot; o &quot;desactivada&quot;, según sus preferencias.
1. Haga clic en **[!UICONTROL Guardar]**.
