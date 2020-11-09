---
keywords: mbox;mbox3rdPartyId;profile syncing;profile synch;PCID
description: 'Información sobre el perfil en tiempo real '
title: Sincronización de perfiles en tiempo real para mbox3rdPartyId en Adobe Target
feature: visitor profiles
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 81%

---


# Sincronización de perfiles en tiempo real para mbox3rdPartyId{#real-time-profile-syncing-for-mbox-rdpartyid}

mbox3rdPartyId es el ID del visitante de su empresa, como el ID de pertenencia para el programa de fidelidad de su empresa.

Cuando un visitante inicia sesión en el sitio de una empresa, esta generalmente crea un ID vinculado a la cuenta del visitante, la tarjeta de fidelidad, el número de pertenencia u otros identificadores aplicables para esa empresa.

Cuando un visitante tiene acceso a una página en la que está habilitado [!DNL Target], se asigna al visitante un PCID de [!DNL Target]. Si el visitante luego inicia sesión, y la implementación pasa el mbox3rdPartyId a [!DNL Target], [!DNL Target] se conecta el mbox3rdPartyId de ese visitante con el PCID de [!DNL Target].

Las actualizaciones se sincronizan con la base de datos con una frecuencia comprendida entre tres y cinco minutos. Cuando el visitante cierra la sesión, los datos fusionados reemplazan a los datos previos asociados con el mbox3rdPartyId, lo que crea un registro más completo de las acciones de ese visitante. Si el mismo atributo existe en ambos ID (por ejemplo, el PCID tiene category=hats y el mbox3rdPartyId tiene category=skis), o si el visitante vio la experiencia A antes de iniciar sesión, pero la experiencia B está almacenada en el mbox3rdPartyId, el atributo almacenado en el mbox3rdPartyId sobrescribe el atributo del PCID. Si el visitante estaba en una actividad o experiencia antes de iniciar sesión, pero en el mbox3rdPartyId están almacenadas una actividad y experiencia diferentes, tras iniciar sesión ese visitante se ubica en la actividad y experiencia del mbox3rdPartyId.

| PCID (sin sesión iniciada) | mbox3rdPartyId (con sesión iniciada) | Combinado y guardado en el mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| Actividad 1, experiencia A | Actividad 1, experiencia B | Actividad 1, experiencia B |
| Actividad 1 |  | Actividad 1 |

Cuando el visitante cierra sesión, se conserva el perfil combinado.

>[!NOTE]
>
>Si desea distinguir entre usuarios autenticados (con inicio de sesión) y usuarios no autenticados, utilice Adobe Experience Cloud Identity Service (ECID) en lugar de mbox3rdPartyID. Una vez que un usuario está asociado con mbox3rdPartyID, permanece asociado al usuario incluso después de cerrar sesión.

>[!NOTE]
>
>[!DNL Adobe Analytics] no se realizará un seguimiento de los objetivos en los casos en los que el [!DNL Adobe Experience Cloud] ID (EDID) cambie (por ejemplo, el visitante cambia de dispositivo), aunque el [!DNL Target] perfil se pueda combinar en función del mbox3rdPartyId y siga teniendo información de actividad. For visitors identified with the same EDID (those who access the page with the same device), [!DNL Analytics for Target] (A4T) should work as expected.

## Consideraciones {#considerations}

Si su página contiene varios mboxes y solo utiliza 3rdPartyID, Target no tiene un perfil o contexto de visitante independiente para cada solicitud de visitante. El contexto 3rdPartyID tiene prioridad sobre el contexto PCID. Es suficiente con que un mbox pase 3rdPartyId para que su contexto tenga prioridad sobre PCID.

Por ejemplo, supongamos que un visitante accede a una página antes de iniciar sesión y ve una experiencia. El mbox global no utiliza 3rdPartyID. Tras iniciar sesión, el visitante ve una de las tres experiencias con mboxes secundarios, algunos de los cuales utilizan 3rdPartyID. El visitante navega por varias páginas del sitio y luego utiliza el botón Atrás para regresar a la página principal, a la que se accede antes de iniciar sesión, y ve una experiencia diferente. En este escenario, el mbox global no pasó 3rdPartyID, pero sí lo hicieron uno o más de los mboxes secundarios. 3rdPartyID tiene prioridad sobre PCID.
