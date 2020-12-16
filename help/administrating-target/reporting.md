---
keywords: report;reports;reporting;experience cloud solution;timezone;time zone;currency;exclude IPs;estimated lift in revenue;revenue;lift in revenue;fine-grained priorities;fine-grained
description: Configure el Compositor de experiencias visuales (VEC) de Adobe Target especificando su configuración general, la configuración de ventanilla móvil y los selectores CSS.
title: Configurar sistema de informes en Adobe Target
feature: administration general
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 33%

---


# Configurar sistema de informes en Destinatario

Configure las opciones generales para usarlas en el sistema de informes [!DNL Adobe Target] que se aplican a toda la cuenta [!DNL Target].

Para acceder a la página de configuración [!UICONTROL Sistema de informes], haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Sistema de informes].**

Puede especificar la siguiente configuración en esta página:

* La solución Adobe Experience Cloud que se va a usar para sistema de informes
* El huso horario que se usará para el sistema de informes
* La divisa que se va a utilizar para el sistema de informes
* Direcciones IP para excluir del sistema de informes
* Si se muestra un alza estimada en los ingresos en sistemas de informes
* Si se deben habilitar prioridades específicas

>[!NOTE]
>
>Tenga en cuenta que la configuración de zona horaria, moneda y direcciones IP para excluir se aplica a actividades que utilizan sistema de informes [!DNL Target]. Esta configuración no se aplica a actividades que utilizan [Analytics para Destinatario (A4T)] como fuente de sistema de informes (/help/c-integrating-target-with-mac/a4t/a4t.md).

![Página sistema de informes](/help/administrating-target/assets/reporting.png)

## Solución de sistema de informes Cloud

Establezca opciones que determinen los datos que se usan para los resultados y los informes.

Seleccione la fuente de informes para sus actividades: [!DNL Target] o [!DNL Adobe Analytics]. Si lo desea, también puede elegir la fuente de informes por actividad.

Tenga en cuenta la siguiente información al elegir su fuente de informes:

* Si la fuente de informes está configurada en **[!DNL Target]**, no se le permite activar una actividad que use como fuente de informes. [!DNL Analytics] Debe cambiar el origen del sistema de informes a [!DNL Target] en la actividad o cambiar el origen del sistema de informes a **[!UICONTROL Seleccionar por actividad]** en **[!UICONTROL Administración] > [!UICONTROL Sistema de informes]**.
* Si el origen de sistema de informes está establecido en **[!DNL Analytics]** aquí, no se le permite activar una actividad que utilice [!DNL Target] como origen de sistema de informes (el origen de sistema de informes se especifica como **[!UICONTROL Destinatario por actividad])**. Debe cambiar el origen de sistema de informes a [!DNL Analytics] en la actividad o cambiar el motor de sistema de informes a **[!UICONTROL Seleccionar por actividad]** en **[!UICONTROL Administración] > [!UICONTROL Sistema de informes]**.
* Si el origen de sistema de informes está establecido en **[!UICONTROL Seleccionar por actividad]** aquí, puede crear, activar y desactivar actividades que sean compatibles con el origen de sistema de informes seleccionado. Para obtener una matriz de actividades admitidas, consulte [Tipos de actividades admitidas](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) en *Adobe Analytics como fuente de sistema de informes para Adobe Target (A4t)*.
* [!UICONTROL La creación, activación y desactivación de actividades de Automated Personalization] (AP) están permitidas independientemente del origen de sistema de informes seleccionado. Las actividades de Automated Personalization no son compatibles cuando elige [Adobe Analytics como fuente de sistema de informes para Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md). Aunque especifique [!DNL Analytics] como fuente de sistema de informes, [!DNL Target] se utiliza como fuente de sistema de informes para actividades de Automated Personalization. Para obtener más información, consulte [Tipos de actividad admitidos](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) en *Adobe Analytics como fuente de sistema de informes para Adobe Target (A4t)*.

## Zona horaria del Sistema de informes

Especifique la zona horaria que se va a usar para el sistema de informes.

## Moneda para Sistema de informes

Especifique la divisa que se va a utilizar para el sistema de informes.

## IP que excluir de los datos de sistema de informes de Destinatario

Especifique las direcciones IP que desee excluir de los datos de sistema de informes. Por ejemplo, excluir las direcciones de compañía internas es una buena manera de garantizar que los datos de sistema de informes reflejen las interacciones de los clientes en el sitio web.

Escriba cada dirección IP en una nueva línea.

## Mostrar el alza estimada en ingresos

Puede elegir mostrar el alza estimada en ingresos si introduce un valor monetario para el objetivo. [!DNL Target] puede calcular el aumento de ingresos que obtendría si todos los usuarios vieran la experiencia ganadora. La característica de alza estimada está deshabilitada de manera predeterminada.

Sólo los usuarios administradores [!DNL Experience Cloud] pueden habilitar o deshabilitar esta función. Si se deshabilita el alza estimada, los campos correspondientes no aparecerán en la interfaz. Deshabilitar esta característica no genera pérdidas de datos, incluidos los datos usados para los cálculos. Los cálculos se basan en datos recopilados, independientemente de si la característica está habilitada o no.

Para obtener información detallada, consulte [Calcular el alza de ingresos](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

## Habilitar prioridades ajustadas

Permitir entradas numéricas para prioridades de entre 0 y 999.

La interfaz de usuario y las opciones de Prioridad varían en función de la configuración. Puede usar la configuración heredada de bajo, medio o alto, o habilitar prioridades específicas de 0 a 999.

La prioridad se utiliza si se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.
