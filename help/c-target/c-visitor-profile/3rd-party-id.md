---
description: El mbox 3 rdpartyid es el ID de visitante de su empresa, como el ID de pertenencia del programa de fidelidad de su empresa.
keywords: mbox; mbox 3 rdpartyid; sincronización de perfiles; sincronización de perfiles; PCID
seo-description: 'Información sobre perfil en tiempo real '
seo-title: Sincronización de perfiles en tiempo real para mbox 3 rdpartyid en Adobe Target
solution: Target
title: Sincronización de perfiles en tiempo real para mbox 3 rdpartyid
topic: Standard
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: f54dba622e449fb8dac44cb37ff711419f8eda4b

---


# Real-time profile syncing for mbox3rdPartyId{#real-time-profile-syncing-for-mbox-rdpartyid}

El mbox 3 rdpartyid es el ID de visitante de su empresa, como el ID de pertenencia del programa de fidelidad de su empresa.

Cuando un visitante inicia sesión en el sitio de una empresa, esta generalmente crea un ID vinculado a la cuenta del visitante, la tarjeta de fidelidad, el número de pertenencia u otros identificadores aplicables para esa empresa.

When a visitor accesses a page on which [!DNL Target] is enabled, that visitor is assigned a [!DNL Target] PCID. If the visitor then logs in, and the implementation passes the mbox3rdPartyId to [!DNL Target], [!DNL Target] connects that visitor's mbox3rdPartyId with the [!DNL Target] PCID.

Las actualizaciones se sincronizan con la base de datos con una frecuencia comprendida entre tres y cinco minutos. Cuando el visitante cierra sesión, los datos combinados sustituyen a los datos anteriores asociados con el mbox 3 rdpartyid, lo que crea un registro más completo de las acciones de dicho visitante. Si existe el mismo atributo en ambos ID—Por ejemplo, PCID tiene category = hats y el mbox 3 rdpartyid tiene category = skis, o si el visitante vio la experiencia A antes de iniciar sesión, pero la experiencia B se almacena en el mbox 3 rdpartyid. —el atributo almacenado en el mbox 3 rdpartyid sobrescribe el atributo del PCID. Si el visitante estuvo en una actividad o experiencia antes de iniciar sesión, pero una actividad y experiencia diferentes se almacenan en el mbox 3 rdpartyid, tras iniciar sesión ese visitante se coloca en la actividad y experiencia de mbox 3 rdpartyid.

| PCID (sin sesión iniciada) | mbox 3 rdpartyid (Sesión iniciada) | Combinado y guardado en mbox 3 rdpartyid |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| Actividad 1, experiencia A | Actividad 1, experiencia B | Actividad 1, experiencia B |
| Actividad 1 |  | Actividad 1 |

Cuando el visitante cierra sesión, se conserva el perfil combinado.

>[!NOTE]
>
>[!DNL Adobe Analytics] los objetivos no se rastrearán en casos en los que los cambios [!DNL Adobe Experience Cloud] de ID (MID) (por ejemplo, el visitante cambia de dispositivo), aunque el [!DNL Target] perfil se pueda combinar en función del mbox 3 rdpartyid y aún tenga información de actividad. Para los visitantes identificados con el mismo MID (los que acceden a la página con el mismo dispositivo), [!DNL Analytics for Target] (A4T) debería funcionar según lo esperado.

## Consideraciones {#considerations}

Si su página contiene varios mboxes y solo utiliza 3 rdpartyid, Target no tiene un perfil o contexto de visitante independiente para cada solicitud de visitante. El contexto 3 rdpartyid tiene prioridad sobre el contexto PCID. Es suficiente para que un mbox pase 3 rdpartyid para que su contexto tenga prioridad sobre PCID.

Por ejemplo, supongamos que un visitante accede a una página antes de iniciar sesión y ver una experiencia. El mbox global no utiliza 3 rdpartyid. Tras iniciar sesión, el visitante ve una de las tres experiencias con mboxes secundarios, algunos de los cuales utilizan 3 rdpartyid. El visitante visita varias páginas del sitio y luego utiliza el botón Atrás para regresar a la página principal a la que se accede antes de iniciar sesión y ver una experiencia diferente. En este escenario, el mbox global no pasó 3 rdpartyid, pero sí uno o más de los mboxes secundarios. 3 Rdpartyid tiene prioridad sobre PCID.
