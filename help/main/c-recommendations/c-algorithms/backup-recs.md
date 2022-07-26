---
keywords: recomendación;copia de seguridad;copia;seguridad
description: Aprenda a utilizar recomendaciones de copia de seguridad en Adobe [!DNL Target] Recommendations. La recomendación que no tiene suficientes artículos recomendados muestra los resultados del algoritmo de copia de seguridad.
title: ¿Cómo utilizo una recomendación de copia de seguridad en Recommendations?
feature: Recommendations
exl-id: 070aa8ef-5691-4106-b5cf-45eb9f6f334c
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 82%

---

# ![PREMIUM](/help/main/assets/premium.png) Usar una recomendación de copia de seguridad

Si utiliza la función de recomendación de copia de seguridad en Adobe Target, cualquier recomendación que no tenga suficientes artículos recomendados no mostrará el contenido predeterminado. En vez de eso, las recomendaciones mostrarán los resultados del algoritmo de copia de seguridad.

Si no utiliza una recomendación de copia de seguridad, y si una recomendación no contiene suficientes artículos para llenar la presentación, el sistema mostrará al usuario contenido predeterminado.

>[!NOTE]
>
>La información adicional se incluye en el [Sección de contenido de Crear criterios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content) , incluida una matriz que explica los resultados que se observarán al usar la variable [!UICONTROL Representación parcial de diseño] y [!UICONTROL Mostrar copia de seguridad de Recommendations] opciones juntas o por separado.

La función de recomendación de copia de seguridad siempre utiliza los artículos más vistos del sitio para llenar los espacios restantes después de utilizar los datos del algoritmo. Por ejemplo, la plantilla está configurada para mostrar cinco artículos recomendados y usted usa el algoritmo *Afinidades de compra*. Sin embargo, solamente tendrá suficientes datos para llenar dos de los cinco espacios, de modo que la función de recomendación de copia de seguridad llena los otros tres espacios con los artículos más vistos.

Las recomendaciones de copia de seguridad se eligen al azar entre los 500 productos más vistos del sitio. El período de tiempo de los datos para las recomendaciones de copia de seguridad es de una semana.

Los 500 resultados más vistos se ordenan secuencialmente y luego se dividen en grupos de 20. Los segmentos se publican en orden, pero los resultados dentro de cada segmento se asignan aleatoriamente y se devuelven a la página. Si los usuarios actualizan la página, se les presentan resultados nuevos y aleatorios. Si el conjunto de resultados de la unión de la recopilación y las reglas de filtrado es menor que 20, se seleccionará aleatoriamente de la colección.

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

Si se habilita el procesamiento parcial de diseño (consulte   [La configuración de Content ](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)) no está activada y no se muestra la plantilla, por tanto se mostrará la recomendación de copia de seguridad o el contenido predeterminado en su lugar.
