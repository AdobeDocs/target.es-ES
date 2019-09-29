---
description: El mbox3rdPartyId es el ID de visitante de su empresa, como el ID de pertenencia para el programa de lealtad de su empresa.
keywords: mbox;mbox3rdPartyId;sincronización de perfiles;sincronización de perfiles;PCID
seo-description: 'Información sobre el perfil en tiempo real '
seo-title: Sincronización de perfiles en tiempo real para mbox3rdPartyId en Adobe Target
solution: Target
title: Sincronización de perfiles en tiempo real para mbox3rdPartyId
topic: Standard
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: f54dba622e449fb8dac44cb37ff711419f8eda4b

---


# Real-time profile syncing for mbox3rdPartyId{#real-time-profile-syncing-for-mbox-rdpartyid}

El mbox3rdPartyId es el ID de visitante de su empresa, como el ID de pertenencia para el programa de lealtad de su empresa.

Cuando un visitante inicia sesión en el sitio de una empresa, esta generalmente crea un ID vinculado a la cuenta del visitante, la tarjeta de fidelidad, el número de pertenencia u otros identificadores aplicables para esa empresa.

When a visitor accesses a page on which [!DNL Target] is enabled, that visitor is assigned a [!DNL Target] PCID. If the visitor then logs in, and the implementation passes the mbox3rdPartyId to [!DNL Target], [!DNL Target] connects that visitor's mbox3rdPartyId with the [!DNL Target] PCID.

Las actualizaciones se sincronizan con la base de datos con una frecuencia comprendida entre tres y cinco minutos. Cuando el visitante cierra la sesión, los datos combinados sustituyen a los datos anteriores asociados con el mbox3rdPartyId, lo que crea un registro más completo de las acciones de ese visitante. Si el mismo atributo existe en ambos ID (por ejemplo, el PCID tiene category=hats y el mbox3rdPartyId tiene category=skis o si el visitante vio la experiencia A antes de iniciar sesión, pero la experiencia B se almacena en el mbox3rdPartyId), el atributo almacenado en el mbox3rdPartyId sobrescribe el atributo del PCID. Si el visitante estuvo en una actividad o experiencia antes de iniciar sesión, pero una actividad y experiencia diferentes se almacenan en mbox3rdPartyId, después de iniciar sesión ese visitante se coloca en la actividad y experiencia de mbox3rdPartyId.

| PCID (sin sesión iniciada) | mbox3rdPartyId (sesión iniciada) | Combinado y guardado en mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| Actividad 1, experiencia A | Actividad 1, experiencia B | Actividad 1, experiencia B |
| Actividad 1 |  | Actividad 1 |

Cuando el visitante cierra sesión, se conserva el perfil combinado.

>[!NOTE]
>
>[!DNL Adobe Analytics] no se rastrearán los objetivos en los casos en que el [!DNL Adobe Experience Cloud] ID (MID) cambie (por ejemplo, el visitante cambie de dispositivo), aunque el [!DNL Target] perfil se pueda combinar en función del mbox3rdPartyId y tenga información de actividad. Para los visitantes identificados con el mismo MID (los que acceden a la página con el mismo dispositivo), [!DNL Analytics for Target] (A4T) debería funcionar según lo esperado.

## Consideraciones {#considerations}

Si la página contiene varios mboxes y solo algunos usan 3rdPartyID, Target no tiene un perfil o contexto de visitante independiente para cada solicitud de visitante. El contexto 3rdPartyID tiene prioridad sobre el contexto PCID. Basta con que un mbox pase 3rdPartyId para que su contexto tenga prioridad sobre PCID.

Por ejemplo, supongamos que un visitante accede a una página antes de iniciar sesión y ve una experiencia. El mbox global no utiliza 3rdPartyID. Después de iniciar sesión, el visitante ve una de las tres experiencias con mboxes secundarios, algunas de las cuales usan 3rdPartyID. El visitante visita varias páginas del sitio y luego utiliza el botón Atrás para volver a la página principal a la que se accedió antes de iniciar sesión y ve una experiencia diferente. En este escenario, el mbox global no pasó 3rdPartyID, pero sí uno o más mboxes secundarios. 3rdPartyID tuvo prioridad sobre PCID.
