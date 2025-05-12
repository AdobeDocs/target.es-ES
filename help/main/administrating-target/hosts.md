---
keywords: host;hosts;grupo de hosts;solución de problemas;prácticas recomendadas;ubox;redirecciones;redireccionamiento;lista blanca;lista de permitidos;lista negra;lista de bloqueados
description: Aprenda a organizar sus sitios web y entornos de preproducción para facilitar la administración y la creación de informes separados en Adobe Target.
title: ¿Qué son los hosts y cómo los utilizo?
feature: Administration & Configuration
role: Admin
exl-id: 31c661c0-686d-440e-ad58-864fb853b1c4
source-git-commit: 0ab5b7d7cbfaef86b9a045883f597900dba72416
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 17%

---

# Hosts

Organice sus sitios y entornos de preproducción para facilitar la administración y la creación de informes separados en [!DNL Adobe Target].

El objetivo primordial de la administración de hosts reside en garantizar que ningún contenido inactivo se muestre por error en los sitios web. La administración de hosts también le permite separar los datos del informe por [entorno](/help/main/administrating-target/environments.md).

Un host es cualquier dominio desde el que se realiza una solicitud [!DNL Target]. En un sitio web, normalmente es la propiedad `location.hostname` de la dirección URL que realiza la solicitud [!DNL Target].

De manera predeterminada, [!DNL Target] no limita un host que puede realizar [!DNL Target] solicitudes y recibir [!DNL Target] respuestas. Cuando los nuevos hosts realizan solicitudes, funcionan automáticamente. Este proceso también permite realizar pruebas en dominios diferentes que no conoce o no puede anticipar. Si desea anular este comportamiento predeterminado, puede configurar una lista de permitidos o lista de bloqueados para limitar qué hosts funcionan con [!DNL Target].

{{permissions-update}}

Para administrar los hosts, haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Hosts]**.

## Reconocer hosts {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

Para reconocer un host y agregarlo a la lista [!UICONTROL Hosts], se deben cumplir las siguientes condiciones:

* Debe existir al menos una solicitud [!DNL Target] en el host
* Una página del host debe tener lo siguiente:

   * Una referencia precisa de at.js
   * Una solicitud [!DNL Target] o una solicitud [!DNL Target] global generada automáticamente

* La página con la solicitud [!DNL Target] debe verse en un explorador

Una vez vista la página, el host se enumera en la lista [!UICONTROL Hosts], lo que le permite administrarlo en un entorno y obtener una vista previa e iniciar actividades y pruebas.

>[!NOTE]
>
>Esto engloba todos los servidores de desarrollo personal.

Después de agregar un host a la lista [!UICONTROL Host], asegúrese de que se reconoce el host.

1. Haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Hosts]**.
1. Si no está en la lista, actualice el navegador.

   De manera predeterminada, un host recién reconocido se coloca en el entorno [!UICONTROL Production]. El entorno [!UICONTROL Production] es el más seguro porque no permite que se vean actividades inactivas desde estos hosts.

1. (Condicional) Haga clic en el icono **[!UICONTROL Move]** ( ![icono de mover](/help/main/assets/icons/MoveTo.svg) ) para mover el host a [!UICONTROL Development], [!UICONTROL Staging] u otro entorno.

>[!NOTE]
>
>El entorno [!UICONTROL Production] no se puede eliminar aunque se le cambie el nombre. Se da por hecho que en este entorno es donde se proporcionan las actividades y pruebas finales y activas. El entorno predeterminado no permite la visualización de campañas inactivas.

## Ordenar o buscar en la lista Hosts {#section_068B23C9D8224EB78BC3B7C8580251B0}

Para ordenar la lista [!UICONTROL Hosts], haga clic en cualquier encabezado de columna ([!UICONTROL Name], [!UICONTROL Environment] o [!UICONTROL Last Requested]) para ordenar la lista en orden ascendente o descendente.

Para buscar en la lista [!UICONTROL Hosts], escriba un término de búsqueda en el cuadro [!UICONTROL Search Hosts].

## Cree listas de permitidos que especifiquen hosts con autorización para enviar [!DNL Target] solicitudes a [!DNL Target]. {#allowlist}

Puede crear una lista de permitidos que especifique los hosts (dominios) con autorización para enviar [!DNL Target] solicitudes a [!DNL Target]. Todos los demás hosts que generan solicitudes obtienen una respuesta de error de autorización comentada. De manera predeterminada, cualquier host que contenga una solicitud [!DNL Target] se registra con [!DNL Target] en el entorno [!UICONTROL Production] y tiene acceso a todas las actividades activas y aprobadas. Si no desea este método, puede usar la lista de permitidos para registrar hosts específicos que cumplan los requisitos para realizar [!DNL Target] solicitudes y recibir contenido de [!DNL Target]. Todos los hosts seguirán mostrándose en la lista [!UICONTROL Hosts], y se podrán seguir utilizando entornos para agrupar estos hosts y asignar niveles diferentes a cada uno, por ejemplo, si el host puede ver actividades activas o inactivas.

