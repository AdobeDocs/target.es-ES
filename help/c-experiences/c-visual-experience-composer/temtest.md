---
keywords: template testing;template;same experience on similar pages;template test
description: Utilice una plantilla de página en Adobe Target para proporcionar estructura a las páginas, o si las páginas contienen elementos similares, para probar las variaciones en elementos de página con una estructura similar.
title: Incluir la misma experiencia en páginas similares con Adobe Target
feature: experiences
uuid: 055b276e-2492-40d8-b48e-849dffa93f35
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 45%

---


# Incluir la misma experiencia en páginas similares

Utilice una plantilla de página en [!DNL Adobe Target] para proporcionar estructura a las páginas, o si las páginas contienen elementos similares, para probar variaciones en elementos de página estructurados de forma similar o en todo el dominio.

Para funcionar correctamente, esta función debe usarse en páginas con una estructura similar o que contengan elementos de plantilla que estén estructurados de la misma manera en todas las páginas.

>[!IMPORTANT]
>
>Si se utiliza esta función para cambiar elementos en páginas que no sean similares, es muy probable que se produzcan resultados inesperados.

Por ejemplo, puede utilizar esta característica para una de las operaciones siguientes:

* Probar una barra de navegación global reorganizando o quitando elementos.
* Quitar un elemento de todas las páginas de productos que usen una plantilla de página en particular.
* Añadir un banner a todas las páginas de productos.
* Cambiar el diseño de la plantilla de artículo.

Puede especificar páginas que incluyan los elementos de cambio o aplicar el cambio en el sitio o dominio.

1. Create  or edit an activity as described in [Activities](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. To specify the pages where the experience will appear, in the [!UICONTROL Visual Experience Composer] (VEC) click the gear icon, then select **[!UICONTROL Page Delivery]**.

   ![Icono de engranaje > Envío de página](/help/c-experiences/c-visual-experience-composer/assets/icon-gear.png)

1. Haga clic en **[!UICONTROL Agregar plantilla de regla]** y, a continuación, especifique los criterios para las páginas en las que quiera agregar la experiencia.

1. Especifique el intervalo de páginas. El intervalo de páginas puede ser uno de los siguientes:

   * Dirección URL (Para obtener más información sobre cómo evalúa Destinatario las direcciones URL, consulte Preguntas más frecuentes sobre [Destinatarios y audiencias](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)).
   * Dominio
   * Ruta
   * Fragmento hash (#) (destinatario la parte de una URL que sigue al símbolo #).
   * Consulta
   * Parámetro

1. Seleccione un operador.

   El operador especifica cómo se relacionan los elementos que hay a continuación del operador con el intervalo de páginas. Los operadores disponibles incluyen:

   * Contiene
   * No contiene
   * Es (con distinción de mayúsculas y minúsculas)
   * No es
   * Comienza con
   * Finaliza con

1. Escriba las cadenas que establecen dónde se agregará la experiencia, como el dominio o las cadenas contenidas en el nombre de la página.

   Por ejemplo, si selecciona **[!UICONTROL Dominio]** y **[!UICONTROL Es (con distinción de mayúsculas y minúsculas)]**, escriba el dominio en el que desea que se agregue la experiencia a todas las páginas.

   Puede incluir varios elementos.

   >[!IMPORTANT]
   >
   >Varios elementos utilizan la lógica OR, lo que significa que cualquier elemento individual de la lista hace que la condición sea verdadera.

1. If desired, enter additional criteria by clicking **[!UICONTROL Add Template Rule]** and repeating the procedure in the previous steps.

   Cuando hay varios criterios se unen entre sí con la lógica AND. [!DNL Target] agrega la experiencia a todas las páginas que cumplan todos los criterios especificados.

>[!IMPORTANT]
>
> [!DNL Target] no puede comprobar las páginas para garantizar que se muestran correctamente, por lo que siempre que se utiliza esta función es recomendable probar las páginas afectadas antes de hacerlas públicas.

## Casos de uso

Revise los siguientes casos de uso para saber cómo utilizar las reglas de plantilla en el sitio:

### Representar la misma actividad en todo el dominio

Puede considerar el uso de reglas de plantilla para representar la misma actividad en todo el dominio en los siguientes casos de uso:

* Para incluir un encabezado o pie de página global
* Para incluir una pancarta global (por ejemplo, anuncios COVID-19)
* Para incluir una promoción de envío libre global

1. Create or edit an activity as described in [Activities](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. To specify the domain where the experience will appear, in the Visual Experience Composer click the gear icon, then select **[!UICONTROL Page Delivery]**.

1. Haga clic en **[!UICONTROL Añadir regla]** de plantilla > **[!UICONTROL Dominio]**.

1. En la lista desplegable **[!UICONTROL Elegir evaluador]** , seleccione **[!UICONTROL Contiene]** y, a continuación, especifique el dominio.

   ![El dominio contiene](/help/c-experiences/c-visual-experience-composer/assets/domain-template-rule.png)

## Training video: Visual Experience Composer (2 of 2) (7:29) ![Tutorial badge](/help/assets/tutorial.png)

* Cambiar el nombre de una experiencia y duplicarla
* Crear una experiencia de redirección
* Segmentar una actividad en una sola dirección URL o un grupo de direcciones URL
* Crear una actividad de varias páginas
* Obtener una vista previa y generar experiencia para sitios web adaptables
* Usar superposiciones para destacar tipos de elementos

>[!VIDEO](https://video.tv.adobe.com/v/17401)