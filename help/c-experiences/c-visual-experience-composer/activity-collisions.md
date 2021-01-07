---
keywords: targeting;collisions;conflicts
description: La ficha Conflictos de la página Información general de Actividad en actividades de listas de Adobe Target entra en conflicto en el sitio.
title: Conflictos de actividades
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: 8110807a73e4d6d9848a52224db04faba033c98c
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 83%

---


# Conflictos de actividades

La ficha [!UICONTROL Conflictos] de la página [!UICONTROL Información general de Actividad] en [!DNL Adobe Target] Conflictos de actividad de listas en el sitio.

Un conflicto de actividades ocurre cuando existen varias actividades configuradas para entregar contenido a la misma página. Cuando se produce un conflicto de actividades, es probable que no se vea el contenido esperado en la página.

Si su actividad contiene posibles conflictos, la pestaña [!UICONTROL Conflictos] se encontrará disponible en la página Información general de la actividad. Se muestran todas las actividades de la misma dirección URL, independientemente de si se ha segmentado la audiencia o no en cada actividad. Abra esta pestaña para ver una lista de las actividades que pueden crear conflictos. Haga clic en una actividad de la lista para ver la página de información general para dicha actividad. Si el conflicto altera la experiencia esperada, edite la actividad.

La lista [!UICONTROL Conflictos] le ayuda a:

* Identificar si ya se está ejecutando una prueba en una página antes de configurar una actividad nueva.
* Solucionar problemas de una actividad si no se muestra el contenido esperado.

La lista [!UICONTROL Conflictos] muestra cada [!DNL Target] escenario en el que se utiliza el mbox y que utiliza la misma dirección URL. La lista muestra para cada posible conflicto la dirección URL de la actividad, el nombre del mbox donde podría producirse el conflicto y todas las actividades que cumplan estos dos criterios. Si hubiera más de un mbox, se incluirán todos.

En la lista se muestra el estado y la prioridad de cada posible conflicto, junto con otros datos. Puede usar el estado y la prioridad para determinar la probabilidad de que se produzca un conflicto. Por ejemplo, si hubiera un posible conflicto entre dos actividades y una estuviera inactiva, el conflicto no llegará a producirse a menos que se active la actividad inactiva. Si el posible conflicto afecta a dos actividades activas con la misma prioridad y la misma audiencia, el conflicto se producirá. Puede cambiar la prioridad o el estado para impedir el conflicto.

Aunque las audiencias sean distintas, sigue habiendo cierta posibilidad de conflicto puesto que es posible que un visitante concreto pertenezca a varias audiencias.
