---
description: mbox3rdPartyID es el ID del visitante de su empresa, como el ID de pertenencia para el programa de fidelidad de su empresa.
keywords: mbox;mbox3rdPartyID;sincronización de perfiles;sinc. de perfiles; PCID
seo-description: 'Información sobre perfil en tiempo real '
seo-title: Sincronización de perfiles en tiempo real para mbox 3 rdpartyid en Adobe Target
solution: Target
title: Sincronización de perfiles en tiempo real para mbox3rdPartyID
topic: Standard
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: 647776170531230a0d0f0aa3d97565fbb75bc963

---


# Sincronización de perfiles en tiempo real para mbox3rdPartyID{#real-time-profile-syncing-for-mbox-rdpartyid}

mbox3rdPartyID es el ID del visitante de su empresa, como el ID de pertenencia para el programa de fidelidad de su empresa.

Cuando un visitante inicia sesión en el sitio de una empresa, esta generalmente crea un ID vinculado a la cuenta del visitante, la tarjeta de fidelidad, el número de pertenencia u otros identificadores aplicables para esa empresa.

When a visitor accesses a page on which [!DNL Target] is enabled, that visitor is assigned a [!DNL Target] PCID. If the visitor then logs in, and the implementation passes the mbox3rdPartyID to [!DNL Target], [!DNL Target] connects that visitor's mbox3rdPartyID with the [!DNL Target] PCID.

Cada tres a cinco minutos, se sincronizan las actualizaciones con la base de datos. Cuando el visitante cierra la sesión, los datos fusionados reemplazan a los datos previos asociados con el mbox3rdPartyID, lo que crea un registro más completo de las acciones de ese visitante. Si el mismo atributo existe en ambos ID (por ejemplo, el PCID tiene category=hats y el mbox3rdPartyID tiene category=skis), o si el visitante vio la experiencia A antes de iniciar sesión, pero la experiencia B está almacenada en el mbox3rdPartyID, el atributo almacenado en el mbox3rdPartyID sobrescribe el atributo del PCID. Si el visitante estaba en una actividad o experiencia antes de iniciar sesión, pero una actividad y experiencia diferentes están almacenadas en el mbox3rdPartyID, tras iniciar sesión ese visitante se coloca en la actividad y experiencia del mbox3rdPartyID.

| PCID (sin sesión iniciada) | mbox3rdPartyID (con sesión iniciada) | Combinado y guardado en el mbox3rdPartyID |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| Actividad 1, experiencia A | Actividad 1, experiencia B | Actividad 1, experiencia B |
| Actividad 1 |  | Actividad 1 |

Cuando el visitante cierra sesión, se conserva el perfil combinado.

>[!NOTE]
>
>Los objetivos [!DNL Adobe Analytics] no se rastrearán cuando cambie el ID (MID) [!DNL Adobe Experience Cloud] (por ejemplo, el visitante cambia de dispositivo), aunque el perfil [!DNL Target] se pueda combinar en función del mbox3rdPartyID y tenga aún información de actividad. Para los visitantes identificados con el mismo MID (los que acceden a la página con el mismo dispositivo), [!DNL Analytics for Target] (A4T) debería funcionar según lo esperado.

## Consideraciones {#considerations}

Si su página contiene varios mboxes y solo utiliza 3 rdpartyid, Target no tiene un perfil o contexto de visitante independiente para cada solicitud de visitante. El contexto 3 rdpartyid tiene prioridad sobre el contexto PCID. Es suficiente para que un mbox pase 3 rdpartyid para que su contexto tenga prioridad sobre PCID.

Por ejemplo, supongamos que un visitante accede a una página antes de iniciar sesión y ver una experiencia. El mbox global no utiliza 3 rdpartyid. Tras iniciar sesión, el visitante ve una de las tres experiencias con mboxes secundarios, algunos de los cuales utilizan 3 rdpartyid. El visitante visita varias páginas del sitio y luego utiliza el botón Atrás para regresar a la página principal a la que se accede antes de iniciar sesión y ver una experiencia diferente. En este escenario, el mbox global no pasó 3 rdpartyid, pero sí uno o más de los mboxes secundarios. 3 Rdpartyid tiene prioridad sobre PCID.
