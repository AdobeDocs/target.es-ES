---
description: mbox3rdPartyID es el ID del visitante de su empresa, como el ID de pertenencia para el programa de fidelidad de su empresa.
keywords: mbox;mbox3rdPartyID;sincronización de perfiles;sinc. de perfiles
seo-description: mbox3rdPartyID es el ID del visitante de su empresa, como el ID de pertenencia para el programa de fidelidad de su empresa.
seo-title: Sincronización de perfiles en tiempo real para mbox3rdPartyID
solution: Target
title: Sincronización de perfiles en tiempo real para mbox3rdPartyID
topic: Standard
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Sincronización de perfiles en tiempo real para mbox3rdPartyID{#real-time-profile-syncing-for-mbox-rdpartyid}

mbox3rdPartyID es el ID del visitante de su empresa, como el ID de pertenencia para el programa de fidelidad de su empresa.

Cuando un visitante inicia sesión en el sitio de una empresa, esta generalmente crea un ID vinculado a la cuenta del visitante, la tarjeta de fidelidad, el número de pertenencia u otros identificadores aplicables para esa empresa.

Cuando un visitante tiene acceso a una página en la que Target está habilitado, se asigna al visitante un PCID de Target. Si el visitante luego inicia sesión, y la implementación pasa el mbox3rdPartyID a Target, Target conecta el mbox3rdPartyID de ese visitante con el PCID de Target.

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
