---
keywords: mvt; prueba multivariable; crear prueba multivariable; creación de prueba multivariable; crear mvt; creación de mvt, procedimiento de mvt; procedimiento de prueba multivariable
description: Aprenda a usar el [!UICONTROL Compositor de experiencias visuales] (VEC) en [!DNL Adobe Target] para crear una [!UICONTROL Prueba multivariable] (MVT).
title: ¿Cómo creo una [!UICONTROL prueba multivariable]?
feature: Multivariate Tests
exl-id: 7712b747-543a-4e19-b689-bea36c44805c
TQID: 'https://experienceleague.adobe.com/gxrnY43A7OWsiW48Rlq1Orp7ZxBswdAPZEAbRQrCDZA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: aad553690f1f399177214c94a2276d038f46d9cb
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 16%
---
# Crear una prueba multivariable {#create-mvt}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a crear una **[!UICONTROL Prueba multivariada]** (MVT) en el **[!UICONTROL Compositor de experiencias visuales]** (VEC). La actividad se crea, se generan y revisan las experiencias, se establece el direccionamiento y se configuran los objetivos y la configuración.

>[!ENDSHADEBOX]

El **[!UICONTROL Compositor de experiencias visuales]** (VEC) en [!DNL Adobe Target] facilita la creación de una **[!UICONTROL prueba multivariable]** y la modificación de partes de la página en [!DNL Target].

El editor de apuntar y hacer clic [!DNL Target] le permite elegir cualquier ubicación y agregar varias ofertas.

La **[!UICONTROL prueba multivariada]** (MVT) toma un informe centrado en una página. Es decir, la prueba se ejecuta en una determinada dirección URL, con las experiencias que diseño para esa página.

Siga los pasos a continuación para crear una **[!UICONTROL prueba multivariable]** (MVT):

