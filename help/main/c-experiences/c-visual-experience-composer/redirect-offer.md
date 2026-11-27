---
keywords: redirigir;redirigir url;enviar a otra página
description: Aprenda a utilizar la opción Redirigir a URL en Adobe [!DNL Target] cuando desee enviar al visitante a una página diferente en lugar de mostrar contenido en la misma página.
title: ¿Puedo redirigir una página a una dirección URL diferente?
feature: Visual Experience Composer (VEC)
exl-id: bd448482-0079-4689-aa24-65ecbb31b8ae
TQID: 'https://experienceleague.adobe.com/8Bh5z7SRWw3QqKQMHZck01GKVBtMufwLbw9JxLsSACU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 2%
---
# Redireccionar a una dirección URL {#redirect-to-url}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a usar la opción **[!UICONTROL Redirigir a URL]** para enviar visitantes a una página diferente en lugar de mostrar contenido en la misma página.

>[!ENDSHADEBOX]

La opción **[!UICONTROL Redirigir a la dirección URL]** de [!DNL Adobe Target] envía a un visitante a una página diferente en lugar de mostrar contenido en la misma página. Se adapta a la comparación de dos páginas completamente diferentes, a diferencia de los cambios en fragmentos de contenido dentro de una página. A continuación, una prueba A/B compara la página A con la página B: una experiencia apunta a la página A predeterminada y la otra redirige a la página B.

Una oferta de redireccionamiento ejecuta código JavaScript que redirige el explorador. El código utiliza el método `window.location.replace();`, de modo que la página desde la que se redirige al visitante no se almacena en el historial del explorador. Por lo tanto, el visitante puede seguir utilizando el botón Atrás del explorador.

## Creación de una oferta de redireccionamiento {#create-redirect-offer}

La experiencia que redirige define la página a la que se envían los visitantes y, opcionalmente, las condiciones de dicha redirección.

1. Cree una experiencia.

1. En el fotograma **[!UICONTROL Experiencias]**, haga clic en el icono **[!UICONTROL Más acciones]** ( ![Más acciones](/help/main/assets/icons/MoreSmallList.svg) ) de la experiencia que redirecciona.

1. Haga clic en **[!UICONTROL Redirigir a la dirección URL]**.

   ![Icono de más acciones](assets/redirect_1.png)

1. En el cuadro de diálogo **[!UICONTROL Redirigir a la dirección URL]**, escriba la dirección URL de la página B.

   ![Icono de más acciones](assets/redirect_2.png)

1. (Opcional) Seleccione la opción para incluir los parámetros de consulta actuales.

   Cuando se selecciona esta opción, todo lo que hay después de `?` en la dirección URL del visitante se anexa a la dirección URL de redireccionamiento en el momento de la redirección.

## Limitaciones

Las ofertas de redireccionamiento tienen las siguientes limitaciones:

* **A4T:** una oferta de redireccionamiento en una actividad que usa A4T requiere una implementación que cumple ciertos requisitos mínimos y se aplica otra información importante. Ver [ofertas de redireccionamiento: preguntas más frecuentes sobre A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md).
* **Compositor de experiencias basadas en formularios:** no use una oferta de redireccionamiento en mboxes que formen parte de la página. Use una oferta de redireccionamiento solamente desde una etiqueta de script que forme parte de HTML `<head>`, y use siempre la creación automática y establezca la oferta de redireccionamiento para el mbox global.

>[!NOTE]
>
>Para pasar el valor de referente de la página de aterrizaje, utilice una oferta de HTML en lugar de una oferta de redireccionamiento.

## Problemas conocidos

Las actividades de redireccionamiento en implementaciones at.js pueden hacer que la dirección URL de vista previa entre en bucle y que la oferta se entregue repetidamente. Use [Modo de control de calidad](/help/main/c-activities/c-activity-qa/activity-qa.md) para previsualizar y probar la actividad. Este problema no afecta a la entrega real de la oferta. (TGT-23019)
