---
keywords: informe;informes;solución de experience cloud;zona horaria;zona horaria;moneda;excluir direcciones IP;alza estimada de ingresos;ingresos;alza de ingresos;prioridades específicas;específicas
description: Use [!DNL Target] o Adobe Analytics como fuente de informes, especifique la zona horaria y el formato de moneda predeterminados, agregue direcciones IP para excluir de los informes, etc.
title: ¿Cómo configuro los informes en Target?
feature: Administración y configuración
role: Administrator
exl-id: fd83e60e-64a6-4d0e-909f-480d13bac32b
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 31%

---

# Configuración de informes en Target

Configure las opciones generales para usarlas en los informes [!DNL Adobe Target] que se aplican a toda la cuenta [!DNL Target].

Para acceder a la página de configuración de [!UICONTROL Reporting], haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Reporting].**

Puede especificar la siguiente configuración en esta página:

* La solución de Adobe Experience Cloud que se utilizará para la creación de informes
* Zona horaria que se usará para los informes
* La moneda que se usará para los informes
* Direcciones IP que se excluirán de los informes
* Si se muestra el alza estimada de ingresos en los informes
* Si se deben habilitar prioridades específicas

>[!NOTE]
>
>Tenga en cuenta que la zona horaria, la moneda y las direcciones IP que excluyen la configuración se aplican a las actividades que utilizan informes [!DNL Target]. Estas configuraciones no se aplican a actividades que utilizan [Analytics for Target (A4T)] como fuente de informes (/help/c-integrating-target-with-mac/a4t/a4t.md).

![Página Informes](/help/administrating-target/assets/reporting.png)

## Solución de nube de informes

Establezca opciones que determinen los datos que se usan para los resultados y los informes.

Seleccione la fuente de informes para sus actividades: [!DNL Target] o [!DNL Adobe Analytics]. Si lo desea, también puede elegir la fuente de informes por actividad.

Tenga en cuenta la siguiente información al elegir su fuente de informes:

* Si la fuente de informes está configurada en **[!DNL Target]**, no se le permite activar una actividad que use como fuente de informes. [!DNL Analytics] Debe cambiar la fuente de informes a [!DNL Target] en su actividad o cambiar la fuente de informes a **[!UICONTROL Seleccionar por actividad]** en **[!UICONTROL Administración] > [!UICONTROL Informes]**.
* Si la fuente de informes está configurada en **[!DNL Analytics]** aquí, no se le permite activar una actividad que usa [!DNL Target] como fuente de informes (la fuente de informes se especifica como **[!UICONTROL Target por actividad])**. Debe cambiar la fuente de informes a [!DNL Analytics] en su actividad o cambiar el motor de informes a **[!UICONTROL Seleccionar por actividad]** en **[!UICONTROL Administración] > [!UICONTROL Informes]**.
* Si la fuente de informes está configurada en **[!UICONTROL Select per activity]** aquí, puede crear, activar y desactivar actividades que sean compatibles con la fuente de informes seleccionada. Para obtener una matriz de actividades compatibles, consulte [Tipos de actividades compatibles](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) en *Adobe Analytics como fuente de informes para Adobe Target (A4t)*.
* [!UICONTROL La creación, activación y desactivación de actividades de Automated Personalization]  (AP) están permitidas independientemente de la fuente de informes seleccionada. Las actividades de Automated Personalization no son compatibles cuando elige [Adobe Analytics como fuente de informes para Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md). Aunque especifique [!DNL Analytics] como fuente de informes, [!DNL Target] se utilizará como fuente de informes para las actividades de Automated Personalization. Para obtener más información, consulte [Tipos de actividades compatibles](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) en *Adobe Analytics como fuente de informes para Adobe Target (A4t)*.

## Zona horaria para la creación de informes

Especifique la zona horaria que se usará para los informes.

## Moneda para informes

Especifique la moneda que se usará para los informes.

## IP a excluir de los datos de informes [!DNL Target]

Especifique las direcciones IP que desee excluir de los datos de informes. Por ejemplo, excluir las direcciones internas de la empresa es una buena manera de garantizar que los datos de los informes reflejen las interacciones de los clientes en el sitio web.

Introduzca cada dirección IP en una nueva línea.

## Mostrar el alza estimada en ingresos

Puede elegir mostrar el alza estimada de ingresos si introduce un valor monetario para el objetivo. [!DNL Target] puede calcular el aumento de ingresos que obtendría si todos los usuarios vieran la experiencia ganadora. La característica de alza estimada está deshabilitada de manera predeterminada.

Solo los usuarios administradores de [!DNL Experience Cloud] pueden habilitar o deshabilitar esta función. Si se deshabilita el alza estimada, los campos correspondientes no aparecerán en la interfaz. Deshabilitar esta característica no genera pérdidas de datos, incluidos los datos usados para los cálculos. Los cálculos se basan en datos recopilados, independientemente de si la característica está habilitada o no.

Para obtener información detallada, consulte [Calcular el alza de ingresos](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

## Habilitar prioridades ajustadas

Permitir entradas numéricas para prioridades de entre 0 y 999.

La interfaz de usuario y las opciones de Prioridad varían en función de la configuración. Puede usar la configuración heredada de bajo, medio o alto, o habilitar prioridades específicas de 0 a 999.

La prioridad se utiliza si se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.
