---
keywords: recomendación;copia de seguridad;copia;seguridad
description: Aprenda a utilizar las recomendaciones de copia de seguridad en Adobe [!DNL Target Recommendations].
title: ¿Cómo se usa una recomendación de copia de seguridad en  [!DNL Target Recommendations]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: 070aa8ef-5691-4106-b5cf-45eb9f6f334c
TQID: https://experienceleague.adobe.com/TziWJoAuEdCqa7uMTpX0O0InnlnjtbPXP-0wzQ-FCM0
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 533
ht-degree: 68%

---

# Usar una recomendación de copia de seguridad

Si usa la característica de recomendación de copia de seguridad de [!DNL Adobe Target], las recomendaciones que no tengan suficientes artículos recomendados no mostrarán el contenido predeterminado. En vez de eso, las recomendaciones mostrarán los resultados del algoritmo de copia de seguridad.

Si no utiliza una recomendación de copia de seguridad, y si una recomendación no contiene suficientes artículos para llenar la presentación, el sistema mostrará al usuario contenido predeterminado.

>[!NOTE]
>
>Se incluye información adicional en la sección [Contenido del tema Crear criterios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content), incluida una matriz que explica los resultados que observará al usar las opciones [!UICONTROL Procesamiento de diseño parcial] y [!UICONTROL Mostrar recomendaciones de copia de seguridad] juntas o por separado.

La función de recomendación de copia de seguridad siempre utiliza los elementos más vistos del sitio para rellenar las ranuras restantes después de utilizar los datos del algoritmo. Por ejemplo, la plantilla está configurada para mostrar cinco artículos recomendados y usted usa el algoritmo *Afinidades de compra*. Sin embargo, solamente tendrá suficientes datos para llenar dos de los cinco espacios, de modo que la función de recomendación de copia de seguridad llena los otros tres espacios con los artículos más vistos.

Las recomendaciones de copia de seguridad se eligen al azar entre los 500 productos más vistos del sitio. El período de tiempo de los datos para las recomendaciones de copia de seguridad es de una semana.

Los 500 resultados más vistos se ordenan secuencialmente y luego se dividen en grupos de 20. Los segmentos se publican en orden, pero los resultados dentro de cada segmento se asignan aleatoriamente y se devuelven a la página. Si los usuarios actualizan la página, se les presentan resultados nuevos y aleatorios. Si el conjunto de resultados de la unión de la colección y las reglas de filtrado es menor que 20, selecciona aleatoriamente de la colección.

Este proceso de agrupamiento significa que las recomendaciones de respaldo se muestran en el siguiente orden:

1. Muestra los 20 elementos más vistos, aleatorios, después
1. Muestra los siguientes 20 elementos más vistos, aleatorios, después
1. Muestra los siguientes 20 elementos más vistos, aleatorios,
1. etcétera

Sin la acumulación de recomendaciones de copia de seguridad, habría sido posible mostrar el 499º artículo más visto, seguido del 200º más visto, seguido del 380º más visto, y así sucesivamente. El proceso de ordenamiento asegura que los artículos más vistos se recomiendan primero.

>[!NOTE]
>
>Si agrupa los artículos en catálogos, las recomendaciones de copia de seguridad generadas para cada algoritmo dentro de la recomendación también usan el catálogo, por lo que únicamente los artículos del catálogo se incluirán en la recomendación de copia de seguridad.

Cualquier artículo excluido por las reglas de exclusión globales no se presenta como recomendación de copia de seguridad.

Las recomendaciones de copia de seguridad están activadas de forma predeterminada y rellenan los espacios extra de una plantilla con una selección aleatoria de los artículos más populares del sitio.

Los duplicados se eliminan de los lotes de recomendaciones.

Por lo general, el uso de recomendaciones de copia de seguridad forma parte de un análisis hecho con el equipo de implementación durante su configuración inicial. Si desea cambiar la configuración de las recomendaciones de copia de seguridad después de la implementación, póngase en contacto con el administrador de su cuenta.

Si Habilitar procesamiento parcial de diseño (consulte [Configuración de contenido](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)) no está habilitado y la plantilla no se muestra, se mostrará la recomendación de copia de seguridad o el contenido predeterminado en su lugar.
