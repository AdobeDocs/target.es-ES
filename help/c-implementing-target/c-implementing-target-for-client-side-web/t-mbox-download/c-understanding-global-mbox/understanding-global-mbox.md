---
keywords: mbox global;implementar mbox.js;implementar at.js
description: Información sobre el mbox global, un nombre que se utiliza para hacer referencia a una sola llamada al servidor realizada en la parte superior de cada página web en la implementación de Adobe Target.
title: Comprender el mbox global
subtopic: Primeros pasos
topic: Standard
uuid: d8f48c94-6487-437b-828f-f9be7da58f48
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Comprender el mbox global{#understand-the-global-mbox}

Información sobre el mbox global, un nombre que se utiliza para hacer referencia a una sola llamada al servidor realizada en la parte superior de cada página web en la implementación de Adobe Target.

El nombre predeterminado del mbox global es [!DNL target-global-mbox]. Si fuera necesario, puede cambiarse el nombre para su cuenta.

Hay muchas diferencias entre un mbox normal (mbox no global) y el mbox global, entre las que se incluyen:

| Mbox normal | Mbox global |
|--- |--- |
| Un mbox normal suele encapsular contenido con una etiqueta `<DIV>`. | El mbox global está “vacío” y no encapsula ningún contenido. |
| El contenido de una sola actividad puede entregarse en un mbox normal. | El contenido de varias actividades puede entregarse en una sola respuesta a un mbox global. |

Si se envían varias actividades a través del mbox global o a través de varios mboxes normales, [!DNL Target] [ determina la prioridad](../../../../c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F) por la cual la actividad (o actividades) se envía a una página web.

Pueden enviarse a [!DNL Target] datos adicionales a nivel de página junto con el mbox global con la función `targetPageParams`. Esta opción es parecida a la funcionalidad de parámetro de mbox. Para obtener más información, consulte [Transferencia de parámetros a un mbox global](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md#concept_33362A04146C4E3C8E7089B65F38B5E5).
