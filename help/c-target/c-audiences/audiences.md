---
keywords: audiencia;reglas de audiencia;crear audiencia;creación de audiencia;segmentación de audiencia;informe de audiencia;audiencia de informe;segmento;parámetros de perfil personalizados;definición de audiencia;lista de audiencias
description: Las audiencias en Adobe Target determinan quién ve el contenido y las experiencias en una actividad segmentada.
title: Crear Audiencias
feature: Audiences
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 95%

---


# Crear audiencias{#create-audiences}

Las audiencias en Adobe Target determinan quién ve el contenido y las experiencias en una actividad segmentada.

Las audiencias se utilizan siempre que está disponible la determinación de objetivos. Al segmentar una actividad, puede seleccionar una audiencia reutilizable de la lista [!UICONTROL Audiencias], [crear una audiencia específica de actividad](/help/c-target/creating-activity-only-audience.md) y segmentarla, o [combinar varias audiencias](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) para crear una audiencia ad-hoc.

También puede usar datos de la audiencia recopilados por [!DNL Analytics] para personalización y segmentación en tiempo real en [!DNL Adobe Target] y otras soluciones de [!DNL Experience Cloud]. Consulte [Audiencias](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html) en la *Guía del usuario de servicios principales*.

[!DNL Target] distingue dos tipos de audiencias:

* **Audiencias de segmentación:** se usan para entregar distintos contenidos a varios tipos de visitantes.
* **Audiencias de informes:** se usan para determinar cuántos tipos distintos de visitantes responden al mismo contenido y, así, analizar los resultados de las pruebas.

   En [!DNL Target], las audiencias de informes solo se pueden configurar si se usa [!DNL Target] como fuente de informes. Si utiliza [ Adobe Analytics como fuente de informes](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T), tiene que configurar la audiencia de informe en [!DNL Analytics].

## Utilizar la lista Audiencias

Para acceder a la lista [!UICONTROL Audiencias], haga clic en **[!UICONTROL Audiencias]** en la barra de menús superior:

![Lista de audiencias](assets/audiences_list.png)

La lista [!UICONTROL Audiencias] contiene todas las audiencias que se pueden usar en las actividades. Utilice la lista [!UICONTROL Audiencias] para crear, editar, eliminar, copiar o combinar audiencias. La lista también muestra la fuente donde se creó la audiencia ([!DNL Target], [!DNL Target Classic], [!DNL Adobe Audience Manager (AAM),], [!DNL Experience Cloud], etc.). No se puede cambiar el nombre a las audiencias predefinidas como “Nuevos visitantes” o “Visitantes que regresan”.

Al trabajar con audiencias que se crearon originalmente en AAM, Target le alerta si hace referencia a una audiencia en actividades de Target que luego se eliminaron en AAM.

* Si se eliminó una audiencia en AAM, se muestra un icono de advertencia tanto en la lista de [!UICONTROL Audiencias] como en el selector de audiencias. Una información sobre herramientas en la IU también indica que la audiencia se eliminó en AAM.
* Si intenta combinar varias audiencias con una audiencia eliminada, o si intenta guardar una actividad que hace referencia a una audiencia eliminada, aparecerá un mensaje de advertencia.

También puede segmentar parámetros de perfil personalizados y parámetros de `user.`. Al agregar una audiencia, haga clic en **[!UICONTROL Añadir regla]** > **[!UICONTROL Perfil de Visitante]** y, a continuación, elija el parámetro que desee utilizar para destinatario de la actividad. Si el parámetro que desea utilizar no está en la lista, significa que ningún mbox lo ha activado. Encontrará otros parámetros personalizados disponibles de mbox en la lista desplegable [!UICONTROL Parámetros personalizados].

Use el cuadro de búsqueda para buscar la lista [!UICONTROL Audiencias]. Puede buscar cualquier parte del nombre de una audiencia, o bien encerrar entre comillas una cadena específica.

Puede ordenar la lista [!UICONTROL Audiencias] por nombre o por la fecha de la última modificación. Para ordenar por nombre o fecha, haga clic en el encabezado de columna y, a continuación, seleccione si quiere mostrar las audiencias en orden ascendente o descendente.

