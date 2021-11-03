---
keywords: Recomendaciones
description: Conozca los requisitos de implementación de Analytics para [!DNL Target] (A4T) y qué considerar antes de implementar esta integración.
title: ¿Qué Debo Saber Antes De Implementar A4T?
feature: Analytics for Target (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: 9a1603cbbe773638693f5836b6cf7c62dc0b56b8
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 31%

---

# Antes de implementar Analytics for Target (A4T) con at.js

Se producen varios cambios en el proceso de recopilación de datos al habilitar [!DNL Adobe Analytics] como fuente de informes para [!DNL Adobe Target] (A4T).

Antes de decidir si usará esta integración, lea el contenido de estas secciones y tenga en cuenta el impacto en sus procesos de creación de informes.

>[!NOTE]
>
>Este artículo se aplica solo a implementaciones de at.js .

## Requisitos de implementación {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>Antes de empezar a usar A4T, debe solicitar que su cuenta esté aprovisionada para la integración. Utilice la variable [Formulario de aprovisionamiento de integraciones de Marketing Cloud](https://www.adobe.com/go/audiences) para solicitar el aprovisionamiento.

Esta integración con A4T requiere que implemente las siguientes versiones de las bibliotecas (o versiones más recientes), en función de si quiere redireccionar ofertas con A4T o no.

>[!NOTE]
>
>Los requisitos siguientes enumeran la variable *mínimo* versiones de at.js necesarias para implementar A4T. La variable [!DNL Target] el equipo de mantiene solo dos versiones de [!DNL at.js]: la versión actual y la segunda versión más reciente. Actualice [!DNL at.js] cuando sea posible para garantizar que dispone de una versión compatible. Para obtener información detallada sobre los cambios en cada versión de at.js, consulte [Detalles de las versiones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A).

### Requisitos necesarios si *no* se utilizan ofertas de redireccionamiento con A4T

Esta integración requiere que implemente las siguientes versiones de la biblioteca (o versiones más recientes) si no planea utilizar ofertas de redireccionamiento con A4T. El orden de la lista es el orden de las operaciones.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js versión 1.8.0
* [!DNL Adobe Target]: Versión 0.9.1 de at.js
* Adobe Analytics: appMeasurement.js versión 1.7.0

### Requisitos necesarios si se utilizan ofertas de redireccionamiento con A4T

Para utilizar ofertas de redireccionamiento con A4T, debe implementar las siguientes versiones de la biblioteca (o más recientes). El orden de la lista es el orden de las operaciones.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js versión 2.3.0

   >[!NOTE]
   >
   >Las versiones de at.js 1.8.0 y posteriores, así como at.js 2.x y posteriores, ya no funcionan con versiones de la API de visitante anteriores a la 2.5.0 para pasar parámetros de Adobe Audience Manager (AAM).

* [!DNL Adobe Target]: Versión 1.6.2 de at.js

* Adobe Analytics: appMeasurement.js versión 2.1

Las instrucciones de descarga e implementación se enumeran en [Implementación de Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).

## Cosas que hay que saber antes de implementar {#section_50D49CC52E11414089C89FB67F9B88F5}

* Esta integración está habilitada en las nuevas actividades cuando selecciona utilizar [!DNL Analytics] como fuente de informes. Después de completar los cambios de implementación descritos en este documento, las actividades existentes no se verán afectadas.
* El proceso de configuración [!DNL Analytics] como fuente de informes para [!DNL Target] incluye varios pasos de implementación, seguidos de un paso de aprovisionamiento. Le recomendamos que lea todo el proceso que se describe a continuación antes de comenzar la implementación. Una vez completados estos pasos, está listo para usar [!DNL Analytics] como fuente de informes cuando esté habilitada para usted. El proceso de aprovisionamiento puede tardar hasta cinco días hábiles.
* La variable [!DNL Visitor ID service] crea un [!DNL Visitor ID] en el [!DNL Adobe Experience Cloud]. Aunque no reemplaza la variable [!DNL Target] mboxPC id o [!DNL Audience Manager] UUID, sustituye la forma en que [!DNL Analytics] identifica a los visitantes nuevos. Si se configura correctamente, se devuelve [!DNL Analytics] Los visitantes también deben identificarse a través de su [!DNL Analytics] ID. Del mismo modo, porque la variable [!DNL Target] mboxPCid permanece intacto, no [!DNL Target] los datos de perfil del visitante se pierden al actualizar a la variable [!DNL Visitor ID service].
* La variable [!DNL Visitor ID service] debe ejecutarse antes de que [!DNL Analytics] y [!DNL Target] código de página. Asegúrese de que `VisitorAPI.js` aparece encima de las etiquetas del resto [!DNL Experience Cloud] soluciones.

## Latencia {#section_9489BE6FD21641A4844E591711E3F813}

Una vez habilitada esta integración, experimentará otros 5-10 minutos de latencia en [!DNL Analytics]. Este aumento de la latencia permite obtener datos de [!DNL Analytics] y [!DNL Target] se almacenarán en la misma visita, lo que le permite desglosar las actividades por página y por sección de sitio.

Este aumento se refleja en todas las [!DNL Analytics] servicios y herramientas, incluidos el flujo en directo y los informes en tiempo real, y se aplica en los siguientes escenarios:

* Para el flujo en directo, los informes en tiempo real, las solicitudes de la API y todos los datos actuales para las variables de tráfico, solo se retrasan las visitas con un ID de datos suplementario.
* Para los datos actuales de las métricas de conversión, los datos finalizados y las fuentes de datos, todas las visitas se retrasan de 5 a 7 minutos más.

El aumento de la latencia comienza después de implementar la variable [!DNL Experience Cloud] servicio de ID de visitante, aunque no haya implementado correctamente esta integración.

## ID suplementario.  {#section_2C1F745A2B7D41FE9E30915539226E3A}

Todo [!DNL Target] las llamadas que utilice una actividad de A4T para ofrecer contenido o registrar la métrica de objetivos deben tener una [!DNL Analytics] visita que comparte el ID suplementario para A4T para que funcione correctamente.

Visitas que contienen datos de [!DNL Analytics] y [!DNL Target] contiene un ID de datos suplementario. Puede ver este ID en la sección [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) como el `sdid` parámetro. Por ejemplo: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`. Este ID se genera cada vez que se cumplen los siguientes criterios:

* Se ha implementado el servicio de ID de visitante.

When [solución de problemas](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md), asegúrese de que el ID suplementario esté presente en [!DNL Analytics] visitas individuales.

## Registro de Analytics en el lado del cliente {#client-side}

Si at.js, la variable [!DNL Experience Cloud Visitor ID Service]y appMeasurement.js están en la página, [!DNL Analytics]y [!DNL Target] vincula correctamente eventos para fines de informes y análisis en el backend, siempre y cuando se incluya el ID suplementario correcto desde la página. No es necesario administrar y realizar operaciones adicionales para A4T para funcionar correctamente.

Hay casos en los que es posible que desee tener más control sobre cuándo y cómo enviar datos de análisis relacionados con [!DNL Target] a [!DNL Analytics] a efectos de la elaboración de informes. Es posible que tenga una herramienta de análisis interna que utilice con fines internos. Sin embargo, también desea enviar los datos de análisis a [!DNL Analytics] a través del producto de análisis interno para que otros miembros de su organización puedan seguir usando [!DNL Analytics] como fuente visual de informes. Consulte [Paso 7: Haga referencia a at.js en todas las páginas del sitio](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) en *Implementación de Analytics for Target* para obtener más información.

## Audiencias compartidas

Al rellenar el [Formulario de aprovisionamiento de integraciones de Marketing Cloud](https://www.adobe.com/go/audiences), tenga en cuenta la siguiente información importante sobre la [!UICONTROL Audiencias compartidas] opción que aparece en &quot;[!UICONTROL Para qué capacidades solicita el aprovisionamiento]?&quot;

![Formulario de solicitud](/help/c-integrating-target-with-mac/a4t/assets/request-form.png)

Cuando se solicita [!UICONTROL Audiencias compartidas], habilite [!UICONTROL Target] y [!UICONTROL Adobe Audience Manager] (AAM) para compartir información, en este caso audiencias.

>[!IMPORTANT]
>
>Esta integración entre [!UICONTROL Target] y AAM incluye costos adicionales. Se le cobrará por cada [!UICONTROL Target] en AAM.
