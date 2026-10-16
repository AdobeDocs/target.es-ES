---
keywords: compositor de experiencias visuales;vec;wysiwyg
description: Aprenda los conceptos básicos del uso del Compositor de experiencias visuales (VEC) en Adobe Target. El VEC es un editor de WYSIWYG que permite crear fácilmente experiencias personalizadas.
title: ¿Cómo utilizo el Compositor de experiencias visuales (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: 51650f2a-1f24-40c7-8692-77f55656b4f6
TQID: 'https://experienceleague.adobe.com/X4nfYuOtD3TVusnVIIEZhXwUdCZ-dMvbZeJlrkmI9Hs'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 140a7287246905d47bf02a84348627017a619386
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 0%
---
# [!UICONTROL Compositor de experiencias visuales] (VEC)

El [!UICONTROL Compositor de experiencias visuales] (VEC) en [!DNL Adobe Target] es un editor de WYSIWYG para crear y probar experiencias personalizadas directamente en sitios web y páginas web móviles sin editar código.

Cree experiencias y ofertas para actividades [!DNL Target] arrastrando y soltando elementos, intercambiando contenido y cambiando diseños de página. El compositor también proporciona opciones para editar HTML y JavaScript.

## Requisitos del explorador {#browser-requirements}

[!DNL Safari] es compatible con la interfaz [!DNL Adobe Target]. Puede crear actividades basadas en formularios en [!DNL Safari] y utilizar todas las funciones, excepto el VEC y el [!UICONTROL Compositor de experiencias mejorado] (EEC). Si abre el Compositor de experiencias visuales en [!DNL Safari], una superposición le indicará que cambie a [!DNL Google Chrome] para editar experiencias.

Los exploradores como [!DNL Firefox] pueden bloquear las páginas que contienen contenido mixto, como una página no segura dentro de un sitio seguro, y evitar que se muestren en el VEC. Si una página no se muestra, haga clic en el icono situado junto a la dirección URL en la barra de direcciones del explorador y, a continuación, haga clic en **[!UICONTROL Deshabilitar la protección en esta página]**. Este problema no afecta a cómo se muestran las páginas a los visitantes del sitio.

## Abra el VEC. {#open-the-vec}

Para establecer la página que se abre de forma predeterminada en el VEC, escriba una URL predeterminada de [!UICONTROL Compositor de experiencias visuales] en la pestaña [!DNL Target] **[!UICONTROL Administración]** > **[!UICONTROL Compositor de experiencias visuales]**.

Si no establece una dirección URL predeterminada, el VEC se abre con una página en blanco en la que puede especificar una dirección URL.

![VEC resaltado](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

## Editar experiencias {#edit-experiences}

### Ver y nombrar experiencias {#view-and-name-experiences}

Utilice las pestañas del carril [!UICONTROL Experiencias] para ver cómo se muestra la página a diferentes audiencias o con diferentes experiencias. Asigne a cada experiencia un nombre descriptivo para facilitar la identificación en la lista.

Por ejemplo, al probar la posición del vínculo a la página de inicio en la barra de navegación, asigne a la experiencia el nombre &quot;Vínculo a Inicio primero&quot; que aparece.

![Cambiar el nombre de una experiencia en el carril de Experiencias](/help/main/c-experiences/c-visual-experience-composer/assets/rename_exp.png)

### Selección y modificación de elementos {#select-and-modify-elements}

Mueva el cursor sobre la página para resaltar elementos individuales con un cuadro contextual.

Haga clic en un elemento resaltado para mostrar las opciones de edición para ese tipo de elemento. Por ejemplo, seleccione una imagen y haga clic en **[!UICONTROL Cambiar origen de la imagen]** para reemplazarla o seleccione un botón para cambiar el color del texto.

![Opciones de edición para un elemento seleccionado](/help/main/c-experiences/c-visual-experience-composer/assets/properties-exp.png)

No se puede editar el contenido de dentro de un iframe incrustado en la página. Para editar ese contenido, asegúrese de que el documento del iframe esté habilitado para [!DNL Target] y luego cargue la dirección URL del iframe directamente en el VEC.

Los cambios en la estructura de la página fuera del VEC pueden afectar a las ubicaciones utilizadas por una actividad. Si esas ubicaciones cambian, es posible que [!DNL Target] no encuentre los elementos que ha modificado, lo que puede causar problemas al editar experiencias.

### Examinar y diseñar {#browse-and-design}

Haz clic en **[!UICONTROL Examinar]** para navegar a una página accesible desde la página actual, como una página de envío o un carro de compras, y prueba los cambios allí.

![Modo de exploración en el VEC](/help/main/c-experiences/c-visual-experience-composer/assets/browse_exp.png)

En el modo Examinar, también puede acceder a los elementos que aparecen al pasar el ratón por encima, como los menús flotantes y los minicarros. Cuando llegue a la página o al elemento que desea editar, haga clic en **[!UICONTROL Diseño]** para editar la experiencia.

Si un estado de movimiento del cursor por encima depende de JavaScript, asegúrate de que **[!UICONTROL Deshabilitar JavaScript]** no esté seleccionado. JavaScript debe estar habilitado para poder editar los elementos que dependen de él.

Para obtener más información acerca de las opciones de edición disponibles, consulte [Opciones del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81).

## Administrar carga de página {#manage-page-loading}

Algunas opciones de edición permanecen disponibles mientras se carga una página o después de que no se haya cargado. También puede cancelar la carga de la página para acceder a estas opciones sin esperar.

### Edición de una página mientras se carga o después de que la página no se haya cargado {#loading}

Puede realizar algunos cambios antes de que una página termine de cargarse en el VEC o después de que no se cargue, por ejemplo, porque el código personalizado ya no funciona.

Utilice las opciones de edición disponibles para lo siguiente:

* Realice cambios sencillos, como añadir código personalizado o cambiar el nombre de una experiencia
* Copie el código personalizado existente de una página que ya no sea accesible
* Realice ediciones sencillas en una página que no se puede cargar en el VEC

Las opciones [!UICONTROL Experiences], [!UICONTROL Components] y [!UICONTROL Configure] siguen estando accesibles mientras la página se carga o después de que no se cargue.

### Cancelación de la carga de una página dentro del VEC {#cancel-loading}

Cancele la carga de la página en el VEC para editar la actividad sin esperar a que termine de cargarse la página.

Cancelar la carga de una página resulta útil cuando necesita:

* Realice pequeñas ediciones en las modificaciones existentes
* Eliminar una o más modificaciones existentes
* Inserción o edición de código personalizado
* Corrija una URL de página introducida incorrectamente
* Habilitar o deshabilitar JavaScript antes de cargar la página en el VEC
* Agregar reglas de prueba de plantilla a los criterios [!UICONTROL Entrega de página]
* Omitir la opción global [!UICONTROL Compositor de experiencias mejorado] (EEC) al cargar una página a través de EEC o en modo de solo iframe

Después de cancelar la carga de la página, puede cambiar entre experiencias en la actividad sin esperar a que se cargue la página. Haga clic en **[!UICONTROL Recargar]** para volver a mostrar la página en el VEC.

>[!IMPORTANT]
>
>Si edita el código personalizado o realiza otras modificaciones después de cancelar la carga de la página, realice pruebas de control de calidad (QA) para comprobar que los cambios se entregan según lo esperado.

Para detener la carga de la página, haga clic en **[!UICONTROL Cancelar carga]** mientras se carga la página. La página permanece descargada para esta actividad durante la sesión de edición actual a menos que la vuelva a cargar.

Haga clic en **[!UICONTROL Recargar]** para reanudar la administración de experiencias en la actividad actual o agregar nuevas modificaciones.
