---
keywords: segmentación;conflictos;conflictos
description: Evite los conflictos de entrega de contenido en la misma página configurando correctamente las actividades en Adobe Target.
title: ¿Cómo puedo evitar conflictos de actividades?
feature: Visual Experience Composer (VEC)
exl-id: 1af90dd1-69c9-41ec-8785-095dcc557b32
TQID: 'https://experienceleague.adobe.com/R6cwp4KnoYPO9Wxr47HswtBX6jKPJ0i-UGdtA1ZHawU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 18%
---
# Conflictos de actividades {#activity-collisions}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a usar la ficha **[!UICONTROL Conflictos]** para buscar actividades que puedan enviar contenido a la misma página.

>[!ENDSHADEBOX]

Un conflicto de actividades ocurre cuando existen varias actividades configuradas para entregar contenido a la misma página. Si se produce un conflicto de actividades, es posible que el contenido esperado no aparezca en la página.

La ficha **[!UICONTROL Conflictos]** de la página **[!UICONTROL Información general de la actividad]** en [!DNL Adobe Target] enumera los conflictos de actividades en el sitio y muestra si una actividad contiene conflictos potenciales. La lista **[!UICONTROL Conflictos]** ayuda a:

* Identifique si ya se está ejecutando una prueba en una página antes de configurar una nueva actividad
* Solucionar problemas de una actividad si no se muestra el contenido esperado.

## Acceso a la pestaña Conflictos {#access-collisions}

Haga clic en **[!UICONTROL Actividades]**, haga clic en la actividad que quiera de la lista y luego acceda al menú **[!UICONTROL Conflictos]**.

![Icono de configuración](assets/collisions_1.png)

Se muestran todas las actividades de la misma dirección URL, independientemente de si se ha segmentado el público o no en cada actividad. La pestaña enumera las actividades que pueden estar colisionando. Si el conflicto altera la experiencia esperada, edite la actividad.

## Leer la lista Conflictos {#collisions-list}

La lista **[!UICONTROL Conflictos]** muestra cada [!DNL Target] escenario donde se usa el mbox y que usa la misma dirección URL. Para cada posible colisión, la lista muestra la URL de la actividad, el nombre del mbox donde podría producirse la colisión y cualquier actividad que coincida con ambos criterios. Si hubiera más de un mbox, se incluirán todos.

La lista también muestra el estado y la prioridad de cada posible colisión, junto con otra información. El estado y la prioridad ayudan a determinar la probabilidad de que se produzca una colisión. Para dos actividades que podrían chocar:

* Si una actividad no está activa actualmente, no puede producirse un conflicto. Una colisión solo es posible si la actividad inactiva se activa.
* Si se produce un conflicto entre dos actividades activas con la misma prioridad y la misma audiencia, se producirá un conflicto. La prioridad o el estado se pueden cambiar para evitar la colisión.
* Si las audiencias son diferentes, existe la posibilidad de que se produzca un conflicto, ya que un visitante en particular podría pertenecer a varias audiencias.
