---
keywords: probar plantillas;plantilla;misma experiencia en páginas similares;prueba de plantilla
description: Aprenda a utilizar el  [!DNL Target] Compositor de experiencias visuales (VEC) de Adobe para incluir la misma experiencia en varias páginas que tienen una estructura similar o que contienen los mismos elementos de .
title: ¿Puedo incluir la misma experiencia en páginas similares?
feature: Experiences and Offers
exl-id: 4ea95794-496c-4eff-96ec-8a9d1f732c4a
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 33%

---

# Incluir la misma experiencia en páginas similares

Use una plantilla de página en [!DNL Adobe Target] para dar estructura a las páginas, o si las páginas contienen elementos similares, para probar variaciones en elementos de página de estructura similar o en todo el dominio.

Para funcionar correctamente, esta función debe utilizarse en páginas que tengan una estructura similar o que contengan elementos de plantilla que estén estructurados igual en todas las páginas.

>[!IMPORTANT]
>
>Si se utiliza esta función para cambiar elementos en páginas que no sean similares, es muy probable que se produzcan resultados inesperados.

Por ejemplo, puede utilizar esta característica para una de las operaciones siguientes:

* Probar una barra de navegación global reorganizando o quitando elementos.
* Quitar un elemento de todas las páginas de productos que usen una plantilla de página en particular.
* Añadir un banner a todas las páginas de productos.
* Cambiar el diseño de la plantilla de artículo.

Puede especificar páginas que incluyan los elementos modificados o aplicar los cambios a todo el sitio o dominio.

1. Cree o edite una actividad como se describe en [Actividades](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. Para especificar las páginas donde aparecerá la experiencia, en el [!UICONTROL Visual Experience Composer] (VEC), haga clic en el icono con forma de engranaje y, a continuación, seleccione **[!UICONTROL Page Delivery]**.

   ![Icono de engranaje > Entrega de página](/help/main/c-experiences/c-visual-experience-composer/assets/icon-gear.png)

1. Haga clic en **[!UICONTROL Add Template Rule]** y, a continuación, especifique los criterios para las páginas en las que quiera agregar la experiencia.

1. Especifique el intervalo de páginas. El intervalo de páginas puede ser uno de los siguientes:

   * URL (para obtener más información sobre cómo Target evalúa las URL, consulte [Preguntas frecuentes sobre objetivos y audiencias](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)).
   * Dominio
   * Ruta
   * Fragmento almohadilla (#) (se dirige a la parte de una dirección URL que sigue al símbolo #).
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

   Por ejemplo, si selecciona **[!UICONTROL Domain]** y **[!UICONTROL Is (case sensitive)]**, escriba el dominio en el que desea que se agregue la experiencia a todas las páginas.

   Puede incluir varios elementos.

   >[!IMPORTANT]
   >
   >Cuando varios elementos utilizan la lógica OR, lo que significa que cualquier elemento de la lista hace que la condición sea verdadera.

1. Si lo desea, escriba otros criterios adicionales haciendo clic en **[!UICONTROL Add Template Rule]** y repitiendo el procedimiento de los pasos anteriores.

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

1. Para especificar el dominio donde aparecerá la experiencia, vaya al Compositor de experiencias visuales, haga clic en el icono con forma de engranaje y, a continuación, seleccione **[!UICONTROL Page Delivery]**.

1. Haga clic en **[!UICONTROL Add Template Rule]** > **[!UICONTROL Domain]**.

1. En la lista desplegable **[!UICONTROL Choose evaluator]**, seleccione **[!UICONTROL Contains]** y luego especifique el dominio.

   ![El dominio contiene](/help/main/c-experiences/c-visual-experience-composer/assets/domain-template-rule.png)

## Vídeo de formación: Compositor de experiencias visuales (2 de 2) (7:29) ![Distintivo de tutorial](/help/main/assets/tutorial.png)

* Cambiar el nombre de una experiencia y duplicarla
* Crear una experiencia de redirección
* Segmentar una actividad en una sola dirección URL o un grupo de direcciones URL
* Crear una actividad de varias páginas
* Obtener una vista previa y generar experiencia para sitios web adaptables
* Usar superposiciones para destacar tipos de elementos

>[!VIDEO](https://video.tv.adobe.com/v/17401)
