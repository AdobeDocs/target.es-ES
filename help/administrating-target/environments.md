---
keywords: environment;troubleshooting;best practices;ubox;redirects;redirect;whitelist;blacklist;blocklist;allowlist
description: Organice sus sitios y entornos de preproducción para facilitar la administración y la creación de informes individuales.
title: Entornos
topic: Standard
uuid: c7682269-4ec2-4a0f-b053-7e0ec77f4604
translation-type: tm+mt
source-git-commit: 3edb13b196240bb1918fc66edcc653936e32d3ef
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 67%

---


# Entornos

Organice sus sitios y entornos de preproducción para facilitar la administración y la creación de informes individuales.

Los hosts se agrupan en entornos para facilitar la administración. Así, se pueden tener decenas de hosts agrupados en dos o tres entornos. The preset environments include [!UICONTROL Production], [!UICONTROL Staging], and [!UICONTROL Development]. Puede añadir entornos nuevos y cambiarles el nombre, si lo desea.

One environment, the default environment, is pre-named [!UICONTROL Production]. El entorno predeterminado no se puede eliminar aunque se le cambie el nombre. [!DNL Target] da por hecho que es desde este entorno desde donde se van a suministrar las actividades y pruebas finales y aprobadas.

When a [!DNL Target] request is received from new websites or domains, these new domains always appear in the [!UICONTROL Production] environment. The [!UICONTROL Production] environment cannot have its settings changed, so unknown or new sites are guaranteed to see only content that is active and ready. La administración de hosts también permite garantizar la calidad de las nuevas actividades y el contenido en los entornos de prueba, ensayo y desarrollo antes de activar las actividades.

Para administrar entornos, haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Entornos]**.

![lista Entornos](/help/administrating-target/assets/environments.png)

## Añadir un entorno {#section_32097D0993724DF3A202D164D3F18674}

1. En la lista [!UICONTROL Entornos] , haga clic en **[!UICONTROL Añadir Entorno]**.
1. Elija un nombre descriptivo para el entorno.
1. Indique el modo activo del entorno: [!UICONTROL Actividades activas] o [!UICONTROL Actividades activas e inactivas].
1. Haga clic en **[!UICONTROL Guardar]**.

## Set the default environment for reporting {#section_4F8539B07C0C45E886E8525C344D5FB0}

Puede seleccionar el entorno que quiere usar como predeterminado para todos los informes de actividad.

If you use [!UICONTROL Production] as your default, all unknown hosts automatically are added here and report data from there is included in the default report view. Al crear un entorno “limpio”, se asegura de que se incluyan solo los sitios o dominios principales.

Para establecer el entorno predeterminado en la creación de informes:

1. En la lista [!UICONTROL Entornos] , haga clic en el icono Estrella

>[!NOTE]
>
>Los usuarios de [!DNL Recommendations] deben volver a generar la base de datos de comportamiento y la base de datos de producto si los hosts se cambian de grupo de hosts.

## Change the name of an environment {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. En la lista [!UICONTROL Entorno] , haga clic en el icono **[!UICONTROL Editar]** .
1. Cambie el nombre del entorno.
1. Haga clic en **[!UICONTROL Guardar]**.

## Delete an environment {#section_737F8869612047868D03FC755B1223D3}

Puede eliminar un entorno que ya no vaya a necesitar.

1. En la lista [!UICONTROL Entorno] , haga clic en el icono **[!UICONTROL Eliminar]** .
1. Haga clic en **[!UICONTROL Eliminar]** para confirmar la acción.

>[!NOTE]
>
>You cannot delete the [!UICONTROL Production] environment, but you can rename it.

## Recommendations: filtrar colecciones y exclusiones por entorno (grupo de hosts)

![Distintivo Premium](/help/assets/premium.png)

Puede obtener una vista previa del contenido de las colecciones y exclusiones de Recommendations para un entorno seleccionado (grupo de hosts).

>[!NOTE]
>
>Recommendations activities are available as part of the [!DNL Target] Premium solution. No están disponibles en [!DNL Target] Standard sin una licencia de [!DNL Target] Premium.

Se puede utilizar un entorno para separar los elementos disponibles en el catálogo para distintos usos. For example, you can use host groups for [!UICONTROL Development] and [!UICONTROL Production] environments, different brands, or different geographies. De forma predeterminada, la vista previa de los resultados en Búsqueda de catálogo, Colecciones y Exclusiones se basa en el grupo de hosts predeterminado. (También puede seleccionar otro grupo de hosts para obtener una vista previa de los resultados mediante el filtro Entorno). De forma predeterminada, los elementos recién añadidos están disponibles en todos los grupos de hosts a menos que se especifique un ID de entorno al crear o actualizar el elemento. Las recomendaciones enviadas dependen del grupo de hosts especificado en la solicitud.

Si no ve sus productos, asegúrese de que esté usando el grupo de hosts correcto. Por ejemplo, si configura que la recomendación use un entorno de ensayo y establece el grupo de hosts en Ensayo, puede que tenga que volver a crear las colecciones en el entorno de ensayo para que se puedan mostrar los productos. Para ver qué productos están disponibles en cada entorno, use Búsqueda en catálogo con cada entorno. También puede obtener una vista previa del contenido de las colecciones y exclusiones de Recommendations para un entorno seleccionado (grupo de hosts).

>[!NOTE]
>Después de cambiar el entorno seleccionado, debe hacer clic en Buscar para actualizar los resultados devueltos.

The [!UICONTROL Environment] filter is available from the following places in the Target UI:

* Búsqueda en el catálogo ([!UICONTROL Recommendations > Buscar en el catálogo])
* Cuadro de diálogo Crear colección ([!UICONTROL Recommendations > Colecciones > Crear nuevo])
* Cuadro de diálogo Actualizar colección ([!UICONTROL Recommendations > Colecciones > Editar])
* Cuadro de diálogo Crear exclusión ([!UICONTROL Recommendations > Exclusiones > Crear nuevo])
* Cuadro de diálogo Actualizar exclusión ([!UICONTROL Recommendations > Exclusiones > Editar])