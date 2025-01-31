---
keywords: probar plantillas;plantilla;misma experiencia en páginas similares;prueba de plantilla
description: Aprenda a utilizar el  [!DNL Target] Compositor de experiencias visuales (VEC) de Adobe para incluir la misma experiencia en varias páginas que tienen una estructura similar o que contienen los mismos elementos de .
title: ¿Puedo incluir la misma experiencia en páginas similares?
feature: Experiences and Offers
hide: true
hidefromtoc: true
source-git-commit: f968ec45f015fa0b195007f5790b9efb743c8b65
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 24%

---

# Incluir la misma experiencia en páginas similares

Use una plantilla de página en [!DNL Adobe Target] para dar estructura a las páginas, o si las páginas contienen elementos similares, para probar variaciones en elementos de página de estructura similar o en todo el dominio.

Para funcionar correctamente, esta función debe utilizarse en páginas que tengan una estructura similar o que contengan elementos de plantilla que estén estructurados igual en todas las páginas.

>[!IMPORTANT]
>
>El uso de esta función para cambiar elementos en páginas que no son similares probablemente cause resultados inesperados.

Por ejemplo, puede utilizar esta característica para una de las operaciones siguientes:

* Probar una barra de navegación global reorganizando o quitando elementos.
* Quitar un elemento de todas las páginas de productos que usen una plantilla de página en particular.
* Añadir un banner a todas las páginas de productos.
* Cambiar el diseño de la plantilla de artículo

Puede especificar páginas que incluyan los elementos modificados o aplicar los cambios a todo el sitio o dominio.

1. Cree o edite una actividad como se describe en [Actividades](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. Para especificar las páginas donde aparece la experiencia, en el [!UICONTROL Visual Experience Composer] (VEC), haga clic en el icono [!UICONTROL Configure] ( ![Configurar icono](/help/main/assets/icons/Setting.svg) ) y, a continuación, seleccione **[!UICONTROL Page Delivery]**.

1. Haga clic en **[!UICONTROL Add Rule]** y, a continuación, especifique los criterios para las páginas en las que quiera agregar la experiencia.

1. Especifique el intervalo de páginas. El intervalo de páginas puede ser uno de los siguientes:

   * [!UICONTROL URL] (para obtener más información sobre cómo evalúa [!DNL Target] las direcciones URL, consulte [Preguntas más frecuentes sobre objetivos y audiencias](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)).
   * [!UICONTROL Domain]
   * [!UICONTROL Path]
   * [!UICONTROL Hash (#) Fragment] (segmentar la parte de una dirección URL que sigue al símbolo #).
   * [!UICONTROL Query]
   * [!UICONTROL Custom]

1. Seleccione un operador.

   El operador especifica cómo se relacionan los elementos que hay a continuación del operador con el intervalo de páginas. Los operadores disponibles incluyen:

   * [!UICONTROL Contains]
   * [!UICONTROL Does not contain]
   * [!UICONTROL Is (case sensitive)]
   * [!UICONTROL Is not]
   * [!UICONTROL Starts with]
   * [!UICONTROL Ends with]

1. Escriba las cadenas que establecen dónde se agregará la experiencia, como el dominio o las cadenas contenidas en el nombre de la página.

   Por ejemplo, si selecciona **[!UICONTROL Domain]** y **[!UICONTROL Is (case sensitive)]**, escriba el dominio en el que desea que se agregue la experiencia a todas las páginas.

   Puede incluir varios elementos.

   >[!IMPORTANT]
   >
   >Cuando varios elementos utilizan la lógica OR, lo que significa que cualquier elemento de la lista hace que la condición sea verdadera.

1. Si lo desea, escriba otros criterios adicionales haciendo clic en **[!UICONTROL Add Rule]** y repitiendo el procedimiento de los pasos anteriores.

   Cuando hay varios criterios se unen entre sí con la lógica AND. [!DNL Target] agrega la experiencia a todas las páginas que cumplan los criterios especificados.

>[!IMPORTANT]
>
> [!DNL Target] no puede comprobar las páginas para asegurarse de que se muestran según lo esperado, por lo que siempre que se utiliza esta característica es recomendable probar las páginas afectadas antes de hacerlas públicas.

## Casos de uso

Revise los siguientes casos de uso para ver las formas de utilizar las reglas de plantilla en su sitio:

### Procesar la misma actividad en todo el dominio

Puede considerar la posibilidad de utilizar reglas de plantilla para procesar la misma actividad en todo el dominio en los siguientes casos de uso:

* Para incluir un encabezado o pie de página global
* Para incluir un banner global (por ejemplo, anuncios de COVID-19)
* Para incluir una promoción de envío gratuito global

1. Cree o edite una actividad como se describe en [Actividades](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. Para especificar el dominio donde aparece la experiencia, en [!UICONTROL Visual Experience Composer] haga clic en el icono [!UICONTROL Configure] ( ![Configurar icono](/help/main/assets/icons/Setting.svg) ) y, a continuación, seleccione **[!UICONTROL Page Delivery]**.

1. Haga clic en **[!UICONTROL Add Rule]** > **[!UICONTROL Domain]**.

1. En la lista desplegable **[!UICONTROL Choose evaluator]**, seleccione **[!UICONTROL Contains]** y luego especifique el dominio.
