---
keywords: informe;informes;informes;solución de experience cloud;huso horario;zona horaria;moneda;excluir direcciones IP;alza estimada de ingresos;ingresos;alza de ingresos;prioridades específicas;específicas
description: Uso [!DNL Target], [!DNL Adobe Analytics], or [!DNL Adobe Customer Journey Analytics] como fuente de informes, especifique el formato predeterminado de zona horaria y moneda, añada direcciones IP que excluir de los informes, etc.
title: ¿Cómo configuro los informes en? [!DNL Target]?
feature: Administration & Configuration
role: Admin
exl-id: fd83e60e-64a6-4d0e-909f-480d13bac32b
source-git-commit: ea9513c4310d13e1e7899aa7e228b4d7ecdf0748
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 22%

---

# Configuración de informes en [!DNL Target]

Configure las opciones generales para usar en [!DNL Adobe Target] informes que se aplican a todo el [!DNL Target] cuenta.

Para acceder a [!UICONTROL Reporting] , haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Reporting].**

Puede especificar la siguiente configuración en esta página:

* La solución de Adobe Experience Cloud para la creación de informes
* Zona horaria que se utilizará para los informes
* La moneda que se utilizará para los informes
* Direcciones IP que se excluirán de los informes
* Si se muestra el alza estimada de los ingresos en la creación de informes
* Si habilitar prioridades específicas

>[!NOTE]
>
>Tenga en cuenta que la zona horaria, la moneda y las direcciones IP que deben excluirse se aplican a las actividades que utilizan [!DNL Target] informes. Esta configuración no se aplica a las actividades que utilizan [Analytics for Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md) o [!DNL Customer Journey Analytics] como fuente de informes.

![Página Informes](/help/main/administrating-target/assets/reporting.png)

## Solución de Reporting Cloud {#solution}

Establezca opciones que determinen los datos que se usan para los resultados y los informes.

Seleccione la fuente de informes para sus actividades: [!DNL Target], [!DNL Adobe Analytics], o [!DNL Adobe Customer Journey Analytics]. También puede elegir la fuente de informes por actividad como parte del flujo de trabajo guiado de tres partes al crear la actividad.

Tenga en cuenta la siguiente información al elegir su fuente de informes:

* **[!DNL Adobe Target]**: si la fuente de informes está configurada en **[!DNL Target]** en este caso, no se le permite crear ni activar una actividad que utilice [!DNL Analytics] o [!DNL Customer Journey Analytics] como fuente de informes. Debe cambiar la fuente de informes a **[!UICONTROL Select per activity]**.
* **[!DNL Adobe Analytics]**: si la fuente de informes está configurada en **[!DNL Analytics]** en este caso, no se le permite crear ni activar una actividad que utilice [!DNL Target] o [!DNL Customer Journey Analytics] como fuente de informes. Debe cambiar la fuente de informes a **[!UICONTROL Select per activity]**.
* **[!DNL Adobe Customer Journey Analytics]**: si la fuente de informes está configurada en **[!DNL Customer Journey Analytics]** en este caso, no se le permite crear ni activar una actividad que utilice [!DNL Target] o [!DNL Analytics] como fuente de informes. Debe cambiar la fuente de informes a **[!UICONTROL Select per activity]**.
* **Seleccionar por actividad**: si la fuente de informes está configurada en **[!UICONTROL Select per activity]** aquí puede crear y activar actividades que sean compatibles con la fuente de informes seleccionada.

Al determinar la fuente de informes, tenga en cuenta la siguiente información:

* **[!DNL Analytics]**: para obtener una matriz de actividades compatibles con [!DNL Analytics] como fuente de informes (A4T), consulte [Tipos de actividades compatibles](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) in *Adobe Analytics como fuente de informes para Adobe Target (A4t)*.

  [!UICONTROL Automated Personalization] (AP) La creación y activación de actividades están permitidas independientemente de la fuente de informes seleccionada. [!UICONTROL Automated Personalization] Las actividades de no son compatibles cuando elige [Adobe Analytics como fuente de informes para Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

  Incluso si especifica [!DNL Analytics] como fuente de informes, [!DNL Target] se usa como fuente de informes para [!DNL Automated Personalization] actividades.

* **[!DNL Customer Journey Analytics]**: para obtener una matriz de actividades compatibles con [!DNL Target] creación de informes en [!DNL Customer Journey Analytics], consulte [Tipos de actividades compatibles](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md#supported-activities) in *[!DNL Target]creación de informes en[!DNL Adobe Customer Journey Analytics]*.

  [!UICONTROL Automated Personalization] (AP), [!UICONTROL Auto-Allocate], y [!UICONTROL Auto-Target] la creación y activación de actividades están permitidas independientemente de la fuente de informes seleccionada. Estas actividades no son compatibles cuando elige [Adobe Customer Journey Analytics como fuente de informes](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md).

  Incluso si especifica [!DNL Customer Journey Analytics] como fuente de informes, [!DNL Target] se usa como fuente de informes para [!DNL Automated Personalization] actividades.

  Si especifica [!DNL Customer Journey Analytics] como fuente de informes para [!UICONTROL Auto-Allocate] o [!UICONTROL Auto-Target] actividades, [!DNL Target] o [!DNL Analytics] puede utilizarse como fuente de informes.

## Zona horaria para informes

Especifique la zona horaria que se utilizará para la creación de informes.

## Moneda para informes

Especifique la moneda que se utilizará en el informe.

## IP que excluir de [!DNL Target] datos de informes

Especifique las direcciones IP que desee excluir de los datos del sistema de informes. Por ejemplo, la exclusión de las direcciones internas de la compañía es una buena manera de garantizar que los datos de los informes reflejen las interacciones de los clientes en el sitio web.

Escriba cada dirección IP en una línea nueva.

## Mostrar el alza estimada en ingresos

Puede elegir mostrar el alza estimada de ingresos si introduce un valor monetario para el objetivo. [!DNL Target] puede calcular el aumento de ingresos que obtendría si todos los usuarios vieran la experiencia ganadora. La característica de alza estimada está deshabilitada de manera predeterminada.

Solo [!DNL Experience Cloud] Los usuarios administradores pueden activar o desactivar esta función. Si se deshabilita el alza estimada, los campos correspondientes no aparecerán en la interfaz. Deshabilitar esta característica no genera pérdidas de datos, incluidos los datos usados para los cálculos. Los cálculos se basan en datos recopilados, independientemente de si la característica está habilitada o no.

Para obtener información detallada, consulte [Calcular el alza de ingresos](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

## Habilitar prioridades ajustadas

Permitir entradas numéricas para prioridades de entre 0 y 999.

La interfaz de usuario y las opciones de Prioridad varían en función de la configuración. Puede usar la configuración heredada de bajo, medio o alto, o habilitar prioridades específicas de 0 a 999.

La prioridad se utiliza si se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.
