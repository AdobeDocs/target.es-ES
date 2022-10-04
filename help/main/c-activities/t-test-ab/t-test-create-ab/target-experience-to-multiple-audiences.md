---
keywords: varias audiencias;versiones de experiencias;versiones de experiencias de target
description: Aprenda a dirigir versiones de la misma experiencia a distintas audiencias en Adobe [!DNL Target] Actividades A/B.
title: ¿Puedo usar varias versiones de una experiencia en una actividad A/B?
feature: A/B Tests
exl-id: 7afe36f0-ec46-4d63-bfff-45d2c8923a04
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 92%

---

# Varias audiencias de una experiencia en una prueba A/B

Puede dirigir versiones de la misma experiencia a distintas audiencias en [!DNL Adobe Target] Actividades A/B. Puede configurar varias audiencias para una experiencia en el Compositor de experiencias visuales o en el Compositor de experiencias basadas en formularios.

Los usuarios pueden cambiar entre audiencias de experiencias a medida que cambian sus perfiles. No están atrapados en la misma experiencia todo el tiempo que dure la actividad.

Por ejemplo, si un sitio tiene un diseño uniforme en todas las páginas o productos y queremos utilizar la misma experiencia para varias audiencias (p. ej., visitantes con navegadores en distintos idiomas), podemos configurar varias versiones de la experiencia. Podríamos presentar la misma experiencia a los hablantes de inglés y a los de japonés. La diferencia solo estaría en que el texto aparecería en el idioma del visitante. Los datos de la experiencia se recaban independientemente del idioma, por lo que el informe muestra el rendimiento de la experiencia y no la versión.

Si no se pudieran configurar versiones de la experiencia, habría que configurar distintas pruebas por cada idioma (en este ejemplo) y luego añadir manualmente los resultados para tener una idea del rendimiento que podría conseguir una sola experiencia con los dos idiomas. Ese método arroja unos resultados menos precisos. En algunas pruebas, estos cálculos pueden no ser siquiera útiles, ya que los visitantes se seleccionan de forma aleatoria.

Al crear distintas versiones de una experiencia, se recibe información más precisa sin necesidad de cálculos manuales ni conjeturas.

## Situación

Vamos a probar dos experiencias, un banner con segmentación geográfica y otro genérico. El banner de cada ubicación geográfica tiene que ser distinto, pero la prueba general consiste en determinar si la segmentación geográfica es mejor que mostrar el contenido genérico. Si configuráramos una experiencia distinta para cada ubicación, estaríamos midiendo el rendimiento de cada ubicación en relación con las demás, no si la segmentación geográfica ayuda más que el banner genérico a lograr los objetivos de éxito.

En este caso, lo que necesitamos son versiones geográficas de la experiencia para poder probar la experiencia segmentada geográficamente con un control no segmentado geográficamente.

1. [Cree una actividad A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) del modo normal.

   Al configurar la experiencia que tendrá varias versiones, seleccione la audiencia de cada versión, como vemos en los pasos siguientes.

1. Seleccione la experiencia y haga clic en **[!UICONTROL Configurar]** > **[!UICONTROL Audiencias]** > **[!UICONTROL Varias audiencias]**.

   ![Opción Varias audiencias](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/multiple-audiences-new.png)

1. Haga clic en **[!UICONTROL Añadir audiencia]** y seleccione la primera audiencia a la que se quiere dirigir. Haga lo mismo por cada audiencia.

   ![imagen exp-versions](assets/exp-versions.png)

   Si la audiencia todavía no existe, haga clic en [Crear audiencia](/help/main/c-target/c-audiences/create-audience.md#task_E18BD77A9A8F4ED0AC50569F94556558) y configúrela.

   Si un visitante cumple los requisitos de más de una audiencia, se devuelve el contenido de todas las audiencias, pero en la página se representa la última de la lista.

1. Continúe configurando la actividad.

## Prácticas recomendadas  

* Elija audiencias que se excluyan entre sí. Si la actividad se creó en el VEC y un visitante se ajusta a más de una audiencia, se devuelve el contenido de todas, pero el que aparece en la página es el de la última audiencia de la lista.
* Las audiencias de participación en la actividad definidas en el diagrama se combinan con las audiencias de experiencia mediante la condición AND. Para participar en la actividad, un visitante debe cumplir los requisitos de la audiencia de la actividad y los requisitos de una de las audiencias de la experiencia.
* Añada las mismas audiencias como segmentos para los informes. De este modo, se pueden ver los resultados de las pruebas tanto en el nivel superior de experiencia, A comparado con B, como en el nivel inferior de experiencia, A comparado con B solo en el “idioma de navegador ja_JP”. Esto solo funciona para los informes de Target, no para los de Analytics.
