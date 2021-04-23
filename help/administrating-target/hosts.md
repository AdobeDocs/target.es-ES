---
keywords: host;hosts;grupo de hosts;solución de problemas;prácticas recomendadas;ubox;redirecciones;redireccionamiento;lista de direcciones permitidas;lista de permitidos;lista de direcciones bloqueadas;lista de bloqueados
description: Aprenda a organizar sus sitios web y entornos de preproducción para facilitar la administración y la creación de informes separados en Adobe Target.
title: ¿Qué son los hosts y cómo puedo utilizarlos?
feature: Administración y configuración
role: Administrator
exl-id: 31c661c0-686d-440e-ad58-864fb853b1c4
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '1080'
ht-degree: 22%

---

# Hosts

Organice sus sitios y entornos de preproducción para facilitar la administración y la creación de informes separados en [!DNL Adobe Target].

El objetivo primordial de la administración de hosts reside en garantizar que ningún contenido inactivo se muestre por error en los sitios web. La administración de hosts también permite separar los datos de los informes por [entorno](/help/administrating-target/environments.md).

Un host es cualquier dominio desde el que se realiza una solicitud [!DNL Target]. En un sitio web, suele ser la propiedad `location.hostname` de la dirección URL que realiza la solicitud [!DNL Target].

De forma predeterminada, [!DNL Target] no se limita a un host que puede realizar [!DNL Target] solicitudes y recibir [!DNL Target] respuestas. Cuando los nuevos hosts realizan solicitudes, funcionan automáticamente. Este proceso también permite realizar pruebas en distintos dominios que no conoce o no puede anticipar. Si desea anular este comportamiento predeterminado, puede configurar una lista de permitidos o lista de bloqueados para limitar los hosts que funcionan con [!DNL Target].

Para administrar hosts, haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Hosts]**.

![](assets/hosts_list.png)

## Reconocer hosts {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

Para reconocer un host y agregarlo a la lista [!UICONTROL Hosts], se deben cumplir las siguientes condiciones:

* Debe existir al menos una solicitud [!DNL Target] en el host
* Una página del host debe tener   lo siguiente:

   * Una referencia a at.js precisa
   * Una solicitud [!DNL Target] o una solicitud [!DNL Target] global generada automáticamente

* La página con la solicitud [!DNL Target] debe verse en un explorador

Una vez que se ve la página, el host aparece enumerado en la lista [!UICONTROL Hosts], lo que le permite administrarlo en un entorno y obtener una vista previa de las actividades y pruebas e iniciarlas.

>[!NOTE]
>
>Esto engloba todos los servidores de desarrollo personal.

Cuando un host se añada a la lista [!UICONTROL Hosts], compruebe si se reconoce.

1. Haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Hosts]**.
1. Si no está en la lista, actualice el navegador. 


   De forma predeterminada, un host recién reconocido se coloca en el entorno [!UICONTROL Production]. El entorno [!UICONTROL Producción] es el entorno más seguro porque no permite que se vean actividades inactivas desde estos hosts.

1. (Condicional) Haga clic en el icono **[!UICONTROL Mover]** ( ![icono de mover](/help/administrating-target/assets/icon-move.png) ) para mover el host al [!UICONTROL Desarrollo], [!UICONTROL Ensayo] u otro entorno.

>[!NOTE]
>
>El entorno [!UICONTROL Production] no se puede eliminar aunque se le cambie el nombre. Se da por hecho que este entorno es donde se sirven las actividades y pruebas finales y activas. El entorno predeterminado no permite la visualización de campañas inactivas.

## Ordene o busque la lista Hosts {#section_068B23C9D8224EB78BC3B7C8580251B0}

Para ordenar la lista [!UICONTROL Hosts], haga clic en cualquier encabezado de columna ([!UICONTROL Nombre], [!UICONTROL Entorno] o [!UICONTROL Última solicitud]) para ordenar la lista en orden ascendente o descendente.

Para buscar la lista [!UICONTROL Hosts], escriba un término de búsqueda en el cuadro [!UICONTROL Buscar hosts].

## Cree listas de permitidos que especifiquen hosts con autorización para enviar solicitudes [!DNL Target] a [!DNL Target]. {#allowlist}

Puede crear una lista de permitidos que especifique los hosts (dominios) con autorización para enviar solicitudes [!DNL Target] a [!DNL Target]. Todos los demás hosts que generan solicitudes obtienen una respuesta de error de autorización comentada. De forma predeterminada, cualquier host que contenga una solicitud [!DNL Target] se registra con [!DNL Target] en el entorno [!UICONTROL Production] y tiene acceso a todas las actividades activas y aprobadas. Si no desea este método, puede usar la lista de permitidos para registrar hosts específicos que son aptos para realizar [!DNL Target] solicitudes y recibir [!DNL Target] contenido. Todos los hosts siguen mostrándose en la lista [!UICONTROL Hosts] y los entornos aún se pueden utilizar para agrupar estos hosts y asignar diferentes niveles a cada uno, como si el host puede ver actividades activas o inactivas.

