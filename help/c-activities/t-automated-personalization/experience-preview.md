---
keywords: vista previa de experiencias;direcciones URL de experiencia;generar direcciones URL;ver direcciones URL de experiencia
description: Se puede generar una dirección URL de experiencia para cada actividad de personalización automatizada de Target para ver el contenido de la experiencia directamente en el sitio antes de que la actividad se publique. De este modo, se puede obtener una vista previa y realizar un control de calidad. Las direcciones URL de experiencias evitan la segmentación para forzar la visualización de una experiencia determinada.
title: Compartir URL de experiencia para previsualizar la personalización automatizada fuera de Target
topic: Standard
uuid: 2ef07b6c-086d-43ac-bf02-efe217652a3a
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# ![PREMIUM](/help/assets/premium.png) Compartir direcciones URL de experiencia para previsualizar la Personalización automatizada fuera de Target{#share-experience-urls-to-preview-automated-personalization-outside-of-target}

Se puede generar una dirección URL de experiencia para cada actividad de personalización automatizada de Target para ver el contenido de la experiencia directamente en el sitio antes de que la actividad se publique. De este modo, se puede obtener una vista previa y realizar un control de calidad. Las direcciones URL de experiencias evitan la segmentación para forzar la visualización de una experiencia determinada.

>[!NOTE]
>
>El modo de control de calidad de la actividad le permite crear direcciones URL de actividad para otro tipo de actividades. Para obtener más información, consulte [Control de calidad de las actividades](../../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40)

.

Para usar direcciones URL de experiencia, tiene que compartir los vínculos que se generan desde Target, no la dirección URL final en la que aterriza al ver la experiencia. Además, si cambia el contenido, hay que generar direcciones URL nuevas. Es posible que, al generar direcciones URL nuevas, las antiguas no funcionen.

Utilice las direcciones URL de experiencia para compartir experiencias con integrantes del equipo y para controlar la calidad de las experiencias en distintos navegadores y entornos sin necesidad de crear una actividad de control de calidad específica. Esta característica resulta especialmente útil en sitios complejos o si las políticas de seguridad no permiten que el sitio se vea en un simulador.

1. Cree una [actividad de Personalización automatizada](../../c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9) o haga clic en la actividad para abrirla.

   No es necesario que la actividad esté activa para poder consultar la vista previa de una experiencia.
1. En la página de resumen de la actividad, haga clic en los tres puntos verticales y después haga clic en **[!UICONTROL Ver direcciones URL de experiencia]**.
1. Revise y/o especifique sus URL.

   * Si está utilizando el Compositor de experiencias visuales (VEC), la URL predeterminada que especificó para la actividad se introduce automáticamente y se genera un vínculo para cada experiencia de la actividad. Puede cambiar esta URL y añadir otras si lo desea.
   * Si usa el Compositor de experiencias basadas en formularios, no aparece ninguna URL predeterminada automáticamente. Si no ha creado previamente una URL de experiencia, haga clic en **Añadir nueva URL**. Debe especificar todas las URL que desea visualizar previamente, así como un nombre para cada una.
   Puede añadir varias direcciones URL, lo cual es útil cuando ejecuta una prueba de varias páginas o una prueba de plantilla y quiere previsualizar la actividad en más de una página.

   En una ventana modal se muestran vínculos a sus experiencias en su sitio para obtener una “auténtica vista previa” de las experiencias fuera del Compositor de experiencias visuales de Target. Debe compartir los vínculos del mensaje para compartir la vista previa. Hacer clic en un vínculo y luego copiar la dirección URL resultante desde la página no funcionará porque la dirección URL contiene un parámetro que solo muestra la página correctamente cuando entra a la página desde el vínculo en el mensaje. Copie el texto de la ventana modal y envíelo por correo electrónico en su totalidad a su equipo.
1. Haga clic en **[!UICONTROL Generar todos]** y luego haga clic en cada una de las experiencias para visualizarlas previamente.

   Si después modifica la experiencia, asegúrese de generar nuevos vínculos de vista previa para su equipo. Para ello, vuelva a la ventana modal y haga clic en **Generar todos** para obtener nuevos vínculos.

   **Nota:** Los vínculos de la vista previa se abren en pestañas nuevas y es necesario que el bloqueador de ventanas emergentes del navegador esté desactivado.

1. Haga clic en cada nombre de experiencia para visualizar previamente la actividad.

   Se abrirá la página de la actividad.
1. Haga clic en **[!UICONTROL Hecho]** para regresar al resumen de la actividad.

## Consideraciones {#example_9F2B333BC63143FF99AE331F57E8BA4C}

**Generar direcciones URL de experiencia**

* La dirección URL de experiencia no se ve afectada por la división del tráfico entre las experiencias.
* La segmentación en el nivel de audiencia no afecta a la vista previa.
* Puede generar automáticamente un máximo de 300 direcciones URL de experiencia por actividad. A partir de esa cantidad, debe generar las direcciones URL de forma manual.
* Puede generar automáticamente un máximo de 300 direcciones URL de experiencia por actividad. A partir de esa cantidad, debe generar las direcciones URL de forma manual.
* En función del número de experiencias, la generación de las direcciones URL puede tardar hasta cinco minutos. No cierre el cuadro de diálogo o, de lo contrario, las direcciones URL se perderán.
* Los vínculos de vista previa generados son válidos durante dos meses. Pasado ese tiempo, debe volver a generar las direcciones URL de vista previa.
* Tiene que volver a generarlas siempre que se modifique una experiencia.

**Compartir direcciones URL de experiencia**

* Puede obtener la vista previa de una experiencia aunque no forme parte de la audiencia de destino.
* Puede compartir las URL de experiencia con compañeros que no tienen acceso a Adobe Target.

**Ver experiencias con las direcciones URL de experiencia**

* La vista previa funciona para todas las actividades guardadas siempre que la página no haya cambiado.
* La dirección URL de experiencia está disponible tanto si la actividad está activa como si está inactiva.
* No se pueden previsualizar las experiencias con el estado de borrador
* Los informes no se ven afectados por la vista previa de las URL de experiencia.

**Resolución de problemas de las direcciones URL de experiencia**

* Si no ve la vista previa en la pestaña nueva (debido a la memoria caché del navegador), pruebe a actualizar dos o tres veces, o copie el vínculo y ábralo en un navegador nuevo, en una nueva sesión o en el modo de navegación privada.
* Independientemente de si efectúa su propio control de calidad para una actividad o si reenvía vínculos a otro equipo, puede previsualizar fácilmente experiencias específicas sin la necesidad de crear distintas pruebas.

