---
keywords: informe;informes;informes;solución de experience cloud;huso horario;zona horaria;moneda;excluir direcciones IP;alza estimada de ingresos;ingresos;alza de ingresos;prioridades específicas;específicas
description: Use [!DNL Target], [!DNL Adobe Analytics], or [!DNL Adobe Customer Journey Analytics] como fuente de informes, especifique el formato predeterminado de moneda y zona horaria, agregue direcciones IP que se excluirán de los informes y mucho más.
title: ¿Cómo configuro los informes en  [!DNL Target]?
feature: Administration & Configuration
role: Admin
exl-id: fd83e60e-64a6-4d0e-909f-480d13bac32b
TQID: https://experienceleague.adobe.com/Vdi1o6bvCbgrhWUrJfCOyxqN3JkhEe3Rd9J-3NmLVyY
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e0eb8757-182f-49f3-94a4-1587d16f5094id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 795
ht-degree: 22%

---

# Configurar la creación de informes en [!DNL Target]

Configure las opciones generales para usar en los informes de [!DNL Adobe Target] que se aplican a toda la cuenta de [!DNL Target].

{{permissions-update}}

Para obtener acceso a la página de configuración de [!UICONTROL Informes], haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Informes].**

Puede especificar la siguiente configuración en esta página:

* La solución de Adobe Experience Cloud que se utilizará para la creación de informes
* Zona horaria que se utilizará para los informes
* La moneda que se utilizará para los informes
* Direcciones IP que se excluirán de los informes
* Si se muestra el alza estimada de los ingresos en la creación de informes
* Si habilitar prioridades específicas

>[!NOTE]
>
>Tenga en cuenta que la zona horaria, la moneda y las direcciones IP para excluir la configuración se aplican a las actividades que usan informes de [!DNL Target]. Esta configuración no se aplica a las actividades que usan [Analytics for Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md) o [!DNL Customer Journey Analytics] como fuente de informes.

![Página de informes](/help/main/administrating-target/assets/reporting.png)

## Solución de Reporting Cloud {#solution}

Establezca opciones que determinen los datos que se usan para los resultados y los informes.

Seleccione el origen de los informes para sus actividades: [!DNL Target], [!DNL Adobe Analytics] o [!DNL Adobe Customer Journey Analytics]. También puede elegir la fuente de informes por actividad como parte del flujo de trabajo guiado de tres partes al crear la actividad.

Tenga en cuenta la siguiente información al elegir su fuente de informes:

* **[!DNL Adobe Target]**: si el origen de informes está establecido en **[!DNL Target]** aquí, no se le permite crear ni activar una actividad que use [!DNL Analytics] o [!DNL Customer Journey Analytics] como origen de informes. Debe cambiar la fuente de informes a **[!UICONTROL Seleccionar por actividad]**.
* **[!DNL Adobe Analytics]**: si el origen de informes está establecido en **[!DNL Analytics]** aquí, no se le permite crear ni activar una actividad que use [!DNL Target] o [!DNL Customer Journey Analytics] como origen de informes. Debe cambiar la fuente de informes a **[!UICONTROL Seleccionar por actividad]**.
* **[!DNL Adobe Customer Journey Analytics]**: si el origen de informes está establecido en **[!DNL Customer Journey Analytics]** aquí, no se le permite crear ni activar una actividad que use [!DNL Target] o [!DNL Analytics] como origen de informes. Debe cambiar la fuente de informes a **[!UICONTROL Seleccionar por actividad]**.
* **Seleccionar por actividad**: si la fuente de informes está configurada en **[!UICONTROL Seleccionar por actividad]** aquí, puede crear y activar actividades que son compatibles con la fuente de informes seleccionada.

Al determinar la fuente de informes, tenga en cuenta la siguiente información:

* **[!DNL Analytics]**: para obtener una matriz de actividades compatibles que usan [!DNL Analytics] como fuente de informes (A4T), consulte [Tipos de actividades compatibles](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) en *Adobe Analytics como fuente de informes para Adobe Target (A4t)*.

  La creación y activación de la actividad [!UICONTROL Automated Personalization] (AP) están permitidas independientemente de la fuente de informes seleccionada. Las actividades de [!UICONTROL Automated Personalization] no se admiten cuando elige [Adobe Analytics como fuente de informes para Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

  Aunque especifique [!DNL Analytics] como fuente de informes, [!DNL Target] se usa como fuente de informes para [!DNL Automated Personalization] actividades.

* **[!DNL Customer Journey Analytics]**: para obtener una matriz de actividades compatibles que usan la creación de informes de [!DNL Target] en [!DNL Customer Journey Analytics], consulte [Tipos de actividades compatibles](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md#supported-activities) en la creación de informes de *[!DNL Target]en[!DNL Adobe Customer Journey Analytics]*.

  La creación y activación de actividades de [!UICONTROL Automated Personalization] (AP), [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] están permitidas independientemente de la fuente de informes seleccionada. Estas actividades no son compatibles cuando elige [Adobe Customer Journey Analytics como fuente de informes](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md).

  Aunque especifique [!DNL Customer Journey Analytics] como fuente de informes, [!DNL Target] se usa como fuente de informes para [!DNL Automated Personalization] actividades.

  Si especifica [!DNL Customer Journey Analytics] como fuente de informes para las actividades de [!UICONTROL Asignación automática] o [!UICONTROL Segmentación automática], se puede usar [!DNL Target] o [!DNL Analytics] como fuente de informes.

## Zona horaria para informes

Especifique la zona horaria que se utilizará para la creación de informes.

## Moneda para informes

Especifique la moneda que se utilizará en el informe.

## IP que excluir de [!DNL Target] datos de informes

Especifique las direcciones IP que desee excluir de los datos del sistema de informes. Por ejemplo, la exclusión de las direcciones internas de la compañía es una buena manera de garantizar que los datos de los informes reflejen las interacciones de los clientes en el sitio web.

Escriba cada dirección IP en una línea nueva.

## Mostrar el alza estimada en ingresos

Puede elegir mostrar el alza estimada de ingresos si introduce un valor monetario para el objetivo. [!DNL Target] puede calcular el aumento de ingresos que obtendría si todos los usuarios vieran la experiencia ganadora. La característica de alza estimada está deshabilitada de manera predeterminada.

Solo los usuarios administradores de [!DNL Experience Cloud] pueden habilitar o deshabilitar esta característica. Si se deshabilita el alza estimada, los campos correspondientes no aparecerán en la interfaz. Deshabilitar esta característica no genera pérdidas de datos, incluidos los datos usados para los cálculos. Los cálculos se basan en datos recopilados, independientemente de si la característica está habilitada o no.

Para obtener información detallada, consulte [Calcular el alza de ingresos](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

## Habilitar prioridades ajustadas

Permitir entradas numéricas para prioridades de entre 0 y 999.

La interfaz de usuario y las opciones de Prioridad varían en función de la configuración. Puede usar la configuración heredada de bajo, medio o alto, o habilitar prioridades específicas de 0 a 999.

La prioridad se utiliza si se asignan varias actividades a la misma ubicación con el mismo público. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.
