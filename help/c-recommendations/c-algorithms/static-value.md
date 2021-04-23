---
keywords: reglas de inclusión;criterios de inclusión;recomendaciones;promoción;promociones;filtrado dinámico;estático;filtro estático
description: Aprenda a introducir manualmente uno o más valores estáticos para filtrar con reglas de inclusión en Adobe [!DNL Target] Recommendations.
title: ¿Cómo Filtro Por Valores Estáticos En Las Actividades De Recommendations?
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 46%

---

# ![](/help/assets/premium.png) PREMIUMStatic Filter

Introduzca manualmente uno o más valores estáticos para filtrar con reglas de inclusión en [!DNL Adobe Target] [!DNL Recommendations].

Por ejemplo, recomendar solo contenido con una clasificación de Motion Picture Association (MPA) de &quot;G&quot; o &quot;PG&quot;.

Puede crear tantas reglas de inclusión como necesite. Las reglas de inclusión se unen mediante un operador Y. Deben cumplirse todas las reglas para incluir un artículo en una recomendación.

>[!NOTE]
>
>Si está familiarizado con el modo en que se configuraban las reglas de inclusión antes de la versión de Target 17.6.1 (junio de 2017), notará que algunas de las opciones y operadores han cambiado. Solo se muestran los operadores aplicables a la opción seleccionada y el nombre de algunos ha cambiado (“coincide” es ahora “es igual que”), de modo que la experiencia sea más coherente e intuitiva. Todas las reglas de inclusión creadas antes de esta versión se migran automáticamente a la nueva estructura. No es necesaria reestructuración alguna por su parte.

## Recomendar contenido clasificado como G o PG

Para crear una regla de inclusión con valores estáticos y recomendar contenido con una clasificación MPA de &quot;G&quot; o &quot;PG&quot; solamente (excluir contenido &quot;R&quot; y &quot;NC17&quot;), puede crear las siguientes reglas de filtrado &quot;clasificación de película es igual a g-rating&quot; y &quot;clasificación de película igual a pg-rating&quot;, como se muestra a continuación.

![ejemplo de clasificación de películas](/help/c-recommendations/c-algorithms/assets/movies.png)
