---
title: Creación de informes
description: Obtenga información sobre cómo ver los informes de indicadores de funcionalidades en Marcas con Customer Journey Analytics.
hide: true
exl-id: edddca99-f263-461b-a16f-b46ee7c15f6c
source-git-commit: eeba7af62ab101e687852ce993a001832ce4a83b
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 0%

---

# Creación de informes {#reporting}

Marcas entrega informes a través de **Customer Journey Analytics (CJA)**. Hay una ficha **Informe** disponible en cada indicador de características y página de detalles de grupo de características. Permite ver un informe de CJA con un ámbito de ese indicador o grupo específico, incrustado directamente en la página.

>[!NOTE]
>
>Los informes se abren con una ventana de informes de **30 días** de manera predeterminada. Puede ajustar el intervalo desde el encabezado del panel.

## Requisitos previos {#prerequisites}

Antes de poder ver los informes, asegúrese de lo siguiente:

1. Los informes están configurados para su aplicación. Consulte [Configurar los informes con Customer Journey Analytics](#setup).
1. El indicador o grupo de características está activo y tiene datos acumulados.

## Ver un informe {#view-report}

### Abra la pestaña Informe y elija una vista de datos {#open-report-tab}

1. Abra un indicador o un grupo de características y seleccione la ficha **Informe**.
1. Se abre el cuadro de diálogo **Seleccionar vista de datos**, que enumera las vistas de datos de CJA disponibles para usted. La primera está seleccionada de forma predeterminada.
1. Elija la vista de datos que desee y seleccione **Ver informe**. Seleccione **Cancelar** para cerrar el cuadro de diálogo sin cargar un informe.
1. El informe se carga dentro de la pestaña, con un ámbito de ese indicador o ID de entidad del grupo.

![Pestaña Informe en la página de detalles de un indicador de funcionalidad](assets/report-tab.png)

>[!NOTE]
>
>El cuadro de diálogo solo enumera las vistas de datos a las que tiene acceso en la zona protegida actual. Si no hay ninguno disponible, el cuadro de diálogo mostrará un mensaje y **Ver informe** permanecerá deshabilitado. Compruebe los permisos de vista de datos o cambie de zona protegida.

![Cuadro de diálogo Seleccionar vista de datos](assets/select-dataview.png)

### Ver el informe de rendimiento {#view-performance-report}

Se muestra el panel **Información general de indicadores** incrustado:

* **Total de personas**, **Participación de personas por día** y **Participación de personas por variante** (grupo de control frente a ID de variante)
* Una tabla **Información general** que enumera cada variante con su porcentaje de personas y participación

Ajuste el intervalo de fechas del encabezado del panel para volver a trazar para una ventana diferente (valor predeterminado 30 días).

![Informe de rendimiento de información general de indicadores](assets/performance-report.png)

### Explorar resultados de experimentación {#explore-experimentation-results}

1. En el panel **Experimentación**, el **Experimento** (indicador o identificador de entidad de grupo) y la **variante de control** están preseleccionados.
1. Agregue una **métrica de éxito** mediante **Agregar métrica** y elija una **métrica de normalización** (valor predeterminado **Personas**) basada en el gráfico que desee trazar.
1. Habilite **Incluir límites superior/inferior de confianza**.
1. Seleccione **Generar** para calcular **Alza**, **Confianza** y **Tasa de conversión** por variante para la métrica seleccionada.

![Panel de experimentación con selectores de experimento, variante de control y métrica](assets/experimentation-selection.png)

Consulte la [documentación del panel Experimentación](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation) para obtener más información sobre cómo se calculan estas métricas.

![Resultados de experimentación que muestran el alza, la confianza y la tasa de conversión por variante](assets/experimentation.png)

### Analizar en CJA (opcional) {#analyze-in-cja}

Una vez que se carga un informe, aparece el botón **Analizar en CJA** en la parte superior derecha de la pestaña Informe. Al seleccionarlo, se abre el mismo informe a página completa en Customer Journey Analytics, en una nueva pestaña del explorador, en la que tiene el conjunto de herramientas completo de CJA para un análisis más profundo y específico.

![Informe de información general de marcas abierto en el espacio de trabajo de Customer Journey Analytics](assets/cja-workspace.png)

>[!IMPORTANT]
>
>El informe se abre como un proyecto temporal no guardado. Si lo personaliza en CJA (agrega métricas, cambia paneles, ajusta filtros, etc.) y desea conservar esos cambios, guárdelo con **Proyecto > Guardar como plantilla**. De lo contrario, las ediciones se perderán al cerrar el informe.

![Menú de proyecto con Guardar como plantilla resaltada](assets/save-as-template.png)

## Configuración de informes con Customer Journey Analytics {#setup}

Los informes requieren un conjunto de datos de Customer Journey Analytics conectado a la aplicación Flags. Póngase en contacto con el servicio de asistencia técnica de Marcas o con su representante de Adobe para habilitar la creación de informes para su aplicación.

>[!NOTE]
>
>La identidad pasada en la solicitud de funcionalidad no necesita estar vinculada a un perfil. La evaluación se produce durante el tiempo de ejecución y el evento se envía a Customer Journey Analytics.

## Consulte también {#see-also}

* [Creación de la primera marca de funcionalidad](create-your-first-feature-flag.md)
* [Pruebas A/B con indicadores de funcionalidades](a-b-testing.md)
* [Creación de un grupo de funciones](create-a-feature-group.md)

<!-- -->
