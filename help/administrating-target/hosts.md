---
keywords: host;hosts;host group;troubleshooting;best practices;ubox;redirects;redirect;whitelist;allowlist;blacklist;blocklist
description: Organice sus sitios y entornos de preproducción para facilitar la administración y la creación de informes individuales.
title: Hosts
topic: Standard
uuid: c7682269-4ec2-4a0f-b053-7e0ec77f4604
translation-type: tm+mt
source-git-commit: cf69c1d8472088d5f6a6b7250bedd1048cac5c10
workflow-type: tm+mt
source-wordcount: '1232'
ht-degree: 57%

---


# Hosts{#hosts}

Organice sus sitios y entornos de preproducción para facilitar la administración y la creación de informes individuales.

El objetivo primordial de la administración de hosts reside en garantizar que ningún contenido inactivo se muestre por error en los sitios web. Host management also lets you separate report data by [environment](/help/administrating-target/environments.md).

Un host es un servidor web (o dominio web) desde el que se proporciona contenido durante cualquiera de las fases del proyecto. Se reconoce cualquier host que hospede un mbox.

Los hosts se agrupan en entornos para facilitar la administración. Así, se pueden tener decenas de hosts agrupados en dos o tres entornos. The preset environments include [!UICONTROL Production], [!UICONTROL Staging], and [!UICONTROL Development]. Puede añadir entornos nuevos y cambiarles el nombre, si lo desea.

One environment, the default environment, is pre-named [!UICONTROL Production]. El entorno predeterminado no se puede eliminar aunque se le cambie el nombre. [!DNL Target] da por hecho que es desde este entorno desde donde se van a suministrar las actividades y pruebas finales y aprobadas.

When an mbox request is received from new websites or domains, these new domains always appear in the [!UICONTROL Production] environment. The [!UICONTROL Production] environment cannot have its settings changed, so unknown or new sites are guaranteed to see only content that is active and ready. La administración de hosts también permite garantizar la calidad de las nuevas actividades y el contenido en los entornos de prueba, ensayo y desarrollo antes de activar las actividades.

[!DNL Target] no limita a un host que puede enviar y recibir mboxes, por lo que cuando surgen nuevos dominios o servidores, funcionan automáticamente (a menos que haya configurado una lista de permitidos o una lista de bloqueo). Esto permite, asimismo, realizar pruebas de anuncios en distintos dominios que no conoce o no puede prever.

Para administrar hosts, haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Hosts]**.

![](assets/hosts_list.png)

## Recognizing hosts {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

Para reconocer un host y agregarlo a la lista [!UICONTROL Hosts] , deben cumplirse las siguientes condiciones:

* Debe existir al menos un mbox en el host.
* Una página del host debe tener   lo siguiente:

   * Una referencia at.js o mbox.js precisa
   * Un mbox o una llamada de mbox global generada automáticamente

* La página con el mbox se debe ver en un navegador.

Tras ver la página, el host se incluye en la lista [!UICONTROL Hosts], lo que permite administrarla en el entorno, así como obtener una vista previa de las actividades y pruebas e iniciarlas.

>[!NOTE] {class=&quot;- topic/note &quot;}
>
>Esto engloba todos los servidores de desarrollo personal.

Cuando un host se añada a la lista [!UICONTROL Hosts], compruebe si se reconoce.

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Hosts]**.
1. Si no está en la lista, actualice el navegador. 


   By default, a newly recognized host is placed in the [!UICONTROL Production] environment. Se trata del entorno más seguro, dado que desde estos hosts no se pueden visualizar actividades inactivas.

1. (Condicional) Haga clic en el icono Mover (icono ![](/help/administrating-target/assets/icon-move.png) mover ) para mover el host al entorno [!UICONTROL Desarrollo], [!UICONTROL Ensayo]u otro.

>[!NOTE]
>
>The [!UICONTROL Production] environment cannot be deleted, even if you rename it. Se da por hecho que desde este se van a suministrar las actividades y pruebas finales y activas. El entorno predeterminado no permite la visualización de campañas inactivas.

## Sort or search the Hosts list {#section_068B23C9D8224EB78BC3B7C8580251B0}

To sort the [!UICONTROL Hosts] list, click any column header ([!UICONTROL Name], [!UICONTROL Environment], or [!UICONTROL Last Requested]) to sort the list in ascending or descending order.

To search the [!UICONTROL Hosts] list, type a search term in the [!UICONTROL Search Hosts] box.

## Create allowlists that specify hosts that are authorized to send mbox calls to Target. {#whitelist}

