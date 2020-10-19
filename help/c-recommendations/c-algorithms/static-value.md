---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;static;static filter
description: Introduzca manualmente uno o varios valores estáticos para filtrar mediante reglas de inclusión en Adobe Target Recommendations.
title: Filtrar por valores estáticos en reglas de inclusión en Adobe Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 75%

---


# ![Filtro estático PREMIUM](/help/assets/premium.png)

Introduzca manualmente uno o varios valores estáticos para filtrar mediante reglas de inclusión en Adobe Target Recommendations.

Por ejemplo, recomendar solo contenido con una clasificación MPAA de “G” o “PG”.

Operadores disponibles:

* igual a
* no es igual
* contiene
* no contiene
* comienza con
* termina con
* el valor está presente
* el valor no está presente
* es mayor o igual que
* es menor o igual que

>[!NOTE]
>
>Si está familiarizado con el modo en que se configuraban las reglas de inclusión antes de la versión de Target 17.6.1 (junio de 2017), notará que algunas de las opciones y operadores han cambiado. Solo se muestran los operadores aplicables a la opción seleccionada y el nombre de algunos ha cambiado (“coincide” es ahora “es igual que”), de modo que la experiencia sea más coherente e intuitiva. Todas las reglas de inclusión creadas antes de esta versión se migran automáticamente a la nueva estructura. No es necesaria reestructuración alguna por su parte.

Puede crear tantas reglas de inclusión como necesite. Las reglas de inclusión se unen mediante un operador Y. Deben cumplirse todas las reglas para incluir un artículo en una recomendación.