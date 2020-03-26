---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notas de la versión que proporcionan información sobre funciones, mejoras y correcciones para las últimas o futuras versiones de Destinatario de DNL.
title: Notas de la versión de evaluación de Adobe Destinatario
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: ba4c776d93f911c122f36113a99ce4349b3c5524

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

En estas notas de la versión se proporciona información acerca de las funciones, las mejoras, las correcciones y los problemas conocidos de las últimas o de las próximas versiones de [!DNL Adobe Target].

**Última actualización: 25 de marzo de 2020**

>[!NOTE]
>
>* Este artículo contiene información de evaluación. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso. Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma o diferir, según la hora de las versiones.
   >
   >
* Los números entre paréntesis son para uso interno de [!DNL Adobe].
   >
   >
* **Cambios** de compatibilidad con TLS: A partir del 1 de marzo de 2020, Destinatario desactivará la compatibilidad con el cifrado TLS 1.1 y TLS 1.0. Seguridad de capa de transporte (TLS) es el protocolo de seguridad más implementado que se usa hoy en día para navegadores web y otras aplicaciones que requieren que los datos se intercambien de forma segura en una red. Este cambio es necesario para cumplir el estándar de cumplimiento de seguridad generalmente aceptado de TLS 1.2 o superior. Compruebe qué versión de TLS está utilizando actualmente. Si su versión es menor que 1.2, implemente los cambios requeridos antes del 1 de marzo de 2020 para seguir usando Destinatario como se espera.
   >
   >   
   Para obtener información detallada sobre el posible impacto y los pasos que debe seguir para actualizar la implementación, consulte Cambios [](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)de codificación TLS (Transport Layer Security).
   >
   >
* **Desaprobación** de mbox.js: El 30 de agosto de 2020, Adobe Destinatario dejará de ser compatible con la biblioteca mbox.js. Después del 30 de agosto de 2020, todas las llamadas realizadas desde mbox.js producirán errores e impactarán en las páginas que tengan actividades de Destinatario en ejecución. Recomendamos que todos los clientes migren a la versión más reciente de la biblioteca at.js antes de esta fecha para evitar problemas potenciales con sus sitios. For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md).
   >
   >   
   Aunque actualmente se admite mbox.js, no hemos proporcionado actualizaciones de funciones a esta biblioteca desde julio de 2017. La versión más reciente de at.js ofrece muchas ventajas con respecto a mbox.js. Entre otras ventajas, at.js mejora los tiempos de carga de página para implementaciones web, mejora la seguridad y proporciona mejores opciones de implementación para aplicaciones de una sola página.
   >
   >   
   Al trasladar a todos los clientes a at.js, nuestros ingenieros y el personal de asistencia técnica podrán proporcionarle nuevas funciones y oferta de la asistencia técnica que espera de Adobe.


## Destinatario at.js (25 de marzo de 2020)

Están disponibles las siguientes versiones nuevas de las bibliotecas JavaScript de Destinatario at.js:

* Versión 2.3.0 de at.js
* Versión 1.8.1 de at.js

For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

## Target Standard/Premium 20.2.1 (23 de marzo de 2020). 

>[!IMPORTANT]
>
>Consulte la información anterior sobre la desaprobación de mbox.js.

Esta versión contiene las siguientes mejoras, correcciones y cambios:

* Se ha corregido un problema que impedía a los clientes seleccionar una colección al realizar una búsqueda en el catálogo. (TGT-36230)
* Se corrigió un problema en el cual un criterio creado mediante API, pero al que no hace referencia una actividad creada en la interfaz de usuario de Destinatario, podía eliminarse erróneamente de la interfaz de usuario. (TGT-35917)
* Se han implementado mejoras de seguridad en la directiva de seguridad de contenido (CSP). (TGT-36190)
* Se ha corregido un problema que hacía que se mostrara &quot;NaN%&quot; al desplazar la barra de porcentaje Ponderación de atributo al extremo izquierdo. (TGT-36211)
* Se han resuelto problemas de localización para que el texto de la interfaz de usuario en varios idiomas se muestre correctamente.
* Hemos estandarizado la lista de las métricas disponibles de las actividades de Adobe Analytics para Destinatario (A4T) al dejar de utilizar las métricas de Adobe Analytics no admitidas en la versión actual de las API de Adobe Analytics. Esto nos permitirá ampliar nuestra compatibilidad con A4T en futuras versiones de Adobe Destinatario.

   Se han realizado los siguientes cambios:

   * &quot;Tiempo promedio empleado en la página&quot; se ha sustituido por &quot;Tiempo promedio invertido en el sitio&quot;. Todas las actividades que usen esto como métrica en la métrica Objetivo principal tendrán &quot;Tiempo promedio invertido en el sitio&quot; (nota: medida en minutos en lugar de segundos) seleccionada como métrica de objetivo principal la próxima vez que se edite la actividad.
   * &quot;Visitantes&quot; se ha sustituido por &quot;Visitantes únicos&quot;. Cualquier actividad que utilice esta métrica como métrica de objetivo principal tendrá &quot;Visitantes únicos&quot; seleccionados como métrica de objetivo principal la próxima vez que se edite la actividad.

* Las siguientes métricas han quedado obsoletas y ya no se pueden seleccionar como métrica de objetivo principal al crear una nueva actividad de A4T.

   | Métricas obsoletas | Métricas de reemplazo sugeridas |
   |--- |--- |
   | Visitantes diarios, Visitantes por hora, Visitantes mensuales, Visitantes trimestrales, Visitantes semanales, Visitantes anuales | Visitantes únicos |
   | Profundidad promedio de la visita | n/a. No sugerida como métrica de objetivo principal |
   | Bots | n/a. No sugerida como métrica de objetivo principal |
   | Tasa de bloqueo móvil, Longitud promedio de sesión anterior móvil, Clasificación promedio de la tienda de aplicaciones móviles, Tasa de bloqueo del rendimiento de la aplicación móvil, Puntuación promedio de la tienda de aplicaciones móviles | n/a. No sugerida como métrica de objetivo principal |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