1. [Creación de la actividad](#create-activity)
1. [Crear y revisar las experiencias](#build-experiences)
1. [Establecer segmentación](#set-targeting)
1. [Configurar objetivos y opciones](#configure-goals-and-settings)

## Creación de la actividad {#create-activity}

Elija el tipo de actividad y el tipo de entrega, especifique la página que desea probar y asigne un nombre a la actividad.

1. Haga clic en **[!UICONTROL Crear actividad]** > **[!UICONTROL Prueba multivariable]**.

   Para obtener más información sobre los distintos tipos de actividades disponibles en [!DNL Target] y sus diferencias, consulte [Actividades](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Consulte [Tipos de actividades de Target](/help/main/c-activities/target-activities-guide.md) para ayudarle a decidir qué tipo de actividad encaja con sus necesidades.

   ![](../../assets/create-mvt-1.png)

1. Elija el tipo de entrega: **[!UICONTROL Web]**, **[!UICONTROL Móvil]**, **[!UICONTROL Correo electrónico]** o **[!UICONTROL Otro/API]**.

1. (Condicional) Si es cliente de [Target Premium](/help/main/c-intro/intro.md#premium), [elija un espacio de trabajo](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. [Especifique la dirección URL](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md#ab-activity-url) de la página que desea probar. Utilice una dirección URL completa, incluido HTTP o HTTPS del principio.

1. A continuación, haga clic en **[!UICONTROL Crear]**. Se abre **[!UICONTROL Compositor de experiencias visuales]**.

1. Para asignar un nombre a la actividad, haz clic en el icono **[!UICONTROL Editar]** ( ![Editar icono](/help/main/assets/icons/Edit.svg) ), especifica un nombre descriptivo para la actividad y luego haz clic en **[!UICONTROL Guardar]**.

   {{activity-name-rules}}

   ![](../../assets/create-mvt-2.png)

## Crear y revisar las experiencias {#build-experiences}

Añada ofertas a cada ubicación, previsualice las experiencias resultantes y compruebe que el plan de prueba es viable.

1. [Cree las ofertas en cada ubicación](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6).

   Puede añadir los siguientes tipos de oferta:

   * HTML
   * Imagen
   * Texto

1. Haz clic en **[!UICONTROL Vista previa]** para [obtener una vista previa de tus experiencias](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md).

1. Haga clic en el icono **[!UICONTROL Mostrar experiencias]** ( ![icono Mostrar experiencias](/help/main/assets/icons/WebPages.svg) ) para mostrar la lista de todas las experiencias en el cuadro izquierdo y, a continuación, haga clic en una experiencia específica de la lista para ver esa experiencia.

1. [Utilice el estimador de tráfico](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) para probar la viabilidad de su plan de prueba.

### Excluir experiencias (opcional) {#exclude-experiences}

Puede elegir excluir una experiencia que muestre variaciones que entran en conflicto o una experiencia que no esté equilibrada desde el punto de vista estético.

1. Haga clic en el icono **[!UICONTROL Administrar contenido]** ( ![icono Administrar experiencias](/help/main/assets/icons/Experience.svg) ) para mostrar el cuadro de diálogo **[!UICONTROL Administrar experiencias]**.

1. Para excluir una experiencia, haz clic en el icono **[!UICONTROL Más acciones]** ( ![Icono de más acciones](/help/main/assets/icons/MoreSmallList.svg) ) junto a esa experiencia y, a continuación, haz clic en **[!UICONTROL Excluir]**.

1. Para excluir varias experiencias, selecciona las casillas de verificación de las experiencias que desees y luego haz clic en **[!UICONTROL Excluir]**.

## Establecer segmentación {#set-targeting}

Elija los visitantes que entran en la prueba y revise el resumen de la prueba.

1. Haga clic en **[!UICONTROL Siguiente]** para acceder a la página de **[!UICONTROL Segmentación]**.

   El diagrama de flujo le guía durante el procedimiento para asignar una audiencia y su porcentaje de tráfico, seleccionar el método de asignación de tráfico y especificar la asignación de tráfico para cada experiencia en la actividad.

1. (Condicional) Haga clic en el control **[!UICONTROL Todos los visitantes]** para seleccionar otra audiencia para la actividad.

   La audiencia **[!UICONTROL Todos los visitantes]** está establecida como predeterminada. Si selecciona otra audiencia, su nombre se muestra en el control situado más a la izquierda. Por ejemplo, podría limitar las entradas al 50 % de todos los visitantes o al 45 % del público de California.

   +++ Pasos para seleccionar una audiencia diferente

   Se muestra el marco derecho, que le permite añadir o eliminar una audiencia y asignar el porcentaje de visitante para la actividad.

   1. Para cambiar la audiencia, haga clic en el icono **[!UICONTROL Reemplazar]** ( ![Reemplazar icono](/help/main/assets/icons/Retweet.svg) ) en el marco derecho.
   1. En el cuadro de diálogo **[!UICONTROL Agregar audiencia]**, [seleccione la audiencia que desee](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) y luego haga clic en **[!UICONTROL Asignar audiencia]**.

      Para crear una audiencia que combine varias audiencias, haga clic en **[!UICONTROL Combinar audiencias]**. Para obtener más información, consulte [Combinar varias audiencias](/help/main/c-target/combining-multiple-audiences.md).

      Para crear una audiencia nueva que no esté ya en la **[!UICONTROL Biblioteca de audiencias]**, haga clic en **[!UICONTROL Crear audiencia]**. En [flujo de trabajo create-audience](/help/main/c-target/c-audiences/audiences.md), elija una de las siguientes opciones:

      * **[!UICONTROL Biblioteca de audiencias]**: cree una audiencia bajo demanda que se guarde en la **[!UICONTROL Biblioteca de audiencias]** y pueda reutilizarse en otras actividades.
      * **[!UICONTROL Solo esta actividad]**: crea una [audiencia específica de la actividad](/help/main/c-target/creating-activity-only-audience.md) que no se guardó en la **[!UICONTROL Biblioteca de audiencias]** y que solo se puede usar en la actividad actual.

   1. Haga clic en **[!UICONTROL Porcentaje de visitantes]** en el cuadro derecho y, a continuación, elija el porcentaje de visitantes correspondiente que quiere que participen de la actividad.

   +++

1. [Revise el resumen de la prueba](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7), realice los cambios que desee y, a continuación, haga clic en **[!UICONTROL Siguiente]**.

## Configurar objetivos y opciones {#configure-goals-and-settings}

En la página **[!UICONTROL Objetivos y configuración]**, indica a [!DNL Target] cómo medir la prueba. La configuración disponible depende de si usa [!DNL Target] o [!DNL Analytics] como fuente de informes.

1. Revise las secciones de la página y configure lo que necesite. Ver [Lo que configuraste en la página Objetivos y configuración](#goals-settings-overview).


   | Sección | Lo que ha configurado |
   |---|---|
   | **[!UICONTROL Configuración de actividades]** | Un objetivo opcional, **[!UICONTROL Priority]** (se usa cuando varias actividades comparten una ubicación y una audiencia) y **[!UICONTROL Duration]** (fechas de inicio y finalización). |
   | **[!UICONTROL Configuración de informes]** | La fuente de informes, la métrica del objetivo (por ejemplo, una métrica de **[!UICONTROL Conversión]**), las métricas adicionales y las audiencias para los informes. La configuración avanzada de la métrica de objetivo también está disponible aquí. |
   | **[!UICONTROL Otros metadatos]** | Notas sobre la actividad que son útiles para usted o para otros integrantes del equipo. |

1. Haga clic en **[!UICONTROL Guardar y cerrar]** para crear la actividad.

Para obtener detalles sobre cada opción, consulte [Objetivos y configuración](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#ab-goals-and-settings).

## Vídeo de formación: Creación de pruebas multivariable (9:25) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

En este vídeo se muestra cómo planificar y crear una prueba multivariable mediante el flujo de trabajo guiado de tres pasos de [!DNL Target].

* Definir y diseñar una prueba multivariable
* Crear una prueba multivariable

>[!VIDEO](https://video.tv.adobe.com/v/29713?captions=spa)
