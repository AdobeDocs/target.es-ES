---
keywords: mbox global;implementar at.js
description: Obtenga información sobre el mbox global en Adobe Target, un nombre utilizado para hacer referencia a la llamada al servidor única que se realiza en la parte superior de cada página web de su [!DNL Target] implementación.
title: ¿Qué es un mbox global?
feature: at.js
role: Developer
exl-id: 84d15feb-f5df-4879-ae35-a7f455c1b20f
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 74%

---

# Comprender el mbox global

Información sobre el mbox global, un nombre utilizado para hacer referencia a la llamada del servidor única que se realiza en la parte superior de cada página web en su implementación de [!DNL Adobe Target].

El nombre predeterminado del mbox global es `target-global-mbox`. Si fuera necesario, puede cambiarse el nombre para su cuenta.

Hay muchas diferencias entre un mbox normal (mbox no global) y el mbox global, entre las que se incluyen:

| Mbox normal | Mbox global |
|--- |--- |
| Un mbox normal suele encapsular contenido con una etiqueta `<DIV>`. | El mbox global está “vacío” y no encapsula ningún contenido. |
| El contenido de una sola actividad puede entregarse en un mbox normal. | El contenido de varias actividades puede entregarse en una sola respuesta a un mbox global. |

Si se envían varias actividades a través del mbox global o a través de varios mboxes normales, [!DNL Target] [ determina la prioridad](/help/main/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F) por la cual la actividad (o actividades) se envía a una página web.

Pueden enviarse a [!DNL Target] datos adicionales a nivel de página junto con el mbox global con la función `targetPageParams`. Esta opción es parecida a la funcionalidad de parámetro de mbox. Para obtener más información, consulte [Pasar parámetros a un mbox global](https://developer.adobe.com/target/implement/client-side/atjs/global-mbox/pass-parameters-to-global-mbox/){target=_blank}.
