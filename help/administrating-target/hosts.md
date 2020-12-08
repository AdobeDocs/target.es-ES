---
keywords: host;hosts;host group;troubleshooting;best practices;ubox;redirects;redirect;whitelist;allowlist;blacklist;blocklist
description: Organice sus sitios y entornos de preproducción para facilitar la administración y el sistema de informes separado en Adobe Target.
title: Hosts
feature: hosts and environments
translation-type: tm+mt
source-git-commit: c2769c0fcf7a05c10405ec855468c829aca785c0
workflow-type: tm+mt
source-wordcount: '1082'
ht-degree: 26%

---


# Hosts{#hosts}

Organice sus sitios y entornos de preproducción para facilitar la administración y la creación de informes individuales.

El objetivo primordial de la administración de hosts reside en garantizar que ningún contenido inactivo se muestre por error en los sitios web. Host management also lets you separate report data by [environment](/help/administrating-target/environments.md).

Un host es cualquier dominio desde el cual se realiza una [!DNL Target] solicitud. En un sitio web, suele ser la `location.hostname` propiedad de la dirección URL que realiza la [!DNL Target] solicitud.

De forma predeterminada, [!DNL Target] no limita a un host que puede realizar [!DNL Target] solicitudes y recibir [!DNL Target] respuestas. Cuando los nuevos hosts realizan solicitudes, funcionan automáticamente. Esto también permite realizar pruebas en distintos dominios que no conoce o no puede prever. Si desea anular este comportamiento predeterminado, puede configurar una lista de permitidos o lista de bloqueados para limitar con qué hosts trabajarán [!DNL Target].

Para administrar hosts, haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Hosts]**.

![](assets/hosts_list.png)

## Recognizing hosts {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

Para reconocer un host y agregarlo a la lista [!UICONTROL Hosts] , deben cumplirse las siguientes condiciones:

* At least one [!DNL Target] request must exist on the host
* Una página del host debe tener   lo siguiente:

   * Una referencia at.js o mbox.js precisa
   * Una [!DNL Target] solicitud o una [!DNL Target] solicitud global generada automáticamente

* The page with the [!DNL Target] request must be viewed in a browser

After the page is viewed, the host is listed in the [!UICONTROL Hosts] list, allowing you to manage it in an environment, as well as preview and launch activities and tests.

>[!NOTE]
>
>Esto engloba todos los servidores de desarrollo personal.

Cuando un host se añada a la lista [!UICONTROL Hosts], compruebe si se reconoce.

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Hosts]**.
1. Si no está en la lista, actualice el navegador. 


   By default, a newly recognized host is placed in the [!UICONTROL Production] environment. Se trata del entorno más seguro, dado que desde estos hosts no se pueden visualizar actividades inactivas.

1. (Condicional) Haga clic en el icono **[!UICONTROL Mover]** ( icono ![](/help/administrating-target/assets/icon-move.png) mover ) para mover el host al entorno [!UICONTROL Desarrollo], [!UICONTROL Ensayo]u otro.

>[!NOTE]
>
>The [!UICONTROL Production] environment cannot be deleted, even if you rename it. Se da por hecho que desde este se van a suministrar las actividades y pruebas finales y activas. El entorno predeterminado no permite la visualización de campañas inactivas.

## Sort or search the Hosts list {#section_068B23C9D8224EB78BC3B7C8580251B0}

To sort the [!UICONTROL Hosts] list, click any column header ([!UICONTROL Name], [!UICONTROL Environment], or [!UICONTROL Last Requested]) to sort the list in ascending or descending order.

To search the [!UICONTROL Hosts] list, type a search term in the [!UICONTROL Search Hosts] box.

## Create allowlists that specify hosts that are authorized to send Target requests to Target. {#allowlist}

You can create an allowlist that specifies hosts (domains) that are authorized to send [!DNL Target] requests to [!DNL Target]. Todos los demás hosts que generen solicitudes obtendrán una respuesta de error de autorización comentada. By default, any host that contains a [!DNL Target] request registers with [!DNL Target] in the [!UICONTROL Production] environment and has access to all active and approved activities. If this is not the desired approach, you can instead use the allowlist to record specific hosts that are eligible to make [!DNL Target] requests and receive [!DNL Target] content. All hosts will continue to display in the [!UICONTROL Hosts] list, and environments can still be used to group these hosts and assign different levels to each, such as whether the host can see active and/or inactive activities.

