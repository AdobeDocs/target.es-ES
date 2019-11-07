---
keywords: host;hosts;grupo de hosts;entorno;solución de problemas;prácticas recomendadas
description: Organice sus sitios y entornos de preproducción para facilitar la administración y la creación de informes individuales.
title: Hosts
topic: Standard
uuid: c7682269-4ec2-4a0f-b053-7e0ec77f4604
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Hosts{#hosts}

Organice sus sitios y entornos de preproducción para facilitar la administración y la creación de informes individuales.

## Hosts {#concept_516BB01EBFBD4449AB03940D31AEB66E}

Organice sus sitios y entornos de preproducción para facilitar la administración y la creación de informes individuales.

Una funcionalidad de [!DNL Target Classic] era similar. Los grupos de hosts de [!DNL Target Classic] se denominaban “entornos” en [!DNL Target Standard/Premium].

El objetivo primordial de la administración de hosts reside en garantizar que ningún contenido inactivo se muestre por error en los sitios web. La administración de hosts también permite separar los datos de los informes según el entorno.

Un host es un servidor web (o dominio web) desde el que se proporciona contenido durante cualquiera de las fases del proyecto. Se reconoce cualquier host que hospede un mbox.

Los hosts se agrupan en entornos para facilitar la administración. Así, se pueden tener decenas de hosts agrupados en dos o tres entornos. Los entornos preestablecidos son los de producción, ensayo y desarrollo. Puede añadir entornos nuevos y cambiarles el nombre, si lo desea.

El entorno predeterminado se denomina Producción. El entorno predeterminado no se puede eliminar aunque se le cambie el nombre. [!DNL Target] da por hecho que es desde este entorno desde donde se van a suministrar las actividades y pruebas finales y aprobadas.

Cuando se recibe una solicitud de mbox procedente de sitios web o dominios nuevos, estos dominios siempre se incluyen en el entorno de producción. La configuración del entorno Producción no se puede alterar, lo cual hace que los sitios nuevos o desconocidos solo puedan ver el contenido que esté aprobado y listo. La administración de hosts también permite garantizar la calidad de las nuevas actividades y el contenido en los entornos de prueba, ensayo y desarrollo antes de activar las actividades.

Target no limita un host que pueda enviar y recibir mboxes, de modo que cuando aparecen servidores o dominios nuevos, funcionan automáticamente (si no se ha configurado una lista de direcciones permitidas o de direcciones bloqueadas). Esto permite, asimismo, realizar pruebas de anuncios en distintos dominios que no conoce o no puede prever.

Para administrar los hosts y entornos, haga clic en **[!UICONTROL Configuración]** &gt; **[!UICONTROL Hosts]**.

![](assets/hosts_list.png)

## Reconocer hosts {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

Información sobre las condiciones que hay que cumplir para que [!DNL Target] reconozca un host y lo añada a la lista Hosts.

Para reconocer un host es necesario cumplir las condiciones siguientes:

* Debe existir al menos un mbox en el host.
* Una página del host debe tener   lo siguiente:

   * Una referencia precisa a [!DNL mbox.js].
   * Un mbox o una llamada de mbox global generada automáticamente

* La página con el mbox se debe ver en un navegador.

Tras ver la página, el host se incluye en la lista [!UICONTROL Hosts], lo que permite administrarla en el entorno, así como obtener una vista previa de las actividades y pruebas e iniciarlas.

>[!NOTE] {class="- topic/note "}
>
>Esto engloba todos los servidores de desarrollo personal.

Cuando un host se añada a la lista [!UICONTROL Hosts], compruebe si se reconoce.

1. Haga clic en **[!UICONTROL Configuración]** &gt; **[!UICONTROL Hosts]**.
1. Si no está en la lista, actualice el navegador. 
De forma predeterminada, un host recién reconocido se incluye en el entorno Producción. Se trata del entorno más seguro, dado que desde estos hosts no se pueden visualizar actividades inactivas.
1. (Condicional) Mueva el host al entorno de desarrollo o ensayo.

>[!NOTE]
>
>El entorno Producción no se puede eliminar aunque se le cambie el nombre. Se da por hecho que desde este se van a suministrar las actividades y pruebas finales y activas. El entorno predeterminado no permite la visualización de campañas inactivas.

## Administrar hosts y entornos {#concept_90573F5A52E04600A8C3C5897880C10F}

Información útil para administrar hosts y entornos (grupos de hosts), incluido cómo configurar el host predeterminado para los informes, crear listas de direcciones permitidas, cambiar el nombre de un entorno, mover un host a otro entorno y eliminar un host o un entorno.


Para acceder a la lista de [!UICONTROL Hosts], haga clic en **[!UICONTROL Configuración]** &gt; **[!UICONTROL Hosts]**.

![](assets/hosts_list.png)

## Filtrar, ordenar o buscar la lista Hosts {#section_068B23C9D8224EB78BC3B7C8580251B0}

Para filtrar las listas [!UICONTROL Hosts] por entorno, haga clic en la lista desplegable **[!UICONTROL Todos]y luego seleccione un entorno (Producción, Ensayo, Desarrollo o un entorno personalizado que haya creado).**

Para ordenar la lista [!UICONTROL Hosts], haga clic en cualquier encabezado de columna (Nombre, Entorno o Última solicitud) para ordenar la lista en orden ascendente o descendente.

Para buscar la lista [!UICONTROL Hosts], escriba un término de búsqueda en el cuadro Buscar.

## Seleccionar varios hosts   {#section_EF3B458475184B7EA997C3559714397C}

Para seleccionar varios hosts, marque las casillas de verificación que hay junto a la columna [!UICONTROL Nombre] de los hosts que quiera. Luego puede mover o eliminar todos los hosts seleccionados.

## Crear un entorno   {#section_32097D0993724DF3A202D164D3F18674}

1. En la lista [!UICONTROL Hosts], haga clic en la ficha **[!UICONTROL Entornos].**
1. Haga clic en **[!UICONTROL Crear entorno]**.
1. Elija un nombre descriptivo para el entorno.
1. Indique el modo activo del entorno: [!UICONTROL Actividades activas] o [!UICONTROL Actividades activas e inactivas].
1. Haga clic en **[!UICONTROL Guardar]**.

## Definir el host predeterminado para informes {#section_4F8539B07C0C45E886E8525C344D5FB0}

Puede seleccionar el entorno que quiere usar como predeterminado para todos los informes de actividad.

Si utiliza el de producción como predeterminado, todos los hosts desconocidos se añaden automáticamente aquí y los datos de los informes se incluyen desde ahí en la vista de informe predeterminada. Al crear un entorno “limpio”, se asegura de que se incluyan solo los sitios o dominios principales.

Para establecer el entorno predeterminado en la creación de informes:

1. En la lista [!UICONTROL Hosts], haga clic en la ficha **[!UICONTROL Configuración].**
1. Seleccione el host predeterminado en la lista desplegable **[!UICONTROL Configuración del entorno].**
1. Haga clic en **[!UICONTROL Guardar]**.

>[!NOTE]
>
>Los usuarios de [!DNL Recommendations] deben volver a generar la base de datos de comportamiento y la base de datos de producto si los hosts se cambian de grupo de hosts.

## Crear listas de direcciones permitidas que incluyan los hosts que están autorizados a enviar llamadas de mbox a Target. {#section_0AF7F56C386A42C381AF704DEF08D5CC}

Puede crear una lista de elementos permitidos que especifique los hosts (dominios) con autorización para enviar llamadas de mbox a [!DNL Target]. Todos los demás hosts que generen llamadas obtendrán una respuesta de error de autorización comentada. Todo host que contenga una llamada de mbox se registra en el entorno Producción de [!DNL Target] de forma predeterminada y tiene acceso a todas las actividades activas y aprobadas. Si este no es el método deseado, puede usar la lista de direcciones permitidas para registrar los hosts específicos que pueden realizar llamadas de mbox y recibir contenido de [!DNL Target]. Todos los hosts seguirán apareciendo en la lista [!UICONTROL Hosts] y los entornos podrán seguir utilizándose para agrupar estos hosts y asignar distintos niveles a cada uno, como, por ejemplo, si el host puede ver campañas activas o inactivas.

Para crear una lista de direcciones permitidas:

1. En la lista [!UICONTROL Hosts], haga clic en la ficha **[!UICONTROL Configuración].**
1. Marque la casilla de verificación **[!UICONTROL Habilitar los hosts autorizados para la entrega de contenido].**
1. Añada los hosts que quiera en el cuadro **[!UICONTROL El host contiene].**

   Se pueden agregar varios hosts, cada uno en una línea.

1. Haga clic en **[!UICONTROL Guardar]**.

Si se realiza una llamada de mbox en un host sin autorización, la llamada responde con `/* no display - unauthorized mbox host */`.

La lista de direcciones permitidas tiene prioridad sobre los entornos. Se recomienda borrar todos los hosts antes de usar la función de lista de elementos permitidos. De esta forma, en la lista de hosts solo aparecerán aquellos permitidos. A continuación, puede mover los hosts al entorno que quiera.

En ocasiones, aparecen dominios de otros sitios en los entornos. Los dominios que efectúen una llamada a su mbox.js aparecerán en la lista. Por ejemplo, si alguien copia una de sus páginas web en su servidor, ese dominio aparecerá en nuestro entorno. También es probable que vea dominios de motores de araña, sitios de traducción de idiomas o unidades de disco locales.

En casos en los que `mboxHost` se pasa en una llamada de API, la conversión se registra para el entorno que se pasa. Si no se pasa ningún entorno, el valor predeterminado del host de la llamada será Producción.

También puede crear una lista de direcciones bloqueadas que incluya los hosts (dominios) que no pueden enviar llamadas de mbox a [!DNL Target]. Para ello, añada los hosts que quiera al cuadro [!UICONTROL El host no contiene].

## Cambiar el nombre de un entorno {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. En la lista [!UICONTROL Hosts], haga clic en la ficha **[!UICONTROL Entornos].**
1. Pase el ratón sobre el entorno que quiera y luego haga clic en el icono **[!UICONTROL Editar].**
1. Cambie el nombre del entorno.
1. Haga clic en **[!UICONTROL Guardar]**.

## Mover un host a otro entorno {#section_9F52549958BD485EB74FE78C32773D2A}

1. En la lista [!UICONTROL Hosts], pase el ratón sobre el host que quiera mover.
1. Haga clic en el icono **[!UICONTROL Mover].**
1. Seleccione el entorno que quiera en la lista desplegable y luego haga clic en el icono de la marca de verificación.

## Eliminación de un host {#section_F56355BA4BC54B078A1A8179BC954632}

Puede eliminar un host cuando ya no vaya a necesitarlo.

1. En la lista [!UICONTROL Hosts], pase el ratón sobre el host que quiera eliminar.
1. Haga clic en el icono **[!UICONTROL Eliminar].**
1. Haga clic en **[!UICONTROL Eliminar]para confirmar la acción.**

>[!NOTE]
>
>El host vuelve a aparecer en la lista si alguien abre una página con mbox en el host.

## Eliminar un entorno {#section_737F8869612047868D03FC755B1223D3}

Puede eliminar un entorno que ya no vaya a necesitar.

1. En la lista [!UICONTROL Hosts], haga clic en la ficha **[!UICONTROL Entornos].**
1. Pase el ratón sobre el entorno que quiera eliminar.
1. Haga clic en el icono **[!UICONTROL Eliminar].**
1. Haga clic en **[!UICONTROL Eliminar]para confirmar la acción.**

>[!NOTE]
>
>El entorno Producción no se puede eliminar aunque se le cambie el nombre.

## Resolución de problemas de hosts {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Prácticas recomendadas para administrar y resolver problemas de hosts en [!DNL Adobe Target].

Pruebe los siguientes consejos de resolución de problemas si tiene algún problema con los hosts:

**El host no aparece en la lista de mbox de la cuenta.**

* Actualice la página [!UICONTROL Hosts] en el navegador.
* Confirme que el código de mbox es correcto, incluida la referencia a [!DNL mbox.js].
* Intente ir a uno de los mbox en el host. Es posible que no se haya presentado ningún mbox del host en un navegador.

**La lista[!UICONTROL Hosts]contiene dominios aleatorios o desconocidos.**

Cuando se efectúa una llamada a [!DNL Target] desde un dominio, este aparecerá en la lista. Con frecuencia, es posible ver dominios de motores de araña, sitios de traducción de idiomas o unidades de disco locales. En caso de que el dominio incluido en la lista no sea uno de los que el equipo usa, puede hacer clic en [!UICONTROL Eliminar] para eliminarlo.

**Mi llamada de mbox devuelve /* sin visualización: host mbox sin autorización */.**

Si se realiza una llamada de mbox en un host sin autorización, la llamada responderá con /* sin visualización: host mbox sin autorización */.

## Recommendations: filtrar colecciones y exclusiones por entorno (grupo de hosts)

![Distintivo Premium](/help/assets/premium.png)

Puede obtener una vista previa del contenido de las colecciones y exclusiones de Recommendations para un entorno seleccionado (grupo de hosts).

>[!NOTE]
>Las actividades de Recommendations están disponibles como parte de la solución Target Premium. No están disponibles en Target Standard sin una licencia de Target Premium.

El grupo de hosts puede utilizarse para separar los elementos disponibles en el catálogo para usos diferentes. Por ejemplo, puede utilizar grupos de hosts para entornos de desarrollo y producción, marcas diferentes o regiones geográficas diferentes. De forma predeterminada, la vista previa de los resultados en Búsqueda de catálogo, Colecciones y Exclusiones se basa en el grupo de hosts predeterminado. (También puede seleccionar otro grupo de hosts para obtener una vista previa de los resultados mediante el filtro Entorno). De forma predeterminada, los elementos recién añadidos están disponibles en todos los grupos de hosts a menos que se especifique un ID de entorno al crear o actualizar el elemento. Las recomendaciones enviadas dependen del grupo de hosts especificado en la solicitud.

Si no ve sus productos, asegúrese de que esté usando el grupo de hosts correcto. Por ejemplo, si configura que la recomendación use un entorno de ensayo y establece el grupo de hosts en Ensayo, puede que tenga que volver a crear las colecciones en el entorno de ensayo para que se puedan mostrar los productos. Para ver qué productos están disponibles en cada entorno, use Búsqueda en catálogo con cada entorno. También puede obtener una vista previa del contenido de las colecciones y exclusiones de Recommendations para un entorno seleccionado (grupo de hosts).

>[!NOTE]
>Después de cambiar el entorno seleccionado, debe hacer clic en Buscar para actualizar los resultados devueltos.

El filtro Entorno está disponible en los siguientes lugares de la interfaz de usuario de Target:

* Búsqueda en el catálogo ([!UICONTROL Recommendations &gt; Buscar en el catálogo])
* Cuadro de diálogo Crear colección ([!UICONTROL Recommendations &gt; Colecciones &gt; Crear nuevo])
* Cuadro de diálogo Actualizar colección ([!UICONTROL Recommendations &gt; Colecciones &gt; Editar])
* Cuadro de diálogo Crear exclusión ([!UICONTROL Recommendations &gt; Exclusiones &gt; Crear nuevo])
* Cuadro de diálogo Actualizar exclusión ([!UICONTROL Recommendations &gt; Exclusiones &gt; Editar])
