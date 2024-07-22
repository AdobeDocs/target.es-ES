---
keywords: segmentación;conflictos;conflictos
description: Los conflictos se producen cuando se configuran varias actividades para enviar contenido a la misma página. Obtenga información sobre cómo evitar conflictos al utilizar Adobe Target.
title: ¿Cómo puedo evitar conflictos de actividades?
feature: Visual Experience Composer (VEC)
exl-id: 1af90dd1-69c9-41ec-8785-095dcc557b32
source-git-commit: b34701113ebdc9f539e5a3d7163aa3dd85368af3
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 67%

---

# Conflictos de actividades

La ficha [!UICONTROL Collisions] de la página [!UICONTROL Activity Overview] de [!DNL Adobe Target] enumera los conflictos de actividades en el sitio.

Un conflicto de actividades ocurre cuando existen varias actividades configuradas para entregar contenido a la misma página. Cuando se produce un conflicto de actividades, es probable que no se vea el contenido esperado en la página.

La pestaña [!UICONTROL Collisions] está disponible en la página de información general de la actividad y puede informarle si su actividad contiene posibles conflictos. Se muestran todas las actividades de la misma dirección URL, independientemente de si se ha segmentado la audiencia o no en cada actividad. Abra esta pestaña para ver una lista de las actividades que pueden crear conflictos. Haga clic en una actividad de la lista para ver la página de información general para dicha actividad. Si el conflicto altera la experiencia esperada, edite la actividad.

La lista [!UICONTROL Collisions] le ayuda a:

* Identificar si ya se está ejecutando una prueba en una página antes de configurar una actividad nueva.
* Solucionar problemas de una actividad si no se muestra el contenido esperado.

La lista [!UICONTROL Collisions] muestra todos los escenarios [!DNL Target] en los que se usa el mbox y que usan la misma dirección URL. Para cada posible colisión, la lista muestra la URL de la actividad, el nombre del mbox donde podría producirse la colisión y cualquier actividad que coincida con ambos criterios. Si hubiera más de un mbox, se incluirán todos.

En la lista se muestra el estado y la prioridad de cada posible conflicto, junto con otros datos. Puede usar el estado y la prioridad para determinar la probabilidad de que se produzca un conflicto. Por ejemplo, si hubiera un posible conflicto entre dos actividades y una estuviera inactiva, el conflicto no llegará a producirse a menos que se active la actividad inactiva. Si el posible conflicto afecta a dos actividades activas con la misma prioridad y la misma audiencia, el conflicto se producirá. Puede cambiar la prioridad o el estado para impedir el conflicto.

Aunque las audiencias sean distintas, sigue habiendo cierta posibilidad de conflicto puesto que es posible que un visitante concreto pertenezca a varias audiencias.
