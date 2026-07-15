---
title: Informes
description: Obtenga información sobre cómo ver los informes de indicadores de funcionalidades en Marcas con Customer Journey Analytics.
hide: true
exl-id: edddca99-f263-461b-a16f-b46ee7c15f6c
source-git-commit: 35fa45d2a5374dcc47a02bb737f28f24847d7fc6
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 1%

---

# Creación de informes {#reporting}

Marcas entrega informes a través de **Customer Journey Analytics (CJA)**. No hay ninguna ficha Resultados o Informes en la consola; en su lugar, un botón **Informe** en cada indicador o grupo de características abre un tablero de CJA con ámbito para ese elemento.

## Requisitos previos {#prerequisites}

Antes de poder ver los informes, asegúrese de lo siguiente:

1. Los informes están configurados para su aplicación. Consulte [Configurar los informes con Customer Journey Analytics](#setup).
1. El indicador o grupo de características está activo y tiene datos acumulados.

## Ver un informe {#view-report}

Para abrir un informe para un indicador de características o un grupo de características:

1. Vaya a la marca de características o al grupo de características en la consola.
1. Seleccionar **informe**.

Se abre un panel de Customer Journey Analytics con ámbito que muestra los datos de ese indicador o grupo de características. El tablero incluye:

* **Participantes**: número total de usuarios aptos para la función (variante + grupo de control combinados)
* **Grupo de control**: número de usuarios asignados al grupo de control (usuarios que recibieron la experiencia predeterminada)
* **Desglose de variante**: recuento acumulado de usuarios inscritos en cada variante y el grupo de control
* **Inscripción diaria**: gráficos de nivel de día que muestran la inscripción en cada variante y el grupo de control a lo largo del tiempo

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
