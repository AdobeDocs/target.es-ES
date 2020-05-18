---
keywords: report;reports;reporting;experience cloud solution;timezone;time zone;currency;exclude IPs;estimated lift in revenue;revenue;lift in revenue;fine-grained priorities;fine-grained
description: Para configurar el Compositor de experiencias visuales (VEC) de Adobe Destinatario, especifique su configuración general, la configuración de ventanilla móvil y los selectores CSS.
title: Configurar sistema de informes en Adobe Destinatario
topic: Standard
translation-type: tm+mt
source-git-commit: 34c4c48602df8550287e86c535ebc350fe2185f7
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 69%

---


# Configurar sistema de informes en Destinatario

Configure las opciones generales para utilizarlas en el sistema de informes de Destinatario que se aplican a toda la [!DNL Target] cuenta.

Para acceder a la página de configuración de [!UICONTROL Sistema de informes] , haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Sistema de informes].**

Puede especificar la siguiente configuración en esta página:

* La solución Adobe Experience Cloud que se va a usar para sistema de informes
* El huso horario que se usará para el sistema de informes
* La divisa que se va a utilizar para el sistema de informes
* Direcciones IP para excluir del sistema de informes
* Si se muestra un alza estimada en los ingresos en sistemas de informes
* Si se deben habilitar prioridades específicas

![Página Sistema de informes](/help/administrating-target/assets/reporting.png)

## Solución de Sistema de informes Cloud

Establezca opciones que determinen los datos que se usan para los resultados y los informes.

Seleccione la fuente de informes para sus actividades: [!DNL Target] o Adobe Analytics. Si lo desea, también puede elegir la fuente de informes por actividad.

Tenga en cuenta la siguiente información al elegir su fuente de informes:

* La creación de actividades (AP), la activación y la desactivación de [!UICONTROL Asignación automática], [!UICONTROL Segmentación automática] y [!UICONTROL Personalización automatizada] están permitidas independientemente de la fuente de informes seleccionada. Estos tipos de actividades no son compatibles cuando elige [Adobe Analytics como fuente de informes para Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md). Incluso si establece Analytics como su fuente de informes, [!DNL Target] se utiliza como fuente de informes para estos tipos de actividades.
* Si la fuente de informes está configurada en Analytics, no se le permite activar una actividad que usa [!DNL Target] como fuente de informes (Target especifica la fuente de informes por cada actividad). Debe cambiar la fuente de informes a Analytics en su actividad o cambiar el motor de informes a Seleccionar por actividad en Configuración > Preferencias.
* Si la fuente de informes está configurada en [!DNL Target], no se le permite activar una actividad que use Analytics como fuente de informes. Debe cambiar la fuente de informes a [!DNL Target] en su actividad o cambiar el motor de informes a Seleccionar por actividad en Configuración > Preferencias.
* Si la fuente de informes está configurada en Seleccionar por actividad, puede crear, activar y desactivar actividades que son compatibles con la fuente de informes seleccionada. Para obtener una matriz de actividades compatibles, consulte [Adobe Analytics como fuente de informes para Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T).
* Cuando se cambia de A/B manual a [!UICONTROL Asignación automática] o [!UICONTROL Segmentación automática], todas las métricas y audiencias de informes se pierden si la fuente de informes de la actividad A/B manual no es compatible con las actividades de [!UICONTROL Asignación automática] o [!UICONTROL Segmentación automática].

## Zona horaria del Sistema de informes

Especifique la zona horaria que se va a usar para el sistema de informes.

## Moneda para Sistema de informes

Especifique la divisa que se va a utilizar para el sistema de informes.

## IP que excluir de los datos de sistema de informes de Destinatario

Especifique las direcciones IP que desee excluir de los datos de sistema de informes. Por ejemplo, excluir las direcciones de compañía internas es una buena manera de garantizar que los datos de sistema de informes reflejen las interacciones de los clientes en el sitio web.

Escriba cada dirección IP en una nueva línea.

## Mostrar el alza estimada en ingresos

Puede elegir mostrar el alza estimada en ingresos si introduce un valor monetario para el objetivo. [!DNL Target] puede calcular el aumento de ingresos que obtendría si todos los usuarios vieran la experiencia ganadora. La característica de alza estimada está deshabilitada de manera predeterminada.

Solo los usuarios administradores de Experience Cloud pueden activar o desactivar esta característica. Si se deshabilita el alza estimada, los campos correspondientes no aparecerán en la interfaz. Deshabilitar esta característica no genera pérdidas de datos, incluidos los datos usados para los cálculos. Los cálculos se basan en datos recopilados, independientemente de si la característica está habilitada o no.

Para obtener información detallada, consulte [Calcular el alza de ingresos](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

## Habilitar prioridades ajustadas

Permitir entradas numéricas para prioridades de entre 0 y 999.

La interfaz de usuario y las opciones de Prioridad varían en función de la configuración. Puede usar la configuración heredada de bajo, medio o alto, o habilitar prioridades específicas de 0 a 999.

La prioridad se utiliza si se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.
