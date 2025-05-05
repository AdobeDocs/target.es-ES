---
keywords: vista previa de experiencias;direcciones URL de experiencia;generar direcciones URL;ver direcciones URL de experiencia
description: Aprenda a utilizar las URL de vista previa de experiencias para las actividades de Adobe  [!DNL Target] Automated Personalization para ver el contenido de las experiencias directamente en el sitio antes de que la actividad esté activa.
title: ¿Cómo puedo usar las direcciones URL de vista previa de experiencias en actividades de Automated Personalization?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Automated Personalization
exl-id: 9f329b8a-5f86-4cae-a3be-eed24fa0a9cd
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 49%

---

# Vista previa de actividades de Automated Personalization con URL de vista previa de experiencias

Se pueden generar URL de vista previa de experiencias para actividades [!DNL Target] [!UICONTROL Automated Personalization] a fin de ver el contenido de las experiencias directamente en el sitio antes de que la actividad esté activa para fines de vista previa y control de calidad. Las URL de vista previa de experiencias omiten la segmentación para forzar la visualización de una experiencia concreta.

>[!NOTE]
>
>Puede crear direcciones URL de vista previa de experiencias para otros tipos de actividades [!DNL Target]. Sin embargo, el proceso es ligeramente diferente. Para obtener más información, consulte [Control de calidad de las actividades.](/help/main/c-activities/c-activity-qa/activity-qa.md#preview)

Utilice las URL de vista previa de experiencias para compartir experiencias con los integrantes del equipo y realizar controles de calidad de experiencias en exploradores y entornos, sin crear una actividad de control de calidad independiente. Esta característica resulta especialmente útil en sitios complejos o si las políticas de seguridad no permiten que el sitio se vea en un simulador.

1. Cree una [actividad de Personalización automatizada](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9) o haga clic en la actividad para abrirla.

   No es necesario que la actividad esté activa para poder consultar la vista previa de una experiencia.

1. En la página Información general de la actividad, haga clic en los tres puntos verticales y luego haga clic en **[!UICONTROL View Experience URLs]**.

1. Revise y/o especifique sus URL.

   * Si usa el [!UICONTROL Visual Experience Composer] (VEC), la dirección URL predeterminada que especificó para la actividad se especifica automáticamente y se genera un vínculo para cada experiencia de la actividad. Puede cambiar esta URL y añadir otras si lo desea.
   * Si usa [!UICONTROL Form-Based Experience Composer], no se escribe automáticamente ninguna dirección URL predeterminada. Si aún no has creado las URL de vista previa de la experiencia, haz clic en **Agregar nueva URL**. Debe especificar todas las URL que desea visualizar previamente, así como un nombre para cada una.

   Puede añadir varias direcciones URL, lo cual es útil cuando ejecuta una prueba de varias páginas o una prueba de plantilla y quiere previsualizar la actividad en más de una página.

   Una ventana modal muestra vínculos a sus experiencias en su sitio para obtener una &quot;auténtica vista previa&quot; de las experiencias fuera del VEC [!DNL Target]. Debe compartir los vínculos del mensaje para compartir la vista previa. Hacer clic en un vínculo y luego copiar la dirección URL resultante desde la página no funcionará porque la dirección URL contiene un parámetro que solo muestra la página correctamente cuando entra a la página desde el vínculo en el mensaje. Copie el texto de la ventana modal y envíelo por correo electrónico en su totalidad a su equipo.

1. Haga clic en **[!UICONTROL Generate All]** y luego haga clic en cada experiencia para previsualizarla.

   Si después realiza cambios en la experiencia, asegúrese de generar nuevos vínculos de vista previa para su equipo. Para ello, vuelva a la ventana modal y haga clic en **Renovar vínculos** para obtener nuevos vínculos.

   >[!NOTE]
   >
   >Los vínculos de vista previa se abren en pestañas nuevas y requieren que el bloqueador de ventanas emergentes del explorador esté deshabilitado.

1. Haga clic en cada nombre de experiencia para visualizar previamente la actividad.

   Se abrirá la página de la actividad.

1. Haga clic **[!UICONTROL Done]** para regresar al resumen de la actividad.

## Consideraciones {#example_9F2B333BC63143FF99AE331F57E8BA4C}

**Generando URL de vista previa de experiencia**

* La URL de vista previa de la experiencia no se ve afectada por la división de tráfico entre experiencias.
* La segmentación en el nivel de audiencia no afecta a la vista previa.
* Puede generar automáticamente un máximo de 300 direcciones URL de experiencia por actividad. A partir de esa cantidad, debe generar las direcciones URL de forma manual.
* En función del número de experiencias, la generación de las direcciones URL puede tardar hasta cinco minutos. No cierre el cuadro de diálogo o se perderán las direcciones URL generadas.
* Los vínculos de vista previa generados son válidos durante dos meses. Pasado ese tiempo, debe volver a generar las direcciones URL de vista previa.
* Tiene que volver a generarlas siempre que se modifique una experiencia.

**URL de vista previa de experiencias compartidas**

* Puede obtener la vista previa de una experiencia aunque no forme parte de la audiencia de destino.
* Puede compartir direcciones URL de vista previa de experiencias con compañeros que no tienen acceso a [!DNL Adobe Target].

**Visualización de experiencias con URL de vista previa de experiencias**

* La vista previa funciona para todas las actividades guardadas siempre que la página no haya cambiado.
* La URL de vista previa de la experiencia está disponible tanto si la actividad está activa como si está inactiva.
* No puede obtener una vista previa de una experiencia que se encuentra en [!UICONTROL Draft] estado.
* Los informes no se ven afectados por la visualización de URL de vista previa de experiencias.

**Solución de problemas de URL de vista previa de experiencia**

* Si no ve la vista previa en la pestaña nueva (debido a la memoria caché del navegador), pruebe a actualizar dos o tres veces, o copie el vínculo y ábralo en un navegador nuevo, en una nueva sesión o en el modo de navegación privada.