Para crear una lista de permitidos:

1. En la lista [!UICONTROL Hosts] , haga clic en **[!UICONTROL Autorizar hosts]**.
1. Active la **[!UICONTROL opción Activar hosts autorizados para el envío]** de contenido.
1. Add the desired hosts in the **[!UICONTROL Host contains]** box, as desired.

   Se pueden agregar varios hosts, cada uno en una línea.

1. Add the desired hosts in the **[!UICONTROL Host does not contains]** box, as desired.

   Se pueden agregar varios hosts, cada uno en una línea.

1. Haga clic en **[!UICONTROL Guardar]**.

If a [!DNL Target] request is made on an unauthorized host, the call will respond with `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**Prácticas** recomendadas de seguridad: Si utiliza la funcionalidad ubox de [!DNL Target], tenga en cuenta que esta lista de permitidos también controlará la lista de los dominios por los que pueden navegar [los redirectores](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) . Asegúrese de agregar los dominios a los que desee redirigir cuando utilice ubox como parte de la implementación. Si la lista de permitidos se deja sin especificar, no [!DNL Adobe] podrá comprobar las direcciones URL de redireccionamiento ni protegerse de posibles redirecciones maliciosas.
>
>La lista de permitidos tiene prioridad sobre los entornos. Debe borrar todos los hosts antes de utilizar la función de lista de permitidos y, a continuación, solo los hosts permitidos por la lista de permitidos aparecerán en la lista de hosts. A continuación, puede mover los hosts al entorno que quiera.

En ocasiones, aparecen dominios de otros sitios en los entornos. Un dominio aparece en la lista si el dominio realiza una llamada a su at.js o mbox.js. Por ejemplo, si alguien copia una de sus páginas web en su servidor, ese dominio aparecerá en nuestro entorno. También es probable que vea dominios de motores de araña, sitios de traducción de idiomas o unidades de disco locales.

En casos en los que `mboxHost` se pasa en una llamada de API, la conversión se registra para el entorno que se pasa. If no environment is passed, the host in the call defaults to [!UICONTROL Production].

You can also create a denylist that specifies hosts (domains) than cannot send [!DNL Target] requests to [!DNL Target] by adding the desired hosts in the [!UICONTROL Host Does Not Contain] box.

>[!NOTE]
>
>Dado que la lista Hosts autorizados se utiliza tanto para los hosts como para los hosts de redireccionamiento predeterminados, debe agregar todos los dominios existentes aprobados para utilizar el SDK de [!DNL Target] Javascript (at.js) [!DNL Adobe Target] Y ** todos los dominios utilizados en las direcciones URL de redireccionamiento predeterminadas de ubox. También debe agregar dominios similares nuevos a la lista de permitidos en el futuro.

## Delete a host {#section_F56355BA4BC54B078A1A8179BC954632}

Puede eliminar un host cuando ya no vaya a necesitarlo.

1. From the [!UICONTROL Hosts] list, click the **[!UICONTROL Delete]** icon.
1. Haga clic en **[!UICONTROL Eliminar]** para confirmar la acción.

>[!NOTE]
>
>El host volverá a aparecer si alguien se desplaza a una página que contiene una [!DNL Target] solicitud en el host.

## Resolución de problemas de hosts {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Pruebe los siguientes consejos de resolución de problemas si tiene algún problema con los hosts:

**El host no aparece en la lista de su cuenta.**

* Actualice la página [!UICONTROL Hosts] en el navegador.
* Confirme que la [!DNL Target] solicitud es correcta, incluida la referencia a at.js o mbox.js.
* Try browsing to one of the [!DNL Target] requests on the host. It&#39;s possible that no [!DNL Target] request on the host was ever rendered in a browser.

**La lista [!UICONTROL Hosts] contiene dominios aleatorios o desconocidos.**

A domain appears in this list if a request to [!DNL Target] is made from the domain. Con frecuencia, es posible ver dominios de motores de araña, sitios de traducción de idiomas o unidades de disco locales. En caso de que el dominio incluido en la lista no sea uno de los que el equipo usa, puede hacer clic en [!UICONTROL Eliminar] para eliminarlo.

**Mi [!DNL Target] solicitud devuelve /* sin visualización - host de mbox no autorizado */.**

If a [!DNL Target] request is made on an unauthorized host, the request will respond with /* no display - unauthorized mbox host */.