Para crear una lista de permitidos:

1. En la lista [!UICONTROL Hosts], haga clic en **[!UICONTROL Authorize Hosts]**.
1. Habilite la opción **[!UICONTROL Enable Authorized Hosts for content delivery]**.
1. Agregue los hosts que desee en el cuadro **[!UICONTROL Host contains]**.

   Se pueden agregar varios hosts, cada uno en una línea.

1. Agregue los hosts que desee en el cuadro **[!UICONTROL Host does not contains]**.

   Se pueden agregar varios hosts, cada uno en una línea.

1. Haga clic en **[!UICONTROL Save]**.

Si se realiza una solicitud [!DNL Target] en un host sin autorización, la llamada responde con `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**Prácticas recomendadas de seguridad**: Si usas la funcionalidad ubox de [!DNL Target], esta lista de permitidos también controla la lista de dominios a los que pueden navegar tus [redirectores](https://experienceleague.adobe.com/docs/target-dev/developer/implement-email/working-with-redirectors.html?lang=es){target=_blank}. Asegúrese de agregar los dominios a los que desee redirigir al utilizar ubox como parte de la implementación. Si no se especifica la lista de permitidos, [!DNL Adobe] no podrá comprobar las direcciones URL de redireccionamiento ni protegerse de posibles redireccionamientos malintencionados.
>
>La lista de permitidos tiene prioridad sobre los entornos. Borre todos los hosts antes de utilizar la función de lista de permitidos y, a continuación, en la lista de hosts solo aparecerán los hosts permitidos por la lista de permitidos. A continuación, puede mover los hosts al entorno que quiera.

En ocasiones, aparecen dominios de otros sitios en los entornos. Si el dominio llama a at.js, aparecerá un dominio en la lista. Por ejemplo, si alguien copia una de sus páginas web en su servidor, ese dominio aparecerá en nuestro entorno. También es probable que vea dominios de motores de araña, sitios de traducción de idiomas o unidades de disco locales.

En casos en los que `mboxHost` se pasa en una llamada de API, la conversión se registra para el entorno que se pasa. Si no se pasa ningún entorno, el valor predeterminado del host de la llamada será [!UICONTROL Production].

También puede crear una lista de bloqueados de que especifique los hosts (dominios) que no pueden enviar [!DNL Target] solicitudes a [!DNL Target] agregando los hosts que desee en el cuadro [!UICONTROL Host Does Not Contain].

>[!NOTE]
>
>La lista [!UICONTROL Authorized Hosts] se usa tanto para los hosts [!DNL Target] como para los hosts de redirección predeterminados. Agregue todos los dominios existentes aprobados para utilizar [!DNL Adobe Target] JavaScript SDK (at.js) *Y* todos los dominios utilizados en las URL de redireccionamiento predeterminadas de ubox. Añada nuevos dominios similares a la lista de permitidos en el futuro.

## Eliminación de un host {#section_F56355BA4BC54B078A1A8179BC954632}

Puede eliminar un host cuando ya no vaya a necesitarlo.

1. En la lista [!UICONTROL Hosts], haga clic en el icono **[!UICONTROL Delete]** ( ![Eliminar icono](/help/main/assets/icons/DeleteOutline.svg) ).
1. Haga clic en **[!UICONTROL Delete]** para confirmar la eliminación.

>[!NOTE]
>
>El host vuelve a aparecer en la lista si alguien abre una página que contiene una solicitud [!DNL Target] en el host.

## Resolución de problemas de hosts {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Pruebe los siguientes consejos de resolución de problemas si tiene algún problema con los hosts:

**El host no aparece en la lista de su cuenta.**

* Actualice la página [!UICONTROL Hosts] en el explorador.
* Confirme que la solicitud [!DNL Target] es correcta, incluida la referencia de at.js.
* Intente navegar a una de las [!DNL Target] solicitudes en el host. Es posible que nunca se haya procesado ninguna solicitud [!DNL Target] del host en un explorador.

**Los dominios aleatorios o desconocidos aparecen en la lista [!UICONTROL Host].**

Aparece un dominio en esta lista si se realiza una solicitud a [!DNL Target] desde el dominio. Con frecuencia, es posible ver dominios de motores de araña, sitios de traducción de idiomas o unidades de disco locales. Si el dominio que aparece en la lista no es uno de los que usa su equipo, puede hacer clic en [!UICONTROL Delete] para quitarlo.

**Mi solicitud [!DNL Target] devuelve /&#42; sin visualización - host de mbox no autorizado &#42;/.**

Si se realiza una solicitud [!DNL Target] en un host sin autorización, la solicitud responde con /&#42; sin visualización: host mbox sin autorización &#42;/.