You can create an allowlist that specifies hosts (domains) that are authorized to send mbox calls to [!DNL Target]. Todos los demás hosts que generen llamadas obtendrán una respuesta de error de autorización comentada. Todo host que contenga una llamada de mbox se registra en el entorno Producción de [!DNL Target] de forma predeterminada y tiene acceso a todas las actividades activas y aprobadas. If this is not the desired approach, you can instead use the allowlist to record specific hosts that are eligible to make mbox calls and receive [!DNL Target] content. Todos los hosts seguirán apareciendo en la lista [!UICONTROL Hosts] y los entornos podrán seguir utilizándose para agrupar estos hosts y asignar distintos niveles a cada uno, como, por ejemplo, si el host puede ver campañas activas o inactivas.

Para crear una lista de permitidos:

1. En la lista [!UICONTROL Hosts] , haga clic en **[!UICONTROL Autorizar hosts]**.
1. Active la **[!UICONTROL opción Activar hosts autorizados para el envío]** de contenido.
1. Add the desired hosts in the **[!UICONTROL Host contains]** box, as desired.

   Se pueden agregar varios hosts, cada uno en una línea.

1. Add the desired hosts in the **[!UICONTROL Host does not contains]** box, as desired.

   Se pueden agregar varios hosts, cada uno en una línea.

1. Haga clic en **[!UICONTROL Guardar]**.

Si se realiza una llamada de mbox en un host sin autorización, la llamada responde con `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**Prácticas** recomendadas de seguridad: Si utiliza la funcionalidad de ubox de [!DNL Target], tenga en cuenta que esta lista de permitidos también controlará la lista de los dominios por los que pueden navegar [los redirectores](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) . Asegúrese de agregar los dominios a los que desee redirigir cuando utilice ubox como parte de la implementación. Si se deja la lista permitida sin especificar, Adobe no podrá verificar las direcciones URL de redireccionamiento ni protegerse de posibles redirecciones maliciosas.
>
>La lista de permitidos tiene prioridad sobre los entornos. Debe borrar todos los hosts antes de utilizar la función de lista de permitidos, y solo los hosts permitidos por la lista de permitidos aparecerán en la lista de hosts. A continuación, puede mover los hosts al entorno que quiera.

En ocasiones, aparecen dominios de otros sitios en los entornos. Un dominio aparece en la lista si el dominio realiza una llamada a su at.js o mbox.js. Por ejemplo, si alguien copia una de sus páginas web en su servidor, ese dominio aparecerá en nuestro entorno. También es probable que vea dominios de motores de araña, sitios de traducción de idiomas o unidades de disco locales.

En casos en los que `mboxHost` se pasa en una llamada de API, la conversión se registra para el entorno que se pasa. If no environment is passed, the host in the call defaults to [!UICONTROL Production].

También puede crear una lista de direcciones bloqueadas que incluya los hosts (dominios) que no pueden enviar llamadas de mbox a [!DNL Target]. Para ello, añada los hosts que quiera al cuadro [!UICONTROL El host no contiene].

>[!NOTE]
>
>Dado que la lista Hosts autorizados se utiliza tanto para hosts de mbox como para hosts de redireccionamiento predeterminados, debe agregar todos los dominios existentes aprobados para utilizar el SDK de JavaScript de Adobe Destinatario (at.js) *Y* todos los dominios utilizados en las direcciones URL de redireccionamiento predeterminadas de ubox. También debe agregar dominios similares nuevos a la lista de permitidos en el futuro.

## Delete a host {#section_F56355BA4BC54B078A1A8179BC954632}

Puede eliminar un host cuando ya no vaya a necesitarlo.

1. From the [!UICONTROL Hosts] list, click the **[!UICONTROL Delete]** icon.
1. Haga clic en **[!UICONTROL Eliminar]** para confirmar la acción.

>[!NOTE]
>
>El host vuelve a aparecer en la lista si alguien abre una página con mbox en el host.

## Resolución de problemas de hosts {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Prácticas recomendadas para administrar y resolver problemas de hosts en [!DNL Adobe Target].

Pruebe los siguientes consejos de resolución de problemas si tiene algún problema con los hosts:

**El host no aparece en la lista de mbox de la cuenta.**

* Actualice la página [!UICONTROL Hosts] en el navegador.
* Confirme que el código de mbox es correcto, incluida la referencia a at.js o mbox.js.
* Intente ir a uno de los mbox en el host. Es posible que no se haya presentado ningún mbox del host en un navegador.

**La lista[!UICONTROL Hosts]contiene dominios aleatorios o desconocidos.**

Cuando se efectúa una llamada a [!DNL Target] desde un dominio, este aparecerá en la lista. Con frecuencia, es posible ver dominios de motores de araña, sitios de traducción de idiomas o unidades de disco locales. En caso de que el dominio incluido en la lista no sea uno de los que el equipo usa, puede hacer clic en [!UICONTROL Eliminar] para eliminarlo.

**Mi llamada de mbox devuelve /* sin visualización: host mbox sin autorización */.**

Si se realiza una llamada de mbox en un host sin autorización, la llamada responderá con /* sin visualización: host mbox sin autorización */.
