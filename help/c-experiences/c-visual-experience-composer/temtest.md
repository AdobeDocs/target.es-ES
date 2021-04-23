---
keywords: probar plantillas;plantilla;misma experiencia en páginas similares;prueba de plantilla
description: Aprenda a utilizar el Adobe [!DNL Target] Compositor de experiencias visuales (VEC) para incluir la misma experiencia en varias páginas con una estructura similar o que contienen los mismos elementos de plantilla.
title: ¿Puedo incluir la misma experiencia en páginas similares?
feature: Experiencias y ofertas
exl-id: 4ea95794-496c-4eff-96ec-8a9d1f732c4a
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 45%

---

# Incluir la misma experiencia en páginas similares

Utilice una plantilla de página en [!DNL Adobe Target] para proporcionar estructura a las páginas, o si las páginas contienen elementos similares, para probar variaciones en elementos de página de estructura similar o en todo el dominio.

Para funcionar correctamente, esta función debe usarse en páginas que tengan una estructura similar o que contengan elementos de plantilla que estén estructurados igual en todas las páginas.

>[!IMPORTANT]
>
>Si se utiliza esta función para cambiar elementos en páginas que no sean similares, es muy probable que se produzcan resultados inesperados.

Por ejemplo, puede utilizar esta característica para una de las operaciones siguientes:

* Probar una barra de navegación global reorganizando o quitando elementos.
* Quitar un elemento de todas las páginas de productos que usen una plantilla de página en particular.
* Añadir un banner a todas las páginas de productos.
* Cambiar el diseño de la plantilla de artículo.

Puede especificar páginas que incluyan los elementos modificados o aplicar el cambio a su sitio o dominio.

1. Cree o edite una actividad como se describe en [Actividades](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. Para especificar las páginas en las que aparecerá la experiencia, en el [!UICONTROL Compositor de experiencias visuales] (VEC), haga clic en el icono del engranaje y, a continuación, seleccione **[!UICONTROL Entrega de páginas]**.

   ![Icono de engranaje > Entrega de páginas](/help/c-experiences/c-visual-experience-composer/assets/icon-gear.png)

1. Haga clic en **[!UICONTROL Agregar plantilla de regla]** y, a continuación, especifique los criterios para las páginas en las que quiera agregar la experiencia.

1. Especifique el intervalo de páginas. El intervalo de páginas puede ser uno de los siguientes:

   * Dirección URL (Para obtener más información sobre cómo Target evalúa las direcciones URL, consulte [Preguntas frecuentes sobre audiencias y segmentación](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)).
   * Dominio
   * Ruta
   * Fragmento hash (#) (dirija la parte de una URL que sigue al símbolo #)
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
   >Cuando varios elementos usan la lógica OR , significa que cualquier elemento de la lista hace que la condición sea verdadera.

1. Si lo desea, escriba otros criterios adicionales haciendo clic en **[!UICONTROL Agregar regla de plantilla]** y repitiendo el procedimiento de los pasos anteriores.

   Cuando hay varios criterios se unen entre sí con la lógica AND. [!DNL Target] agrega la experiencia a todas las páginas que cumplan todos los criterios especificados.

>[!IMPORTANT]
>
> [!DNL Target] no puede comprobar las páginas para garantizar que se muestran correctamente, por lo que siempre que se utiliza esta función es recomendable probar las páginas afectadas antes de hacerlas públicas.

## Casos de uso

Revise los siguientes casos de uso para saber cómo usar las reglas de plantilla en el sitio:

### Representar la misma actividad en todo el dominio

Puede considerar la posibilidad de utilizar reglas de plantilla para representar la misma actividad en todo el dominio para los siguientes casos de uso:

* Incluir un encabezado o pie de página global
* Para incluir un banner global (por ejemplo, anuncios COVID-19)
* Para incluir una promoción de envío libre global

1. Cree o edite una actividad como se describe en [Actividades](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. Para especificar el dominio en el que aparecerá la experiencia, en el Compositor de experiencias visuales, haga clic en el icono de engranaje y, a continuación, seleccione **[!UICONTROL Entrega de páginas]**.

1. Haga clic en **[!UICONTROL Agregar regla de plantilla]** > **[!UICONTROL Dominio]**.

1. En la lista desplegable **[!UICONTROL Elija evaluador]**, seleccione **[!UICONTROL Contiene]** y, a continuación, especifique el dominio.

   ![El dominio contiene](/help/c-experiences/c-visual-experience-composer/assets/domain-template-rule.png)

## Vídeo de formación: Compositor de experiencias visuales (2 de 2) (7:29) ![Distintivo tutorial](/help/assets/tutorial.png)

* Cambiar el nombre de una experiencia y duplicarla
* Crear una experiencia de redirección
* Segmentar una actividad en una sola dirección URL o un grupo de direcciones URL
* Crear una actividad de varias páginas
* Obtener una vista previa y generar experiencia para sitios web adaptables
* Usar superposiciones para destacar tipos de elementos

>[!VIDEO](https://video.tv.adobe.com/v/17401)
