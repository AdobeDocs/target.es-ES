---
keywords: parpadeo, ocultar previamente, preocultación, personalización, implementación, antiparpadeo, VEC, compositor de experiencias visuales
description: Descubra cómo la preocultación de contenido reduce el parpadeo al ocultar solo las regiones que cambiará la personalización activa de Adobe Target, mediante una configuración de nivel de cuenta, una biblioteca de páginas ligera y controles por actividad.
title: Ocultamiento previo del contenido para experiencias personalizadas
feature: Administration & Configuration
role: Admin
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#beta newtab=true" tooltip="¿Qué son las funciones beta en  [!DNL Adobe Target]?"
hide: true
source-git-commit: 77741253fdfb007d0eda0c57fe293df2f9c638a2
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 3%

---

# Ocultamiento previo del contenido para experiencias personalizadas

>[!AVAILABILITY]
>
>La ocultación previa de contenido para contenido personalizado está disponible como capacidad **beta**.

Cuando un visitante carga una página, el contenido predeterminado puede aparecer brevemente y luego reemplazarse por contenido personalizado de [!DNL Adobe Target]. Ese interruptor visible se llama a menudo **parpadeo** y es un problema común de experiencia para los programas de personalización.

Con la preocultación de contenido puede administrar el parpadeo ocultando solo las partes de la página que personalizan sus actividades durante la carga de la página, de modo que los clientes vean menos parpadeo y menos tiempo de pantalla vacío.

Así es como funciona la preocultación de contenido, desde la cuenta predeterminada hasta la implementación de su página y las opciones por actividad.

1. Habilite la ocultación previa de contenido para su cuenta a fin de establecer el valor predeterminado global. Está desactivado de forma predeterminada. [Más información](#content-pre-hiding-enable-account)

1. Agregue la biblioteca de ocultamiento previo del contenido a `<head>` de todas las páginas donde ejecute actividades de personalización.

1. [!DNL Target] crea un conjunto de reglas a partir de las actividades activas [!UICONTROL Visual Experience Composer] y [!UICONTROL Enhanced Experience Composer]. El conjunto de reglas enumera selectores y regiones que la entrega puede cambiar.

   Tenga en cuenta que no se admiten [!UICONTROL Form-Based Composer] actividades.

1. La biblioteca recupera ese conjunto de reglas de la CDN de Adobe y oculta previamente los elementos coincidentes solo mientras el contenido personalizado aún se está cargando.

1. En **[!UICONTROL Goals & Settings]**, puede deshabilitar **[!UICONTROL Content pre-hiding]** para actividades individuales, pero solo si está habilitado en el nivel de cuenta. [Más información](#content-pre-hiding-activity)

## Habilite la ocultación previa de contenido para su instancia {#content-pre-hiding-enable-account}

>[!IMPORTANT]
>
>Para habilitar la ocultación previa de contenido para la instancia, debe ser **administrador**.

La preocultación de contenido está desactivada en la instancia hasta que se activa. Use **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** para activar la característica, establecer los valores predeterminados y acceder a la descarga para su equipo de implementación.

1. En [!DNL Target], haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

1. En el menú **[!UICONTROL Content pre-hiding]**, habilite la opción Preocultación de contenido.

   ![](assets/content-pre-hiding-1.png)

1. Si es necesario, actualice **[!UICONTROL Pre-hiding timeout]** en segundos.

1. Haga clic en **[!UICONTROL Save]**. Esto aplicará la configuración de administración de parpadeo a la instancia.

1. Una vez habilitado, haga clic en **[!UICONTROL Download]** y luego agregue el archivo a la página `<head>` para que se cargue antes de [!DNL at.js] o de [!DNL Web SDK]. Para obtener instrucciones de implementación completas, consulte [Contenido preocultado de SDK](https://experienceleague.adobe.com/es/docs/target-dev/developer/client-side/prehide-sdk).

   ![](assets/content-pre-hiding-2.png)

La instancia ahora utiliza la configuración de tiempo de espera y ocultamiento previo del contenido guardado como predeterminada para las actividades de inclusión.

## Habilite la ocultación previa de contenido para su actividad {#content-pre-hiding-activity}

Con la preocultación habilitada para su instancia, elija si cada actividad la usa en **[!UICONTROL Goals & Settings]**. Las actividades para las que habilita la preocultación se incluyen en el comportamiento de destino cuando están activas.

A continuación, [!DNL Target] crea un conjunto de reglas ligeras a partir de actividades activas creadas en [!UICONTROL Visual Experience Composer] (VEC) y [!UICONTROL Form-Based Composer], y describe los selectores y las áreas que puede cambiar la entrega.

Cuando crea o edita una actividad:

1. Acceda a la actividad para la que desea activar la opción de ocultamiento previo.

1. Acceda a la lista desplegable **[!UICONTROL Edit activity]** y seleccione **[!UICONTROL Edit Goals & Settings]**.

   ![](assets/content-pre-hiding-3.png)

1. En el menú **[!UICONTROL Content pre-hiding]**, active la opción **[!UICONTROL Enable content pre-hiding]** para activar o desactivar esta actividad de la preocultación.

   ![](assets/content-pre-hiding-4.png)

1. Una vez finalizado, haga clic en **[!UICONTROL Save & Close]**.

Después de guardar y como las actividades se activan o desactivan, el conjunto de reglas se actualiza para que la ocultación previa permanezca alineada con lo que realmente se entrega, sin ediciones en el código de página para cada lanzamiento.

En el lado del visitante, la biblioteca recupera ese conjunto de reglas de la CDN de Adobe en cada carga de página y preoculta los elementos coincidentes solo cuando es necesario hasta que el contenido personalizado está listo.
