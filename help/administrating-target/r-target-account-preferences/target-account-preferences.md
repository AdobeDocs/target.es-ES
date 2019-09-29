---
description: Configure las preferencias de su cuenta para que Target Standard o Target Premium funcionen correctamente con la cuenta.
keywords: preferencias de cuenta;preferencias;detalles de sitio;nombre de mbox personalizado;solución de Experience Cloud usada para los informes;Mostrar alza estimada de los ingresos;selectores css;usar clases de elementos;URL predeterminada del Compositor de experiencias visuales;Activar el compositor de experiencias mejorado;Generar instantáneas de experiencia;configuración de las ventanillas móviles;sector vertical;criterios incompatibles de filtro
seo-description: Configure las preferencias de su cuenta para que Adobe Target Standard o Target Premium funcionen correctamente con la cuenta.
seo-title: Preferencias
solution: Target
subtopic: Primeros pasos
title: Preferencias
topic: Standard
uuid: ed3904c8-533b-4b9c-a3a1-079c61b1bf2a
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Preferencias{#preferences}

Configure las preferencias de su cuenta para que [!DNL Target Standard] o [!DNL Target Premium] funcionen correctamente con la cuenta.

Para definir las preferencias de la cuenta, haga clic en **[!UICONTROL Configuración]** &gt; **[!UICONTROL Preferencias]**, configure las preferencias que quiera y, luego, haga clic en **[!UICONTROL Enviar]**.

La ilustración siguiente muestra las opciones de configuración disponibles en la página [!UICONTROL Preferencias de cuenta].

![página Preferencias](/help/administrating-target/r-target-account-preferences/assets/target-account-preferences.png)

>[!NOTE]
>
>Algunas de estas preferencias solo están disponibles si tiene [Target Premium](/help/c-intro/intro.md#premium).

## Detalles del sitio {#section_04A3340FC29B46978DB77058259F4EE0}

Especifique cómo se ha configurado el sitio.

### Mbox global personalizado

Seleccione el nombre de mbox opcional que está utilizando para publicar actividades de [!DNL Target]. Este mbox global debe estar vacío, lo que significa que no tiene contenido predeterminado. Guarde esta configuración solo después de que el archivo [!DNL at.js] o [!DNL mbox.js] se haya instalado en el sitio.

>[!CAUTION]
>
>Si configura esta opción incorrectamente podrían interrumpirse las actividades existentes.

## Resultados e informes {#section_47C887AABD704A96BCD1C00BEABF4BCE}

Establezca opciones que determinen los datos que se usan para los resultados y los informes.

| Opción | Descripción |
|--- |--- |
| Solución de Experience Cloud que se usa para los informes | Seleccione la fuente de informes para sus actividades: [!DNL Target] o Adobe Analytics. Si lo desea, también puede elegir la fuente de informes por actividad. Tenga en cuenta la siguiente información al elegir su fuente de informes:<ul><li>La creación de actividades (AP), la activación y la desactivación de [!UICONTROL Asignación automática], [!UICONTROL Segmentación automática] y [!UICONTROL Personalización automatizada] están permitidas independientemente de la fuente de informes seleccionada. Estos tipos de actividades no son compatibles cuando elige [Adobe Analytics como fuente de informes para Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md). Incluso si establece Analytics como su fuente de informes, [!DNL Target] se utiliza como fuente de informes para estos tipos de actividades.</li><li>Si la fuente de informes está configurada en Analytics, no se le permite activar una actividad que usa [!DNL Target] como fuente de informes (Target especifica la fuente de informes por cada actividad). Debe cambiar la fuente de informes a Analytics en su actividad o cambiar el motor de informes a Seleccionar por actividad en Configuración &gt; Preferencias.</li><li>Si la fuente de informes está configurada en [!DNL Target], no se le permite activar una actividad que use Analytics como fuente de informes. Debe cambiar la fuente de informes a [!DNL Target] en su actividad o cambiar el motor de informes a Seleccionar por actividad en Configuración &gt; Preferencias.</li><li>Si la fuente de informes está configurada en Seleccionar por actividad, puede crear, activar y desactivar actividades que son compatibles con la fuente de informes seleccionada. Para obtener una matriz de actividades compatibles, consulte [Adobe Analytics como fuente de informes para Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T).</li><li>Cuando se cambia de A/B manual a [!UICONTROL Asignación automática] o [!UICONTROL Segmentación automática], todas las métricas y audiencias de informes se pierden si la fuente de informes de la actividad A/B manual no es compatible con las actividades de [!UICONTROL Asignación automática] o [!UICONTROL Segmentación automática].</li></ul> |
| Mostrar el alza estimada en ingresos | También puede elegir mostrar el alza estimada en ingresos si introduce un valor monetario en el objetivo. [!DNL Target] puede calcular el aumento de ingresos que obtendría si todos los usuarios vieran la experiencia ganadora. La característica de alza estimada está deshabilitada de manera predeterminada.<br>Solo los usuarios administradores de Experience Cloud pueden activar o desactivar esta característica. Si se deshabilita el alza estimada, los campos correspondientes no aparecerán en la interfaz. Deshabilitar esta característica no genera pérdidas de datos, incluidos los datos usados para los cálculos. Los cálculos se basan en datos recopilados, independientemente de si la característica está habilitada o no.<br>Para obtener información detallada, consulte [Calcular el alza de ingresos](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md). |
| Habilitar prioridades ajustadas | Permitir entradas numéricas para prioridades de entre 0 y 999.<br>La interfaz de usuario y las opciones de Prioridad varían en función de la configuración. Puede usar la configuración heredada de bajo, medio o alto, o habilitar prioridades específicas de 0 a 999.<br>La prioridad se utiliza si se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta. |

## Selectores CSS {#section_8155EDBF449E4198863235F94D1EA872}

Explica cómo [!DNL Target] genera los selectores CSS.

Estas opciones ayudan a [!DNL Target] a comprender la estructura de su sitio para generar mejores selectores CSS para la entrega de contenido. De forma predeterminada, [!DNL Target] genera selectores en función de los ID de elementos de la página. Si el sitio usa pocos ID, o ID duplicados en la misma página, usar estas clases puede ser una mejor opción.

Puede elegir una o ambas de las siguientes opciones:

| Opción | Descripción |
|--- |--- |
| Usar identificadores de elementos | Desmarque esta opción si se usa el mismo identificador para varios elementos o si el identificador de elemento puede cambiar en la carga de página. |
| Usar clases de elementos | De manera predeterminada, [!DNL Target] solo usa ID de elementos. Sin embargo, si la página está diseñada para usar clases para identificar elementos, como una página creada con [!DNL Adobe Experience Manager], también debería seleccionar [!UICONTROL Usar clases de elementos].<br>**Nota:** aunque se ha hecho todo lo posible para garantizar la precisión, tenga en cuenta que el uso de estas clases puede generar errores. Si no selecciona ninguna opción, también se ve afectada la precisión. El orden de la precisión es ID &gt; clases &gt; ninguna opción. También asegúrese de probar la página para asegurarse de que los selectores sean correctos.<br>Puede anular esta configuración por actividad (haga clic en el icono de engranaje [!UICONTROL Configuración], luego seleccione [!UICONTROL Selectores CSS]). Esto resulta especialmente útil si tiene varios sitios que están configurados de forma diferente.<br>**Nota:** No se puede anular la configuración por actividad en las actividades de [!UICONTROL Personalización automatizada] y [!UICONROL Pruebas multivariable].  Consulte [Selectores de elementos utilizados en el Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/vec-selectors.md) para obtener información adicional sobre selectores. |

## Compositor de experiencias visuales {#section_CD9BDD372CF54E678F88E8BA95757A5A}

| Opción | Descripción |
|--- |--- |
| URL predeterminada del Compositor de experiencias visuales | La dirección URL predeterminada que utiliza el [!UICONTROL Compositor de experiencias visuales]. Esta es la página predeterminada, como la página principal, que se utiliza siempre que quiere configurar una experiencia para cada nueva actividad. Si no establece una URL predeterminada, tiene que escribir una URL para cada actividad en el momento de la creación. |
| Activar el compositor de experiencias mejorado | Permite editar en sitios con eliminación de iFrames y sitios con contenido mixto. Es posible que algunos sitios no sean compatibles con la versión mejorada. Desactive esta opción para revertir al Compositor de experiencias original. La publicación de actividades en los sitios no se verá afectada por esta opción.<br>Para obtener más información, consulte [Solución de problemas del Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).<br>**Nota:** También puede habilitar el Compositor de experiencias mejorado en el nivel de actividad. |
| Cargar contenido combinado | Habilite el contenido combinado al abrir un sitio web mediante el Compositor de experiencias mejorado (EEC). Al habilitar esta opción, se evitará una carga excesiva de recursos estáticos a través de los servidores proxy de Target.<br>Esta opción resulta útil, por ejemplo, si los encabezados de Políticas de seguridad de contenido (CSP) permiten cargar contenido mixto sin el uso de servidores proxy con el EEC habilitado.<br>Esta opción también resulta útil si el sitio web HTTP tiene una mayor cantidad de tiempo de carga en el EEC, donde JavaScript, imágenes, etc. tardan más de lo esperado en cargarse mediante proxy. |
| Generar instantáneas de experiencia | Cuando se habilitan las instantáneas de experiencia, se generan miniaturas de las experiencias en el diagrama de flujo de trabajo de la actividad. Si deshabilita las instantáneas, podría obtener un rendimiento más rápido para algunos usuarios. |

## Configuración de las ventanillas móviles {#section_42176D062BCE4A28ADBB784CC4BEF84D}

Puede añadir dispositivos para usarlos al obtener una vista previa de las experiencias. Cada dispositivo tiene una audiencia asociada.

| Opción | Descripción |
|--- |--- |
| ![Distintivo Premium](/help/assets/premium.png) Agregar nuevo | Haga clic en [!UICONTROL Agregar nueva], escriba un nombre descriptivo para la ventanilla móvil, especifique la anchura y la altura, seleccione un sistema operativo y, por último, haga clic en [!UICONTROL Guardar].  Si desea información sobre cómo añadir una ventanilla móvil, consulte [Configuración de la ventanilla móvil](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md). |

## Vídeo de formación: Preferencias de cuenta (7:33)

Este vídeo incluye información sobre las preferencias de cuenta.

* Describir la configuración de la cuenta disponible en [!DNL Target Standard]

>[!VIDEO](https://video.tv.adobe.com/v/17379?captions=spa)