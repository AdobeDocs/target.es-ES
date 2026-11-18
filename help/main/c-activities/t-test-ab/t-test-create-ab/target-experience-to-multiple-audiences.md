---
keywords: varios públicos;versiones de experiencias;versiones de experiencias de target
description: Descubra cómo dirigirse a diferentes segmentos de audiencia con versiones de la misma experiencia en actividades A/B.
title: ¿Puedo utilizar varias versiones de una experiencia en una actividad A/B?
feature: A/B Tests
exl-id: 7afe36f0-ec46-4d63-bfff-45d2c8923a04
TQID: 'https://experienceleague.adobe.com/FleyH-u5cWI5vku9E4-RMWeIc95WgPy-VQ-eytxka18'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 4876228feee28031373f7e0abe62a66b05b15274
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 8%
---
# Varios públicos de una experiencia en una prueba A/B {#multiple-experience-audiences}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a segmentar distintas audiencias con versiones de la misma experiencia en una actividad A/B, ilustrada por un caso de uso con los pasos a seguir y las prácticas recomendadas.

>[!ENDSHADEBOX]

En [!DNL Adobe Target] actividades A/B, puede segmentar versiones de la misma experiencia para distintas audiencias. Puede configurar varias audiencias para una experiencia en el **[!UICONTROL Compositor de experiencias visuales]** (VEC) o en el Compositor de experiencias basadas en formularios.

Los datos se recopilan para la experiencia independientemente de la versión, por lo que el informe muestra el rendimiento de la experiencia, no de cada versión. Los visitantes también pueden cambiar entre audiencias de experiencia a medida que cambia su perfil. No permanecen en la misma experiencia durante toda la actividad.

## Caso de uso {#use-case}

Está probando dos experiencias:

* un banner con segmentación geográfica

* un titular genérico.

El titular de cada ubicación geográfica debe ser diferente, pero el objetivo de la prueba es determinar si la segmentación geográfica funciona mejor que el contenido genérico.

Si configura una experiencia independiente para cada ubicación, mide el rendimiento de cada ubicación geográfica en comparación con las demás. No mide si el targeting geográfico ayuda a alcanzar sus objetivos de éxito en comparación con el banner genérico.

En este caso, necesita versiones específicas de la experiencia para poder probar la experiencia de segmentación geográfica con un control sin segmentación geográfica.

Para configurar las versiones específicas de cada ubicación geográfica:

1. [Cree una actividad A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) del modo normal.

   Cuando configure la experiencia que tiene varias versiones, seleccione la audiencia de cada versión, tal como se describe en los pasos siguientes.

1. Seleccione la experiencia y haga clic en **[!UICONTROL Configurar]** > **[!UICONTROL Varias audiencias]**.

1. En el panel **[!UICONTROL Audiencias de experiencia]**, haga clic en el icono **[!UICONTROL Agregar audiencia]** ( ![Agregar icono](/help/main/assets/icons/Add.svg) ) y, a continuación, seleccione la primera audiencia a la que desee dirigirse. Haga lo mismo por cada público.

   Si la audiencia aún no existe, [cree la audiencia](/help/main/c-target/c-audiences/create-audience.md) y configúrela.

1. Continúe configurando la actividad.

## Prácticas recomendadas {#best-practices}

* Elija audiencias que se excluyan mutuamente. Si un visitante cumple los requisitos de más de una audiencia, se devuelve el contenido de todas estas audiencias y el contenido de la audiencia enumerada en último lugar se muestra en la página. Esto se aplica a las actividades creadas en el VEC.
* Las audiencias de entrada de actividad definidas en el diagrama se combinan con las audiencias de experiencia mediante una condición Y. Para entrar en la actividad, un visitante debe cumplir los requisitos de la audiencia de actividad y de una de las audiencias de experiencia.
* Añada las mismas audiencias como segmentos para los informes. Esto le ayuda a ver los resultados de las pruebas en el nivel superior de experiencia, A frente a B, y en el nivel inferior de experiencia, A frente a B solo para &quot;idioma del explorador ja_JP&quot;. Esto solo funciona para informes basados en [!DNL Target], no para informes basados en [!DNL Analytics].
