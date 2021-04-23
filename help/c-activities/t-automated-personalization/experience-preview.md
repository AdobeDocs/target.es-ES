---
keywords: vista previa de experiencias;direcciones URL de experiencia;generar direcciones URL;ver direcciones URL de experiencia
description: Aprenda a utilizar las direcciones URL de vista previa de la experiencia para actividades de Adobe [!DNL Target] Automated Personalization para ver el contenido de la experiencia directamente en el sitio antes de que la actividad esté activa.
title: ¿Cómo puedo utilizar las direcciones URL de vista previa de experiencia en actividades de Automated Personalization?
feature: Personalización automatizada
exl-id: 9f329b8a-5f86-4cae-a3be-eed24fa0a9cd
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 65%

---

# ![](/help/assets/premium.png) PREMIUMPver las actividades de Automated Personalization con direcciones URL de vista previa de la experiencia

Se pueden generar direcciones URL de vista previa de experiencias para actividades de Automated Personalization de Target para ver el contenido de la experiencia directamente en el sitio antes de que la actividad esté activa para obtener una vista previa y un control de calidad. Las direcciones URL de vista previa de experiencias evitan la segmentación para forzar la visualización de una experiencia en particular.

>[!NOTE]
>
>Las direcciones URL de vista previa de experiencias para Automated Personalization difieren del modo de control de calidad de la actividad. El modo de control de calidad de la actividad le permite crear direcciones URL de actividad para otro tipo de actividades. Para obtener más información, consulte [Control de calidad de las actividades](/help/c-activities/c-activity-qa/activity-qa.md).
>
>Las direcciones URL de vista previa de experiencias para actividades AP solo están disponibles cuando se utiliza at.js 1.x. Actualmente, las direcciones URL de vista previa de experiencias para actividades AP no son compatibles con at.js 2.x.

Utilice las direcciones URL de vista previa de la experiencia para compartir experiencias con integrantes del equipo y para controlar la calidad de las experiencias en distintos navegadores y entornos, sin necesidad de crear una actividad de control de calidad independiente. Esta característica resulta especialmente útil en sitios complejos o si las políticas de seguridad no permiten que el sitio se vea en un simulador.

1. Cree una [actividad de Personalización automatizada](/help/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9) o haga clic en la actividad para abrirla.

   No es necesario que la actividad esté activa para poder consultar la vista previa de una experiencia.
1. En la página de resumen de la actividad, haga clic en los tres puntos verticales y después haga clic en **[!UICONTROL Ver direcciones URL de experiencia]**.
1. Revise y/o especifique sus URL.

   * Si está utilizando el Compositor de experiencias visuales (VEC), la URL predeterminada que especificó para la actividad se introduce automáticamente y se genera un vínculo para cada experiencia de la actividad. Puede cambiar esta URL y añadir otras si lo desea.
   * Si usa el Compositor de experiencias basadas en formularios, no aparece ninguna URL predeterminada automáticamente. Si no ha creado previamente direcciones URL de vista previa de la experiencia, haga clic en **Agregar nueva dirección URL**. Debe especificar todas las URL que desea visualizar previamente, así como un nombre para cada una.

   Puede añadir varias direcciones URL, lo cual es útil cuando ejecuta una prueba de varias páginas o una prueba de plantilla y quiere previsualizar la actividad en más de una página.

   En una ventana modal se muestran vínculos a sus experiencias en su sitio para obtener una “auténtica vista previa” de las experiencias fuera del Compositor de experiencias visuales de Target. Debe compartir los vínculos del mensaje para compartir la vista previa. Hacer clic en un vínculo y luego copiar la dirección URL resultante desde la página no funcionará porque la dirección URL contiene un parámetro que solo muestra la página correctamente cuando entra a la página desde el vínculo en el mensaje. Copie el texto de la ventana modal y envíelo por correo electrónico en su totalidad a su equipo.
1. Haga clic en **[!UICONTROL Generar todos]** y luego haga clic en cada una de las experiencias para visualizarlas previamente.

   Si a continuación realiza cambios en la experiencia, asegúrese de generar nuevos vínculos de vista previa para su equipo. Para ello, vuelva a la ventana modal y haga clic en **Renovar vínculos** para obtener nuevos vínculos.

   **Nota:** Los vínculos de la vista previa se abren en pestañas nuevas y es necesario que el bloqueador de ventanas emergentes del navegador esté desactivado.

1. Haga clic en cada nombre de experiencia para visualizar previamente la actividad.

   Se abrirá la página de la actividad.
1. Haga clic en **[!UICONTROL Hecho]** para regresar al resumen de la actividad.

## Consideraciones {#example_9F2B333BC63143FF99AE331F57E8BA4C}

**Generación de direcciones URL de vista previa de experiencias**

* La dirección URL de vista previa de la experiencia no se ve afectada por la división del tráfico entre las experiencias.
* La segmentación en el nivel de audiencia no afecta a la vista previa.
* Puede generar automáticamente un máximo de 300 direcciones URL de experiencia por actividad. A partir de esa cantidad, debe generar las direcciones URL de forma manual.
* Puede generar automáticamente un máximo de 300 direcciones URL de experiencia por actividad. A partir de esa cantidad, debe generar las direcciones URL de forma manual.
* En función del número de experiencias, la generación de las direcciones URL puede tardar hasta cinco minutos. No cierre el cuadro de diálogo o, de lo contrario, las direcciones URL se perderán.
* Los vínculos de vista previa generados son válidos durante dos meses. Pasado ese tiempo, debe volver a generar las direcciones URL de vista previa.
* Tiene que volver a generarlas siempre que se modifique una experiencia.

**Compartir URL de vista previa de experiencias**

* Puede obtener la vista previa de una experiencia aunque no forme parte de la audiencia de destino.
* Puede compartir las direcciones URL de vista previa de la experiencia con compañeros que no tengan acceso a Adobe Target.

**Visualización de experiencias con direcciones URL de vista previa de experiencias**

* La vista previa funciona para todas las actividades guardadas siempre que la página no haya cambiado.
* La dirección URL de vista previa de la experiencia está disponible tanto si la actividad está activa como si está inactiva.
* No puede obtener una vista previa de una experiencia que esté en estado de borrador.
* Los informes no se ven afectados por la visualización de las direcciones URL de vista previa de la experiencia.

**Resolución de problemas de las direcciones URL de vista previa de la experiencia**

* Si no ve la vista previa en la pestaña nueva (debido a la memoria caché del navegador), pruebe a actualizar dos o tres veces, o copie el vínculo y ábralo en un navegador nuevo, en una nueva sesión o en el modo de navegación privada.
