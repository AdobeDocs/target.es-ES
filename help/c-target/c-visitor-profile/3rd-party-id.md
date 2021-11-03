---
keywords: mbox;mbox3rdPartyId;sincronización de perfiles;sinc. de perfiles;PCID
description: Aprenda a utilizar el mbox3rdPartyId, que es el ID de visitante de su organización, como el ID de pertenencia o el programa de fidelidad de su organización.
title: ¿Cómo utilizo la sincronización de perfiles en tiempo real para mbox3rdPartyId?
feature: Audiences
exl-id: ed409225-fa35-49da-87d1-1770221f2ae0
source-git-commit: 47772ebbdec10f78ec120d2e4437eccad969b338
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 92%

---

# Sincronización de perfiles en tiempo real para mbox3rdPartyId

El `mbox3rdPartyId` en [!DNL Adobe Target] es el ID de visitante de su compañía, como el ID de pertenencia para el programa de fidelidad de su empresa.

Cuando un visitante inicia sesión en el sitio de una empresa, esta generalmente crea un ID vinculado a la cuenta del visitante, la tarjeta de fidelidad, el número de pertenencia u otros identificadores aplicables para esa empresa.

Cuando un visitante tiene acceso a una página en la que está habilitado [!DNL Target], se asigna al visitante un PCID de [!DNL Target]. Si el visitante luego inicia sesión, y la implementación pasa el `mbox3rdPartyId` a [!DNL Target], [!DNL Target] conecta el `mbox3rdPartyId` de ese visitante con el PCID de [!DNL Target].

Las actualizaciones se sincronizan con la base de datos con una frecuencia comprendida entre tres y cinco minutos. Cuando el visitante cierra la sesión, los datos fusionados reemplazan a los datos previos asociados con el `mbox3rdPartyId`, lo que crea un registro completo de las acciones de ese visitante. Si el mismo atributo existe en ambos ID (por ejemplo, el PCID tiene category=hats y el `mbox3rdPartyId` tiene category=skis), o si el visitante vio la experiencia A antes de iniciar sesión, pero la experiencia B está almacenada en el `mbox3rdPartyId`, el atributo almacenado en el `mbox3rdPartyId` sobrescribe el atributo del PCID. Si el visitante estaba en una actividad o experiencia antes de iniciar sesión, pero una actividad y experiencia diferentes están almacenadas en el `mbox3rdPartyId`, tras iniciar sesión ese visitante se coloca en la actividad y experiencia del `mbox3rdPartyId`.

| PCID (sin sesión iniciada) | mbox3rdPartyId (con sesión iniciada) | Combinado y guardado en el mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| Actividad 1, experiencia A | Actividad 1, experiencia B | Actividad 1, experiencia B |
| Actividad 1 |  | Actividad 1 |

Cuando el visitante cierra sesión, se conserva el perfil combinado.

>[!NOTE]
>
>Si desea distinguir entre usuarios autenticados (que han iniciado sesión) y usuarios no autenticados, utilice el [!DNL Adobe Experience Cloud Identity Service] (ECID) en lugar de mbox3rdPartyID. Una vez que un usuario está asociado con mbox3rdPartyID, permanece asociado con el usuario incluso después de cerrar la sesión.

>[!NOTE]
>
>[!DNL Adobe Analytics] no se realiza un seguimiento de los objetivos en los casos en que la variable [!DNL Adobe Experience Cloud] El ID (ECID) cambia (por ejemplo, el visitante cambia de dispositivo), aunque la variable [!DNL Target] el perfil se puede combinar en función del mbox3rdPartyId y seguirá teniendo información de actividad. Para los visitantes identificados con el mismo ECID (los que acceden a la página con el mismo dispositivo), [!DNL Analytics for Target] (A4T) debe funcionar según lo esperado.

## Consideraciones {#considerations}

* Si su página contiene varios mboxes y solo algunos utilizan `3rdPartyID`, [!DNL Target] no tiene un perfil o contexto del visitante independiente para cada solicitud de visitante. El contexto `3rdPartyID` tiene prioridad sobre el contexto PCID. Es suficiente con que un mbox pase `3rdPartyId` para que su contexto tenga prioridad sobre PCID.

   Por ejemplo, supongamos que un visitante accede a una página antes de iniciar sesión y ve una experiencia. El mbox global no utiliza `3rdPartyID`. Tras iniciar sesión, el visitante ve una de las tres experiencias con mboxes secundarios, algunos de los cuales utilizan `3rdPartyID`. El visitante navega por varias páginas del sitio y luego utiliza el botón Atrás para regresar a la página principal, a la que se accede antes de iniciar sesión, y ve una experiencia diferente. En este escenario, el mbox global no pasó `3rdPartyID`, pero sí lo hicieron uno o más de los mboxes secundarios. `3rdPartyID` tuvo prioridad sobre PCID.

* Puede enviar los ID de cliente de visitantes a [!DNL Target] mediante dos métodos:

   1. Utilice `mbox3rdPartyId`/`thirdPartyId`.

      * `mbox3rdPartyId` es el nombre del parámetro cuando se usa `targetPageParams` o `targetPageParamsAll`
      * `thirdPartyId` es el nombre del parámetro que se establece directamente en la carga útil de la API de entrega.
      * Solo puede enviar un valor en este parámetro.
   1. Utilice la función `setCustomerId`/`customerIds` del servicio ECID.

      * `setCustomerId` es una función que puede utilizar en implementaciones del lado del cliente (explorador) cuando VisitorAPI.js está disponible en la página.
      * `customerIds` es el nombre del parámetro que se utiliza cuando se establece directamente en la carga útil de la API de entrega y que generalmente se realiza en implementaciones del lado del servidor o IOT (Internet de las cosas).
      * A diferencia de `mbox3rdPartyId`/`thirdPartyId`, puede enviar varios ID como una lista en este enfoque, pero como [!DNL Target] solo admite un ID de cliente único por ID de TnT, utiliza el primer ID de la lista con un alias conocido (alias configurado en la IU de Atributos del cliente).

   >[!IMPORTANT]
   >
   > El uso de ambos enfoques mencionados anteriormente de forma intercambiable para un único visitante puede dar como resultado combinaciones de perfiles incorrectas de los perfiles [!DNL Target] no autenticados y autenticados.
   >
   >Adobe no recomienda utilizar `mbox3rdPartyId`/`thirdPartyId` y `setCustomerID`/`customerIds` juntos.
   >
   >Si debe utilizar ambos métodos de forma intercambiable, asegúrese de que el primer ID de la lista utilizado por `setCustomerID`/`customerIds` es el que utilizan `thirdPartyId`/`mbox3rdPartyId` y viceversa.

