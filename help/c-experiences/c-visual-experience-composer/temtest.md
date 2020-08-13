---
keywords: template testing;template;same experience on similar pages;template test
description: Si utiliza una plantilla de página para aportar estructura a sus páginas o si las páginas contienen elementos similares, esta característica permite probar variaciones en elementos de página de estructura similar.
title: Incluir la misma experiencia en páginas similares
feature: experiences
uuid: 055b276e-2492-40d8-b48e-849dffa93f35
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 96%

---


# Incluir la misma experiencia en páginas similares{#include-the-same-experience-on-similar-pages}

Si utiliza una plantilla de página para aportar estructura a sus páginas o si las páginas contienen elementos similares, esta característica permite probar variaciones en elementos de página de estructura similar.

Para que esta característica funcione correctamente, debe usarse en páginas que tengan una estructura muy similar. O contener elementos de plantilla con la misma estructura en todas las páginas.

>[!IMPORTANT]
>
>Si se utiliza esta función para cambiar elementos en páginas que no sean similares, es muy probable que se produzcan resultados inesperados.

Por ejemplo, puede utilizar esta característica para una de las operaciones siguientes:

* Probar una barra de navegación global reorganizando o quitando elementos.
* Quitar un elemento de todas las páginas de productos que usen una plantilla de página en particular.
* Añadir un banner a todas las páginas de productos.
* Cambiar el diseño de la plantilla de artículo.

El siguiente vídeo de demostración incluye información sobre el uso de plantillas:

Puede especificar páginas que incluyan los elementos modificados o aplicar los cambios a todo el sitio.

1. Cree una actividad como se describe en [Actividades](../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).
1. Para especificar las páginas en las que aparecerá la experiencia, vaya al Compositor de experiencias visuales, haga clic en el icono con forma de engranaje y, a continuación, seleccione **[!UICONTROL Publicación de página]**.
1. Haga clic en **[!UICONTROL Agregar plantilla de regla]** y, a continuación, especifique los criterios para las páginas en las que quiera agregar la experiencia.

1. Especifique el intervalo de páginas. El intervalo de páginas puede ser uno de los siguientes:

   * Dirección URL (Para obtener más información sobre cómo evalúa Destinatario las direcciones URL, consulte Preguntas más frecuentes sobre [Destinatarios y audiencias](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)).
   * Dominio
   * Ruta
   * Fragmento hash (#) (segmente la parte de una dirección URL que sigue al símbolo #)
   * Consulta
   * Parámetro

1. Seleccione un operador.

   El operador especifica cómo se relacionan los elementos que hay a continuación del operador con el intervalo de páginas. Los operadores disponibles son:

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
   >Cuando varios elementos usan la lógica `OR`, significa que cualquier elemento de la lista hace que la condición sea verdadera.

1. Si lo desea, escriba otros criterios adicionales haciendo clic en **[!UICONTROL Agregar plantilla de regla]** y repitiendo el procedimiento del paso anterior.

   Cuando hay varios criterios se unen entre sí con la lógica AND. Adobe Target agrega la experiencia a todas las páginas que cumplan todos los criterios especificados.

>[!IMPORTANT]
>
> Target no puede comprobar las páginas para garantizar que se muestran correctamente, por lo que siempre que se utiliza esta función es recomendable probar las páginas afectadas antes de hacerlas públicas.

## Vídeo de formación: Compositor de experiencias visuales (2 de 2) (7:29) ![Insignia de tutorial](/help/assets/tutorial.png)

* Cambiar el nombre de una experiencia y duplicarla
* Crear una experiencia de redirección
* Segmentar una actividad en una sola dirección URL o un grupo de direcciones URL
* Crear una actividad de varias páginas
* Obtener una vista previa y generar experiencia para sitios web adaptables
* Usar superposiciones para destacar tipos de elementos

>[!VIDEO](https://video.tv.adobe.com/v/17401)