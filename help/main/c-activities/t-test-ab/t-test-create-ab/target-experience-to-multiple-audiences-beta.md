---
keywords: varias audiencias;versiones de experiencias;versiones de experiencias de target
description: Descubra cómo dirigirse a diferentes segmentos de audiencia con versiones de la misma experiencia en actividades A/B.
title: ¿Puedo utilizar varias versiones de una experiencia en una actividad A/B?
feature: A/B Tests
hide: true
hidefromtoc: true
source-git-commit: ec35109b5d668a96f7e71149df7c965ce2bf3ceb
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 52%

---

# Varias audiencias de una experiencia en una prueba A/B

Puede segmentar versiones de la misma experiencia a distintas audiencias en [!DNL Adobe Target] actividades A/B. Puede configurar varias audiencias para una experiencia en el [!UICONTROL Visual Experience Composer] (VEC) o en el Compositor de experiencias basadas en formularios.

Los visitantes pueden cambiar entre audiencias de experiencia a medida que cambia su perfil. Los visitantes no están atascados en la misma experiencia durante toda la actividad.

Por ejemplo, si un sitio tiene un diseño uniforme en todas las páginas o productos y queremos utilizar la misma experiencia para varias audiencias (p. ej., visitantes con navegadores en distintos idiomas), podemos configurar varias versiones de la experiencia. Podríamos presentar la misma experiencia a los hablantes de inglés y a los de japonés. La diferencia solo estaría en que el texto aparecería en el idioma del visitante. Los datos de la experiencia se recaban independientemente del idioma, por lo que el informe muestra el rendimiento de la experiencia y no la versión.

Si no se pudieran configurar versiones de la experiencia, habría que configurar distintas pruebas por cada idioma (en este ejemplo) y luego añadir manualmente los resultados para tener una idea del rendimiento que podría conseguir una sola experiencia con los dos idiomas. Ese método arroja unos resultados menos precisos. En algunas pruebas, estos cálculos pueden no ser siquiera útiles, ya que los visitantes se seleccionan de forma aleatoria.

Al crear distintas versiones de una experiencia, se recibe información más precisa sin necesidad de cálculos manuales ni conjeturas.

## Escenario

Está probando dos experiencias, un banner con objetivo geográfico en lugar de un banner genérico. El titular de cada geografía debe ser diferente, pero la prueba general es determinar si la segmentación geográfica es mejor que mostrar contenido genérico. Si configura una experiencia independiente para cada ubicación, en realidad estaría midiendo el rendimiento de cada ubicación geográfica en comparación con la otra, en lugar de si el targeting geográfico ayuda a alcanzar sus objetivos de éxito cuando se mide con el banner genérico.

En este caso, lo que necesita son versiones específicas de la experiencia, para que pueda probar la experiencia de segmentación geográfica con un control sin segmentación geográfica.

1. [Cree una actividad A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) del modo normal.

   Al configurar la experiencia que tendrá varias versiones, seleccione la audiencia de cada versión, como vemos en los pasos siguientes.

1. Seleccione la experiencia y haga clic en **[!UICONTROL Configure]** > **[!UICONTROL Multiple Audiences]**.

1. Haga clic en el icono **[!UICONTROL Add Audience]** ( ![Agregar icono](/help/main/assets/icons/Add.svg) ) en el panel Audiencias de experiencia y, a continuación, seleccione la primera audiencia a la que desee dirigirse. Haga lo mismo por cada audiencia.

   Si la audiencia todavía no existe, haga clic en [Crear audiencia](/help/main/c-target/c-audiences/create-audience.md#task_E18BD77A9A8F4ED0AC50569F94556558) y configúrela.

   Si un visitante cumple los requisitos de más de una audiencia, se devuelve el contenido de todas las audiencias, pero en la página se representa la última de la lista.

1. Continúe configurando la actividad.

## Prácticas recomendadas  

* Elija audiencias que se excluyan mutuamente. Si la actividad se creó en el VEC y un visitante coincide con más de una audiencia, se devuelve el contenido de cada audiencia y el contenido de la audiencia se muestra por última vez en la página.
* Las audiencias de participación en la actividad definidas en el diagrama se combinan con las audiencias de experiencia mediante la condición AND. Para participar en la actividad, un visitante debe cumplir los requisitos de la audiencia de la actividad y los requisitos de una de las audiencias de la experiencia.
* Añada las mismas audiencias como segmentos para los informes. Esto le ayuda a ver los resultados de las pruebas en el nivel superior de experiencia, A frente a B, y en el nivel inferior de experiencia, A frente a B solo para &quot;idioma del explorador ja_JP&quot;. Esto solo funciona para informes basados en [!DNL Target], no para informes basados en [!DNL Analytics].