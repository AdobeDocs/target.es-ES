---
description: Se requieren varios pasos a la hora de implementar Adobe Analytics como fuente de informes para Target (A4T).
keywords: A4T;Adobe Analytics;actividad basada en Analytics;grupo de informes de Analytics;grupo de informes;integración de Analytics Target;configurar grupo de informes
seo-description: Se requieren varios pasos a la hora de implementar Adobe Analytics como fuente de informes para Target (A4T).
seo-title: Implementación de Analytics for Target
solution: Target
title: Implementación de Analytics for Target
topic: Premium
uuid: da6498c8-1549-4c36-ae42-38c731a28f08
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Implementación de Analytics for Target{#analytics-for-target-implementation}

Se requieren varios pasos a la hora de implementar Adobe Analytics como fuente de informes para Target (A4T).

## Pasos de la implementación {#section_73961BAD5BB4430A95E073DE5C026277}

En la tabla siguiente se describen los pasos necesarios para implementar esta integración en un sitio.

## Paso 1: Solicitar el aprovisionamiento para Analytics y Target

Después de implementar Analytics como fuente de informes para Target, debe aprovisionar para Analytics y Target. [Rellene este formulario para solicitar el aprovisionamiento](http://www.adobe.com/go/audiences).

## Paso 2: Configurar los permisos de usuario

Deben cumplirse los requisitos de cuenta de usuario para poder crear en Adobe Target una actividad basada en Adobe Analytics. Consulte [Requisitos de permisos de usuario](/help/c-integrating-target-with-mac/a4t/account-reqs.md).

## Paso 3: Implementar el servicio ID de visitante de Experience Cloud

El servicio de ID de visitante permite identificar a usuarios en todas las soluciones de Experience Cloud. Debe implementar o migrar a la versión requerida del ID de visitante de Experience Cloud. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Consulte [Implementación del servicio de Experience Cloud ID para Target](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-target.html) en la documentación del servicio ID de visitante de Experience Cloud.

## Paso 4: Actualizar AppMeasurement para JavaScript o s_code

Debe implementar o migrar a la versión requerida de appMeasurement.js. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Para nuevas implementaciones, consulte [Implementación de JavaScript para Analytics](https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html).

Para realizar una migración, consulte [Migración a AppMeasurement para JavaScript](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=appmeasure_mjs_migrate).

## Paso 5: Descargar y actualizar at.js o mbox.js

Debe implementar o migrar a la versión requerida de at.js o mbox.js con su cuenta de producción. No es necesario modificar el código.

Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/c-integrating-target-with-mac/a4t/before-implement.md).

## Paso 6: Host at.js o mbox.js

Si ha implementado anteriormente at.js o mbox.js, puede reemplazar el archivo existente con la versión actualizada. Para obtener más información, consulte “Requisitos de implementación” en [Antes de la implementación](/help/c-integrating-target-with-mac/a4t/before-implement.md).

En caso contrario, el archivo se puede alojar junto con los archivos del servicio ID de visitante y de AppMeasurement for JavaScript. Estos archivos deben alojarse en un servidor web al que se pueda acceder desde todas las páginas del sitio. En el paso siguiente necesitará la ruta de acceso a estos archivos.

## Paso 7: Agregar la referencia de at.js o mbox.js a todas las páginas del sitio

Incluya at.js o mbox.js debajo de VisitorAPI.js agregando la línea de código siguiente en la <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> etiqueta de cada página:

Para at.js:

```
<script language="JavaScript" type="text/javascript" 
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

Para mbox.js:

```
<script language="JavaScript" type="text/javascript" 
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/mbox.js"></script>
```

Es esencial que VisitorAPI.js se cargue antes que at.js o mbox.js; por ello, si va a actualizar un archivo at.js o mbox.js existente, compruebe el orden de carga.

## Paso 8: Validar la implementación

Cargue sus páginas después de haber actualizado las bibliotecas de JavaScript para confirmar que los valores del parámetro mboxMCSDID en las llamadas de Target coinciden con el valor del parámetro sdid en la llamada de vista de página de Analytics.

Es especialmente importante confirmar esto en las aplicaciones de una sola página (SPA), donde el orden de las llamadas no siempre es predecible.

**Nota:** Es necesario que estos valores coincidan para que A4T funcione correctamente.

## Paso 9 (opcional): Eliminar el código de integración anterior

Recomendamos quitar la integración anterior para simplificar la implementación y que no resulte necesario resolver discrepancias entre los sistemas. Puede eliminar cualquier código que haya implementado para una integración anterior de SC a T&amp;T, como `mboxLoadSCPlugin`.

## Paso 10: Habilitar las opciones para usar Analytics como fuente de informes para Target

En Target, haga clic en [!UICONTROL Configuración &gt; Preferencias] y elija [!UICONTROL Seleccionar por actividad] o [!UICONTROL Adobe Analytics] para habilitar las opciones.

* La opción Seleccionar por actividad permite elegir entre Target y Analytics a la hora de crear cada actividad.
* La opción Adobe Analytics establece Analytics como fuente de informes para todas las actividades que cree.

