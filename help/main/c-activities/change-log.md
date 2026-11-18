---
keywords: registro de cambios de actividades;registro de cambios
description: Acceda al registro de cambios de una actividad en Adobe [!DNL Target] para ver un registro de quién modificó las actividades y cuándo se produjeron los cambios.
title: ¿Cómo puedo ver un registro de cambios de actividades?
feature: Activities
exl-id: 72a901c1-4fba-4044-b72b-393cab56b936
TQID: 'https://experienceleague.adobe.com/YmadzVwbj4Hy1bk3Q7a0hp9oZ7-lSgl12ImQaEsiDwU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: 8c6f23b495228ab930e6649aa2f9e6dae506cae2
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 10%
---
# Registro de cambios de actividades {#change-log}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a ver las acciones realizadas en una actividad, quién las realizó y cuándo.

>[!ENDSHADEBOX]

El [!DNL Adobe Target] **[!UICONTROL Registro de cambios]** registra las acciones realizadas en una actividad, incluidos los cambios, quién realizó los cambios y cuándo se produjeron. Proporciona un historial claro de la actividad y la página **[!UICONTROL Registro de cambios]** se rellena para obtener información en tiempo real.

Para acceder a la página **[!UICONTROL Registro de cambios]**:

1. Haga clic en **[!UICONTROL Actividades]** y luego haga clic en la actividad en la lista.
1. Haga clic en **[!UICONTROL Registro de cambios]** en el carril izquierdo.

   La página enumera la acción realizada, la fecha de la acción y el usuario que la realizó cada vez que se crea, actualiza, activa o desactiva una actividad. Asimismo, también se enumeran los cambios en los objetivos personalizados y en las ofertas utilizadas en la actividad.

   ![Menú de registro de cambios](assets/change_logs.png)

1. Para enumerar las acciones en orden ascendente o descendente, haga clic en el encabezado de columna **[!UICONTROL Date]**.

1. Actualice la página para ver los cambios de estado.

## API de registro de auditoría de Target

* [Revisiones: obtenga el registro de auditoría por el último nombre del autor y una marca de tiempo posterior a la modificación](https://developer.adobe.com/target/administer/admin-api/#tag/Revisions){target=_blank}
* [Enumerar registro de cambios de actividad](https://developer.adobe.com/target/administer/admin-api/#tag/Activities/operation/getChangelog){target=_blank}
