---
keywords: segmentación;conflictos;conflictos
description: Se producen conflictos cuando se configuran varias actividades para entregar contenido en la misma página. Obtenga información sobre cómo evitar conflictos al utilizar Adobe Target.
title: ¿Cómo puedo evitar los conflictos de actividades?
feature: Visual Experience Composer (VEC)
exl-id: 1af90dd1-69c9-41ec-8785-095dcc557b32
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 79%

---

# Conflictos de actividades

La variable [!UICONTROL Conflictos] en la ficha [!UICONTROL Información general de actividad] en [!DNL Adobe Target] enumera los conflictos de actividades en el sitio.

Un conflicto de actividades ocurre cuando existen varias actividades configuradas para entregar contenido a la misma página. Cuando se produce un conflicto de actividades, es probable que no se vea el contenido esperado en la página.

Si su actividad contiene posibles conflictos, la pestaña [!UICONTROL Conflictos] se encontrará disponible en la página Información general de la actividad. Se muestran todas las actividades de la misma dirección URL, independientemente de si se ha segmentado la audiencia o no en cada actividad. Abra esta pestaña para ver una lista de las actividades que pueden crear conflictos. Haga clic en una actividad de la lista para ver la página de información general para dicha actividad. Si el conflicto altera la experiencia esperada, edite la actividad.

La variable [!UICONTROL Conflictos] le ayuda a:

* Identificar si ya se está ejecutando una prueba en una página antes de configurar una actividad nueva.
* Solucionar problemas de una actividad si no se muestra el contenido esperado.

La variable [!UICONTROL Conflictos] la lista muestra cada [!DNL Target] escenario en el que se usa el mbox y que usa la misma dirección URL. La lista muestra para cada posible conflicto la dirección URL de la actividad, el nombre del mbox donde podría producirse el conflicto y todas las actividades que cumplan estos dos criterios. Si hubiera más de un mbox, se incluirán todos.

En la lista se muestra el estado y la prioridad de cada posible conflicto, junto con otros datos. Puede usar el estado y la prioridad para determinar la probabilidad de que se produzca un conflicto. Por ejemplo, si hubiera un posible conflicto entre dos actividades y una estuviera inactiva, el conflicto no llegará a producirse a menos que se active la actividad inactiva. Si el posible conflicto afecta a dos actividades activas con la misma prioridad y la misma audiencia, el conflicto se producirá. Puede cambiar la prioridad o el estado para impedir el conflicto.

Aunque las audiencias sean distintas, sigue habiendo cierta posibilidad de conflicto puesto que es posible que un visitante concreto pertenezca a varias audiencias.
