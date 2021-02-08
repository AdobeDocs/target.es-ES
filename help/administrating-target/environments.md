---
keywords: entorno;solución de problemas;prácticas recomendadas;ubox;redirecciones;redireccionamiento;lista blanca;lista negra;lista de bloqueados;lista de permitidos
description: Aprenda a utilizar entornos en Adobe Target para organizar sus sitios y entornos de preproducción para facilitar la administración y el sistema de informes separado.
title: ¿Qué son los Entornos y cómo los uso?
feature: Administration & Configuration
role: Administrator
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 63%

---


# Entornos

Organice sus sitios y entornos de preproducción para facilitar la administración y la creación de informes individuales.

Los hosts se agrupan en entornos para facilitar la administración. Así, se pueden tener decenas de hosts agrupados en dos o tres entornos. Los entornos preestablecidos incluyen [!UICONTROL Producción], [!UICONTROL Ensayo] y [!UICONTROL Desarrollo]. Puede añadir entornos nuevos y cambiarles el nombre, si lo desea.

Un entorno, el entorno predeterminado, se denomina previamente [!UICONTROL Producción]. El entorno predeterminado no se puede eliminar aunque se le cambie el nombre. [!DNL Target] da por hecho que es desde este entorno desde donde se van a suministrar las actividades y pruebas finales y aprobadas.

Cuando se recibe una solicitud [!DNL Target] de nuevos sitios Web o dominios, estos nuevos dominios siempre aparecen en el entorno [!UICONTROL Producción]. El entorno [!UICONTROL Producción] no puede cambiar su configuración, por lo que los sitios nuevos o desconocidos solo verán contenido que esté activo y listo. La administración de hosts también permite garantizar la calidad de las nuevas actividades y el contenido en los entornos de prueba, ensayo y desarrollo antes de activar las actividades.

Para administrar entornos, haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Entornos]**.

![Lista entornos](/help/administrating-target/assets/environments.png)

## Añadir un entorno {#section_32097D0993724DF3A202D164D3F18674}

1. En la lista [!UICONTROL Entornos], haga clic en **[!UICONTROL Añadir Entorno]**.
1. Elija un nombre descriptivo para el entorno.
1. Indique el modo activo del entorno: [!UICONTROL Actividades activas] o [!UICONTROL Actividades activas e inactivas].
1. Haga clic en **[!UICONTROL Guardar]**.

## Definir el entorno predeterminado para sistema de informes {#section_4F8539B07C0C45E886E8525C344D5FB0}

Puede seleccionar el entorno que quiere usar como predeterminado para todos los informes de actividad.

Si utiliza [!UICONTROL Producción] como opción predeterminada, todos los hosts desconocidos se agregan automáticamente aquí y los datos del informe desde allí se incluyen en la vista de informe predeterminada. Al crear un entorno “limpio”, se asegura de que se incluyan solo los sitios o dominios principales.

Para establecer el entorno predeterminado en la creación de informes:

1. En la lista [!UICONTROL Entornos], haga clic en el icono Estrella

>[!NOTE]
>
>Los usuarios de [!DNL Recommendations] deben volver a generar la base de datos de comportamiento y la base de datos de producto si los hosts se cambian de grupo de hosts.

## Cambiar el nombre de un entorno {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. En la lista [!UICONTROL Entorno], haga clic en el icono **[!UICONTROL Editar]**.
1. Cambie el nombre del entorno.
1. Haga clic en **[!UICONTROL Guardar]**.

## Eliminar un entorno {#section_737F8869612047868D03FC755B1223D3}

Puede eliminar un entorno que ya no vaya a necesitar.

1. En la lista [!UICONTROL Entorno], haga clic en el icono **[!UICONTROL Eliminar]**.
1. Haga clic en **[!UICONTROL Eliminar]** para confirmar la acción.

>[!NOTE]
>
>No puede eliminar el entorno [!UICONTROL Producción], pero puede cambiarle el nombre.

## Recommendations: filtrar colecciones y exclusiones por entorno (grupo de hosts)

![Distintivo Premium](/help/assets/premium.png)

Puede obtener una vista previa del contenido de las colecciones y exclusiones de Recommendations para un entorno seleccionado (grupo de hosts).

>[!NOTE]
>
>Las actividades de Recommendations están disponibles como parte de la solución [!DNL Target] Premium. No están disponibles en [!DNL Target] Standard sin una licencia de [!DNL Target] Premium.

Se puede utilizar un entorno para separar los elementos disponibles en el catálogo para distintos usos. Por ejemplo, puede utilizar grupos de hosts para entornos [!UICONTROL de desarrollo] y [!UICONTROL de producción], marcas diferentes o diferentes regiones geográficas. De forma predeterminada, la vista previa de los resultados en Búsqueda de catálogo, Colecciones y Exclusiones se basa en el grupo de hosts predeterminado. (También puede seleccionar otro grupo de hosts para obtener una vista previa de los resultados mediante el filtro Entorno). De forma predeterminada, los elementos recién añadidos están disponibles en todos los grupos de hosts a menos que se especifique un ID de entorno al crear o actualizar el elemento. Las recomendaciones enviadas dependen del grupo de hosts especificado en la solicitud.

Si no ve sus productos, asegúrese de que esté usando el grupo de hosts correcto. Por ejemplo, si configura que la recomendación use un entorno de ensayo y establece el grupo de hosts en Ensayo, puede que tenga que volver a crear las colecciones en el entorno de ensayo para que se puedan mostrar los productos. Para ver qué productos están disponibles en cada entorno, use Búsqueda en catálogo con cada entorno. También puede obtener una vista previa del contenido de las colecciones y exclusiones de Recommendations para un entorno seleccionado (grupo de hosts).

>[!NOTE]
>Después de cambiar el entorno seleccionado, debe hacer clic en Buscar para actualizar los resultados devueltos.

El filtro [!UICONTROL Entorno] está disponible en los siguientes lugares de la interfaz de usuario de Destinatario:

* Búsqueda en el catálogo ([!UICONTROL Recommendations > Buscar en el catálogo])
* Cuadro de diálogo Crear colección ([!UICONTROL Recommendations > Colecciones > Crear nuevo])
* Cuadro de diálogo Actualizar colección ([!UICONTROL Recommendations > Colecciones > Editar])
* Cuadro de diálogo Crear exclusión ([!UICONTROL Recommendations > Exclusiones > Crear nuevo])
* Cuadro de diálogo Actualizar exclusión ([!UICONTROL Recommendations > Exclusiones > Editar])