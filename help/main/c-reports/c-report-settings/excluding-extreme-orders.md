---
keywords: Target;informes;configuración de informes;pedidos extremos;valores extremos
description: Aprenda a excluir los valores extremos de los informes que se ven afectados en Adobe [!DNL Target] para que algunos pedidos inusuales no afecten a los resultados de la actividad.
title: ¿Cómo se excluyen los valores extremos en los informes?
feature: Reports
exl-id: fd2d0c18-62c0-41e0-800c-b2ae123f0e74
TQID: https://experienceleague.adobe.com/yQtG4u-sLVJ66PezWW9ZgmY8ZuK177m-hLdQq-zlmfI
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 332
ht-degree: 62%

---

# Excluir valores extremos

Puede excluir los valores extremos de los informes que se ven afectados en [!DNL Adobe Target], de modo que algunos pedidos inusuales no afecten a los resultados de la actividad. Un ejemplo de pedido inusual puede ser el caso de un entrenador que compre uniformes para todo un equipo en lugar de compradores que compren uniformes de forma individual.

>[!NOTE]
>
>El indicador [!UICONTROL Excluir valores extremos] se aplica solo a las actividades con tipos de métrica [!UICONTROL Ingresos] y [!UICONTROL Participación].

Los valores extremos se marcan automáticamente en función de las reglas descritas a continuación. Puede alternar entre ver y excluir los valores extremos de los informes. Los valores extremos de una actividad se excluirán cuando la actividad se haya ejecutado durante una hora o cuando se hayan realizado 15 pedidos, lo que suceda antes.

Un valor se considera extremo si cuenta con más de 3 desviaciones estándares +/- del valor de pedido promedio según los datos del último mes (hasta el momento en el que se realizó el cálculo).

Por ejemplo, el filtro de valores extremos a menudo resulta útil cuando se usa RPV. RPV combina valor de pedido promedio y tasa de conversión, y a menudo expone la volatilidad de esas métricas. Si usa RPV y determina que los pedidos no parecen estar distribuidos normalmente, podría ver resultados más normales al aplicar el filtro de pedidos extremos.

Cuando se marca un valor como extremo, su valor se reemplaza por el valor de pedido promedio de la experiencia para el último mes, excluidos los extremos. El pedido también se marca como extremo en el informe [!UICONTROL Detalles del pedido] y en la descarga de CSV para obtener resultados diarios.

**Para excluir valores extremos de los informes:**

1. Abra una actividad que incluya tipos de métrica [!UICONTROL Ingresos] o [!UICONTROL Participación] y, a continuación, haga clic en la ficha **[!UICONTROL Informes]**.
1. Haga clic en el icono Configuración de informes ( ![icono Configuración de informes](/help/main/assets/icons/Setting.svg) ) para mostrar el cuadro de diálogo **[!UICONTROL Configuración]**.

1. Deslice el botón de alternancia **[!UICONTROL Excluir valores extremos]** a la posición &quot;activado&quot; u &quot;desactivado&quot;, según desee.
1. Haga clic en **[!UICONTROL Guardar]**.
