---
keywords: Target;informes;configuración de informes;pedidos extremos;valores extremos
description: Obtenga información sobre cómo excluir valores extremos de los informes que se ven afectados por Adobes [!DNL Target] por lo tanto, algunos pedidos inusuales no afectan a los resultados de su actividad.
title: ¿Cómo se excluyen los valores extremos en los informes?
feature: Reports
exl-id: fd2d0c18-62c0-41e0-800c-b2ae123f0e74
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 72%

---

# Excluir valores extremos

Puede excluir valores extremos de los informes que se vean afectados en [!DNL Adobe Target] por lo tanto, algunos pedidos inusuales no afectan a los resultados de su actividad. Un ejemplo de pedido inusual puede ser el caso de un entrenador que compre uniformes para todo un equipo en lugar de compradores que compren uniformes de forma individual.

>[!NOTE]
>
>El indicador [!UICONTROL Excluir valores extremos] se aplica a las actividades con tipos de métrica de ingresos y participación.

Los valores extremos se marcan automáticamente en función de las reglas descritas a continuación. Puede alternar entre ver y excluir los valores extremos de los informes. Los valores extremos de una actividad se excluirán cuando la actividad se haya ejecutado durante una hora o cuando se hayan realizado 15 pedidos, lo que suceda antes.

Un valor se considera extremo si cuenta con más de 3 desviaciones estándares +/- del valor de pedido promedio según los datos del último mes (hasta el momento en el que se realizó el cálculo).

Por ejemplo, el filtro de valores extremos a menudo resulta útil cuando se usa RPV. RPV combina valor de pedido promedio y tasa de conversión, y a menudo expone la volatilidad de esas métricas. Si usa RPV y determina que los pedidos no parecen estar distribuidos normalmente, podría ver resultados más normales al aplicar el filtro de pedidos extremos.

Cuando se marca un valor como extremo, su valor se reemplaza por el valor de pedido promedio de la experiencia para el último mes, excluidos los extremos. El pedido también se marca como extremo en la variable [!UICONTROL Detalles del pedido] y en la descarga de CSV para obtener resultados diarios.

**Para excluir valores extremos de los informes:**

1. Abra una actividad que incluya tipos de métrica de ingresos o participación y, después, haga clic en la pestaña **[!UICONTROL Informes]**.
1. Haga clic en el icono de engranaje para mostrar el **[!UICONTROL Configuración]** Cuadro de diálogo.

   ![Resultado del paso](assets/exclude_extreme_values.png)

1. Deslice el **[!UICONTROL Excluir valores extremos]** alterne a la posición &quot;on&quot; o &quot;off&quot; según desee.
1. Haga clic en **[!UICONTROL Guardar]**.
