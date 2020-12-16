---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;static;static filter
description: Introduzca manualmente uno o varios valores estáticos para filtrar mediante reglas de inclusión en Adobe Target Recommendations.
title: Filtrar por valores estáticos en reglas de inclusión en Adobe Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: f8311dbc91b74977a11dc9b97a70465ab4493b93
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 48%

---


# ![](/help/assets/premium.png) PREMIUMSfiltro estático

Especifique manualmente uno o varios valores estáticos para filtrar mediante reglas de inclusión en [!DNL Adobe Target] [!DNL Recommendations].

Por ejemplo, recomendar solo contenido con una clasificación de la Asociación de imágenes de movimiento (MPA) de &quot;G&quot; o &quot;PG&quot;.

Puede crear tantas reglas de inclusión como necesite. Las reglas de inclusión se unen mediante un operador Y. Deben cumplirse todas las reglas para incluir un artículo en una recomendación.

>[!NOTE]
>
>Si está familiarizado con el modo en que se configuraban las reglas de inclusión antes de la versión de Target 17.6.1 (junio de 2017), notará que algunas de las opciones y operadores han cambiado. Solo se muestran los operadores aplicables a la opción seleccionada y el nombre de algunos ha cambiado (“coincide” es ahora “es igual que”), de modo que la experiencia sea más coherente e intuitiva. Todas las reglas de inclusión creadas antes de esta versión se migran automáticamente a la nueva estructura. No es necesaria reestructuración alguna por su parte.

## Contenido recomendado con clasificación G o PG

Para crear una regla de inclusión con valores estáticos para recomendar contenido con una clasificación MPA de &quot;G&quot; o &quot;PG&quot; solamente (excluir contenido &quot;R&quot; y &quot;NC17&quot;), puede crear las siguientes reglas de filtrado &quot;clasificación de películas es igual a g-nominal&quot; y &quot;clasificación de películas igual a pg-rating&quot;, como se muestra a continuación.

![ejemplo de clasificación de películas](/help/c-recommendations/c-algorithms/assets/movies.png)