## Ver definiciones de audiencia {#section_11B9C4A777E14D36BA1E925021945780}

En varios puntos de la interfaz de Target puede ver detalles de la definición de una audiencia en forma de tarjeta emergente, sin necesidad de abrir la audiencia. Esta funcionalidad se aplica a las audiencias creadas en Target Standard/Premium y a las importadas desde Target Classic o creadas mediante API.

Por ejemplo, a la siguiente definición se accede pasando el puntero sobre una audiencia en la Lista de audiencias y haciendo clic en el icono Ver:

![Actividades > Definición de audiencia](assets/audience_definition_list.png)

A la siguiente definición de audiencia se accede haciendo clic en el icono Ver de la página Información general de una actividad:

![Actividades > Definición de audiencia](assets/audience_definition_list.png)

Haga clic en la pestaña [!UICONTROL Uso de la audiencia] para ver otras actividades que hacen referencia a esa audiencia, si es aplicable. De esta forma, puede evitar el impacto accidental en otras actividades mientras edita audiencias. La información incluye actividades en vivo, actividades inactivas, actividades archivadas y actividades de sincronización. Esta función está disponible para todas las audiencias (audiencias de biblioteca y  [audiencias solo de actividad](/help/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)).

Si una audiencia se combina con otra audiencia y la audiencia combinada se usa para crear una actividad, la información de uso de ambas audiencias mostrará esa actividad recién creada.

![](assets/audience_definition_list_usage.png)

La siguiente tarjeta de definición de audiencia corresponde a una audiencia importada desde Adobe Experience Cloud. En este caso, se importó desde Adobe Audience Manager (AAM).

![Pestaña Uso en la tarjeta de Definición de audiencia](assets/audience_definition_mc.png)

Estos tipos de audiencia importada cuentan con los siguientes detalles:

| Tipo de audiencia | Detalles |
|--- |--- |
| Audiencia móvil | Nombre de marketing, Proveedor y Modelo.<br>Se muestra el operador `matches | does not match` en lugar de `equals | does not equal`<br>![Audiencia móvil importada](/help/c-target/c-audiences/assets/imported_mobile_audience.png). |
| Audiencia de comportamiento del visitante | **user.categoryAffinity:** `categoryAffinity` con parámetro `FAVORITE`.<br>![Afinidad de categoría importada ](/help/c-target/c-audiences/assets/imported_category_affinity.png)<br>**Supervisión:** el servicio de monitorización es equivalente a verdadero.<br>**Sin servicio de monitoreo:** Servicio de monitoreo es igual a falso.<br>![Supervisión importada](/help/c-target/c-audiences/assets/imported_monitoring.png) |
| Audiencias que utilizan el operador NOT | **Regla única:** Target muestra la audiencia con el formato `[All Visitor AND [NOT [rule]`. La regla única NOT se muestra con AND con la audiencia `AllVisitor`.<br>![Audiencia no importada](/help/c-target/c-audiences/assets/imported_not_audience.png) |

Tenga en cuenta lo siguiente al trabajar con audiencias importadas:

* Target Standard/Premium ya no admite audiencias de segmentación por expresión.
* Target Standard/Premium no admite algunas audiencias obsoletas o dispone de operadores mejorados que facilitan el uso. Debido a esto, aunque una audiencia importada funcione tal y como se indica en su descripción, puede no estar disponible para su creación en la interfaz de Standard/Premium. Por ejemplo, puede ver las audiencias sociales con sus reglas, pero Target Standard/Premium no permite crearlas.

## Vídeo de formación: Uso de audiencias  ![Insignia de tutorial](/help/assets/tutorial.png)

Este vídeo contiene información sobre el uso de las audiencias.

* Explicar el término “audiencia”
* Explicar las dos formas de usar audiencias para la optimización
* Buscar audiencias en la lista de audiencias
* Dirigir una actividad a una audiencia
* Usar audiencias para la creación pasiva de informes en una actividad

>[!VIDEO](https://video.tv.adobe.com/v/17398)
