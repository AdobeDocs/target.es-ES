---
keywords: informe;informes;informes;solución de experience cloud;huso horario;zona horaria;moneda;excluir direcciones IP;alza estimada de ingresos;ingresos;alza de ingresos;prioridades específicas;específicas
description: Uso [!DNL Target] Para Adobe Analytics como fuente de informes, especifique el formato predeterminado de zona horaria y moneda, agregue direcciones IP que excluir de los informes, etc.
title: ¿Cómo configuro la creación de informes en Target?
feature: Administration & Configuration
role: Admin
exl-id: fd83e60e-64a6-4d0e-909f-480d13bac32b
source-git-commit: d414f1554e1875e873f1ce557a7edf86b88ee79e
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 32%

---

# Configuración de informes en Target

Configure las opciones generales para usar en [!DNL Adobe Target] informes que se aplican a todo el [!DNL Target] cuenta.

Para acceder a [!UICONTROL Informes] , haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Informes].**

Puede especificar la siguiente configuración en esta página:

* La solución de Adobe Experience Cloud para la creación de informes
* Zona horaria que se utilizará para los informes
* La moneda que se utilizará para los informes
* Direcciones IP que se excluirán de los informes
* Si se muestra el alza estimada de los ingresos en la creación de informes
* Si habilitar prioridades específicas

>[!NOTE]
>
>Tenga en cuenta que la zona horaria, la moneda y las direcciones IP que deben excluirse se aplican a las actividades que utilizan [!DNL Target] informes. Esta configuración no se aplica a las actividades que utilizan [Analytics for Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md) como fuente de informes.

![Página Informes](/help/main/administrating-target/assets/reporting.png)

## Solución de Reporting Cloud {#solution}

Establezca opciones que determinen los datos que se usan para los resultados y los informes.

Seleccione la fuente de informes para sus actividades: [!DNL Target] o [!DNL Adobe Analytics]. Si lo desea, también puede elegir la fuente de informes por actividad.

Tenga en cuenta la siguiente información al elegir su fuente de informes:

* Si la fuente de informes está configurada en **[!DNL Target]**, no se le permite activar una actividad que use como fuente de informes. [!DNL Analytics] Debe cambiar la fuente de informes a [!DNL Target] en su actividad o cambie la fuente de informes a **[!UICONTROL Seleccionar por actividad]** in **[!UICONTROL Administration] > [!UICONTROL Informes]**.
* Si la fuente de informes está configurada como **[!DNL Analytics]** en este caso, no se le permite activar una actividad que utilice [!DNL Target] como fuente de informes (la fuente de informes se especifica como **[!UICONTROL Objetivo por actividad])**. Debe cambiar la fuente de informes a [!DNL Analytics] en su actividad o cambie el motor de informes a **[!UICONTROL Seleccionar por actividad]** in **[!UICONTROL Administration] > [!UICONTROL Informes]**.
* Si la fuente de informes está configurada como **[!UICONTROL Seleccionar por actividad]** aquí puede crear, activar y desactivar actividades que son compatibles con la fuente de informes seleccionada. Para ver una matriz de actividades compatibles, consulte [Tipos de actividades compatibles](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) in *Adobe Analytics como fuente de informes para Adobe Target (A4t)*.
* [!UICONTROL Automated Personalization] (AP) La creación, activación y desactivación de actividades están permitidas independientemente de la fuente de informes seleccionada. Las actividades de Automated Personalization no son compatibles cuando elige [Adobe Analytics como fuente de informes para Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md). Incluso si especifica [!DNL Analytics] como fuente de informes, [!DNL Target] se utiliza como fuente de informes para las actividades de Automated Personalization. Para obtener más información, consulte [Tipos de actividades compatibles](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) in *Adobe Analytics como fuente de informes para Adobe Target (A4t)*.

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
