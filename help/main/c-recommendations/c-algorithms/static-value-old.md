---
keywords: reglas de inclusión;criterios de inclusión;recomendaciones;promoción;promociones;filtrado dinámico;estático;filtro estático
description: Aprenda a escribir manualmente uno o más valores estáticos para filtrar mediante reglas de inclusión en Adobe [!DNL Target] Recommendations.
title: ¿Cómo Filtro Por Valores Estáticos En Las Actividades De Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 42%
---
# Filtro estático

Escriba manualmente uno o más valores estáticos para filtrar mediante reglas de inclusión en [!DNL Adobe Target] [!DNL Recommendations].

Por ejemplo, recomendar solo contenido con una clasificación de Asociación de imágenes en movimiento (MPA) de &quot;G&quot; o &quot;PG&quot;.

Puede crear tantas reglas de inclusión como necesite. Las reglas de inclusión se unen mediante un operador Y. Deben cumplirse todas las reglas para incluir un artículo en una recomendación.

>[!NOTE]
>
>Si está familiarizado con el modo en que se configuraban las reglas de inclusión antes de la versión de Target 17.6.1 (junio de 2017), notará que algunas de las opciones y operadores han cambiado. Solo se muestran los operadores aplicables a la opción seleccionada y el nombre de algunos ha cambiado (“coincide” es ahora “es igual que”), de modo que la experiencia sea más coherente e intuitiva. Todas las reglas de inclusión creadas antes de esta versión se migran automáticamente a la nueva estructura. No es necesaria reestructuración alguna por su parte.

## Recomendar contenido con clasificación G o PG

Para crear una regla de inclusión con valores estáticos para recomendar contenido con una clasificación MPA de solo &quot;G&quot; o &quot;PG&quot; (excluir contenido &quot;R&quot; y &quot;NC17&quot;), puede crear las siguientes reglas de filtrado &quot;clasificación de película es igual a clasificación g&quot; y &quot;clasificación de película es igual a clasificación pg&quot;, como se muestra a continuación.

![ejemplo de clasificación de películas](/help/main/c-recommendations/c-algorithms/assets/movies.png)
