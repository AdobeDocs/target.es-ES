---
keywords: ingresos;alza de ingresos;aumento estimado de ingresos;estimar alza;valor estimado
description: Calcule el alza que podría lograr si todos los visitantes ven la experiencia ganadora, si las tendencias continúan como lo han hecho durante la prueba.
title: ¿Qué calculo para el alza de ingresos?
feature: Administration & Configuration
role: Admin
exl-id: a3c5e20e-f5d5-4b6f-b169-59d5916584ab
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 85%

---

# Estimar el aumento de ingresos

Use [!DNL Adobe Target] para calcular el aumento de ingresos que obtendría si todos los usuarios vieran la experiencia ganadora.

>[!NOTE]
>
>El alza estimada no está disponible para las actividades [!UICONTROL Experience Targeting] (XT) en este momento.

La característica de alza estimada está desactivada de manera predeterminada. Se puede habilitar en las preferencias de cuenta. Solo los usuarios administradores de Experience Cloud pueden activar o desactivar esta característica. Si se deshabilita el alza estimada, los campos correspondientes no aparecerán en la interfaz. Deshabilitar esta característica no genera pérdidas de datos, incluidos los datos usados para los cálculos. Los cálculos se basan en datos recopilados, independientemente de si la característica está habilitada o no.

>[!IMPORTANT]
>
>El alza estimada es solo una aproximación. Su precisión depende de varios factores, como las cifras previstas si continuaran las tendencias actuales. Estos valores se calculan según el rendimiento anterior y no debe utilizarse como orientación financiera. Los resultados futuros pueden variar.

Esto calcula el aumento obtenido por la experiencia ganadora y el número total de visitantes en toda la duración de la actividad, y muestra el aumento que obtendría si todos los visitantes vieran la experiencia ganadora y las tendencias continuaran igual que durante la prueba.

El aumento estimado en los ingresos se calcula en función de los ingresos por visita (RPV) obtenidos de la métrica del objetivo principal.

El alza estimada se calcula con la fórmula siguiente: (&lt;winning experience RPV> - &lt;control experience RPV&lt;)&#42;&lt;total number of visitors in the activity>

El número resultante se redondea a un decimal, como máximo, si la forma corta tiene un solo dígito antes del decimal. Por ejemplo: 1,6 millones de dólares, 60 000 dólares, 900 dólares, 8500 dólares, 205 000 dólares

Por ejemplo, si la experiencia ganadora muestra un aumento de 0,59 dólares y la experiencia de control muestra un aumento de 0,15 dólares, la estimación calculará un aumento de 0,44 dólares por visitante. Si tiene 75 000 visitantes, el aumento de ingresos resultante será de 33 000 dólares si todos los visitantes ven la experiencia ganadora y continúan las tendencias actuales.

Igualmente, si la experiencia ganadora muestra un aumento de 0,17 dólares en la experiencia de control y recibe 192 000 visitantes durante toda la prueba, si continúan las tendencias actuales puede prever un aumento de ingresos de 32 640 dólares.

El alza estimada en el campo de ingresos se muestra como “---” en las siguientes circunstancias:

* Si no hay suficientes visitantes para realizar un cálculo razonable.
* Si no se ha proporcionado el valor estimado de la métrica en la página de configuración de la métrica.
* Si la experiencia que da mejores resultados es la de control.

Al configurar los objetivos de una actividad, el campo Valor estimado proporciona un valor para el objetivo. Este valor permite a Target calcular el alza estimada de ingresos. Este campo es opcional; sin embargo, los ingresos en aumento de las métricas sin ingresos no se pueden calcular sin él. El tipo de datos es moneda. Este campo se muestra de forma progresiva después de que el usuario indique la acción realizada para alcanzar el objetivo.

Los ingresos estimados si el 100 % de los visitantes ven la experiencia ganadora se muestra en la parte superior de los informes de Target.