Para crear una lista de permitidos:

1. En la lista [!UICONTROL Hosts], haga clic en **[!UICONTROL Autorizar hosts]**.
1. Active el botón **[!UICONTROL Habilitar los hosts autorizados para la entrega de contenido]**.
1. Agregue los hosts que desee en el cuadro **[!UICONTROL El host contiene]** , según desee.

   Se pueden agregar varios hosts, cada uno en una línea.

1. Agregue los hosts que desee en el cuadro **[!UICONTROL El host no contiene]**, como desee.

   Se pueden agregar varios hosts, cada uno en una línea.

1. Haga clic en **[!UICONTROL Guardar]**.

Si se realiza una solicitud [!DNL Target] en un host sin autorización, la llamada responde con `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**Prácticas** recomendadas de seguridad: Si utiliza la funcionalidad ubox de  [!DNL Target], esta lista de permitidos también controla la lista de dominios a los que navegan los  [](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) redirectores. Asegúrese de añadir todos los dominios a los que desee redirigir cuando utilice ubox como parte de la implementación. Si la lista de permitidos se deja sin especificar, [!DNL Adobe] no puede comprobar las direcciones URL de redireccionamiento ni protegerse de posibles redirecciones maliciosas.
>
>La lista de permitidos tiene prioridad sobre los entornos. Borre todos los hosts antes de utilizar la función de lista de permitidos y, a continuación, solo los hosts permitidos por la lista de permitidos aparecerán en la lista de hosts. A continuación, puede mover los hosts al entorno que quiera.

En ocasiones, aparecen dominios de otros sitios en los entornos. Si el dominio llama a at.js, aparecerá un dominio en la lista. Por ejemplo, si alguien copia una de sus páginas web en su servidor, ese dominio aparecerá en nuestro entorno. También es probable que vea dominios de motores de araña, sitios de traducción de idiomas o unidades de disco locales.

En casos en los que `mboxHost` se pasa en una llamada de API, la conversión se registra para el entorno que se pasa. Si no se pasa ningún entorno, el host de la llamada toma el valor predeterminado [!UICONTROL Production].

También puede crear una  de lista de bloqueados que especifique hosts (dominios) que no puedan enviar solicitudes [!DNL Target] a [!DNL Target] agregando los hosts que desee en el cuadro [!UICONTROL El host no contiene].

>[!NOTE]
>
>La lista [!UICONTROL Hosts autorizados] se utiliza tanto para hosts [!DNL Target] como para hosts de redirección predeterminados. Agregue todos los dominios existentes aprobados para utilizar el [!DNL Adobe Target] SDK de JavaScript (at.js) *AND* todos los dominios utilizados en las direcciones URL de redireccionamiento predeterminadas de ubox. Agregue dominios similares nuevos a la lista de permitidos en el futuro.

## Eliminar un host {#section_F56355BA4BC54B078A1A8179BC954632}

Puede eliminar un host cuando ya no vaya a necesitarlo.

1. En la lista [!UICONTROL Hosts], haga clic en el icono **[!UICONTROL Eliminar]**.
1. Haga clic en **[!UICONTROL Eliminar]** para confirmar la acción.

>[!NOTE]
>
>El host vuelve a aparecer en la lista si alguien abre una página que contiene una solicitud [!DNL Target] en el host.

## Resolución de problemas de hosts {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Pruebe los siguientes consejos de resolución de problemas si tiene algún problema con los hosts:

**El host no aparece en la lista de la cuenta.**

* Actualice la página [!UICONTROL Hosts] en el navegador.
* Confirme que la solicitud [!DNL Target] es correcta, incluida la referencia a at.js .
* Intente ir a una de las [!DNL Target] solicitudes en el host. Es posible que no se haya procesado ninguna solicitud [!DNL Target] en el host en un explorador.

**La lista [!UICONTROL Hosts] contiene dominios aleatorios o desconocidos.**

Un dominio aparece en esta lista si se realiza una solicitud a [!DNL Target] desde el dominio. Con frecuencia, es posible ver dominios de motores de araña, sitios de traducción de idiomas o unidades de disco locales. En caso de que el dominio incluido en la lista no sea uno de los que el equipo usa, puede hacer clic en [!UICONTROL Eliminar] para eliminarlo.

**Mi  [!DNL Target] solicitud devuelve /* sin visualización: host mbox sin autorización */.**

Si se realiza una solicitud [!DNL Target] en un host sin autorización, la solicitud responde con /* sin visualización: host mbox sin autorización */.
