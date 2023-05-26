---
keywords: reglas de inclusión;criterios de inclusión;recomendaciones;promoción;promociones;filtrado dinámico;estático;filtro estático
description: Aprenda a introducir manualmente uno o más valores estáticos para filtrar con reglas de inclusión en Adobe [!DNL Target] Recommendations.
title: ¿Cómo Filtro Por Valores Estáticos En Las Actividades De Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 47%

---

# Filtro estático

Introduzca manualmente uno o más valores estáticos para filtrar con reglas de inclusión en [!DNL Adobe Target] [!DNL Recommendations].

Por ejemplo, recomendar solo contenido con una clasificación de Asociación de imágenes en movimiento (MPA) de &quot;G&quot; o &quot;PG&quot;.

Puede crear tantas reglas de inclusión como necesite. Las reglas de inclusión se unen mediante un operador Y. Deben cumplirse todas las reglas para incluir un artículo en una recomendación.

>[!NOTE]
>
>Si está familiarizado con el modo en que se configuraban las reglas de inclusión antes de la versión de Target 17.6.1 (junio de 2017), notará que algunas de las opciones y operadores han cambiado. Solo se muestran los operadores aplicables a la opción seleccionada y el nombre de algunos ha cambiado (“coincide” es ahora “es igual que”), de modo que la experiencia sea más coherente e intuitiva. Todas las reglas de inclusión creadas antes de esta versión se migran automáticamente a la nueva estructura. No es necesaria reestructuración alguna por su parte.

## Recomendar contenido con clasificación G o PG

Para crear una regla de inclusión con valores estáticos para recomendar contenido con una clasificación MPA de solo &quot;G&quot; o &quot;PG&quot; (excluir contenido &quot;R&quot; y &quot;NC17&quot;), puede crear las siguientes reglas de filtrado &quot;clasificación de película es igual a clasificación g&quot; y &quot;clasificación de película es igual a clasificación pg&quot;, como se muestra a continuación.

![ejemplo de clasificación de películas](/help/main/c-recommendations/c-algorithms/assets/movies.png)
