---
description: Información sobre cambios en la forma en que Adobe y Target usan TLS (Seguridad de capa de transporte) para mantener los más altos estándares de seguridad y promover la seguridad de los datos de los clientes.
keywords: tls;tls 1.0;seguridad de la capa de transporte;cifrado
seo-description: Información sobre cambios en la forma en que Adobe y Target usan TLS (Seguridad de capa de transporte) para mantener los más altos estándares de seguridad y promover la seguridad de los datos de los clientes.
seo-title: Cambios en el cifrado de TLS (Seguridad de capa de transporte)
solution: Target
title: Cambios en el cifrado de TLS (Seguridad de capa de transporte)
topic: Standard
uuid: d222b966-ee73-4254-87b7-68099583e0dd
translation-type: tm+mt
source-git-commit: 540f763f649364e8f424c9bed057675603a462d7

---


# Cambios en el cifrado de TLS (Seguridad de capa de transporte){#tls-transport-layer-security-encryption-changes}

Información sobre cambios en la forma en que Adobe y Target usan TLS (Seguridad de capa de transporte) para mantener los más altos estándares de seguridad y promover la seguridad de los datos de los clientes.

Seguridad de capa de transporte (TLS) es el protocolo de seguridad más implementado que se usa hoy en día para navegadores web y otras aplicaciones que requieren que los datos se intercambien de forma segura en una red. [!DNL Adobe] tiene estándares de cumplimiento de seguridad que requieren la discontinuación de protocolos más viejos y exigen el uso de TLS 1.2 para tener en uso la versión más actualizada y segura.

>[!NOTE]
>
>El 20 de febrero de 2019, la infraestructura de Adobe Target se actualizó en las regiones de EMEA, Japón y APAC para dejar de recopilar datos de usuarios finales con dispositivos antiguos o exploradores Web que no admiten TLS 1.1 o posterior. La misma actualización está planificada para la región de Norteamérica para **el 1 de abril de 2019**. Utilizar TLS 1.2 mejora la seguridad. Es importante que avance por los específicos y planifique los cambios con su equipo de TI para lograr una transición suave.

No esperamos que esto tenga un impacto significativo en los datos de los clientes ni en los informes.

## Compositor de experiencias visuales (VEC) con Compositor de experiencias mejorado (EEC) habilitado {#section_B374B62DEC3344C194AC7BECC2EE0AA0}

Hasta ahora, el [Compositor de experiencias mejorado](../../c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) (EEC) de Adobe Target usaba TLS 1.0 de forma predeterminada. A partir de la versión de Target 18.4.1 (25 de abril de 2018), Target pasará a utilizar TLS 1.2 de forma predeterminada.

Adobe realizará la migración de sus clientes por etapas a TLS 1.2. Para aquellos cuyos dominios ya cumplan con 1.2, los pasaremos a TLS 1.2 sin que usted tenga que hacer ningún cambio. La mayoría de los dominios de los clientes ya admiten TLS 1.2. Sin embargo, si su dominio no admite TLS 1.2, conservaremos esos dominios en TLS 1.0 como hoy en día (hasta febrero de 2019).

No debería tener ningún problema durante esta fase de migración. Si el VEC ha dejado de cargar un sitio que antes funcionaba,   [abra un ticket de Client Care](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) citando esta migración como causa posible.

Si, sin embargo, es uno de los clientes que están en TSL 1.0 sin admitir TLS 1.2, debería planificar la migración de sus dominios e infraestructura a TLS 1.2. Seguiremos admitiendo el protocolo TLS 1.0 hasta febrero de 2019. A partir de febrero de 2019, Target no admitirá que el protocolo TLS 1.0 se use para VEC mediante la funcionalidad del Compositor de experiencias mejorado.

Aunque recomendamos encarecidamente que todos estén en TLS 1.2 de ahora en adelante, si usted es un nuevo cliente, pero *NO* admite TLS 1.2, póngase en contacto con el Servicio de atención al cliente para informarles de que necesita estar en TLS 1.0 para el Compositor de experiencias mejorado. Sin embargo, planifique pasar a TLS 1.2, ya que la compatibilidad con TLS 1.0 terminará en febrero de 2019.

## Entrega de actividades   {#section_46CA5943E4354B259014C2BF340AECD6}

A partir de febrero de 2019, los servidores de Target dejarán de ser compatibles con TLS 1.0. Este cambio significa que los servidores de Target ya no aceptarán solicitudes de usuarios finales que utilicen dispositivos antiguos o navegadores web que no sean compatibles con TLS 1.1 o versiones posteriores. Como resultado, los dispositivos y navegadores más antiguos y que solo admitan TLS 1.0 (o que admitan TLS 1.0 de forma predeterminada) no recibirán de Adobe Target contenido de actividades. Se mostrará el contenido predeterminado del sitio.

Algunos de los dispositivos y navegadores antiguos que se verán afectados son:

* Android 4.3 y versiones anteriores
* Internet Explorer 8-10 en Windows 7 y versiones anteriores
* Internet Explorer 10 en Windows Phone 8.0
* Safari 6.0.4/OS X10.8.4 y versiones anteriores

Mientras planifica este cambio, considere lo siguiente (tenga en cuenta que el plazo de febrero de 2019 afecta a todos estos elementos):

* Debe asegurarse de que el sitio predeterminado esté listo en una manera que sea utilizable para dispositivos y navegadores que cumplan los requisitos.
* Tenga presente que el número de visitantes de sus informes de Target puede experimentar una caída insignificante en el número de visitantes.
* Puede que necesite cambiar de audiencia creada específicamente para dirigirse a dispositivos o navegadores antiguos que admiten TLS 1.0 (la entrega a esos dispositivos y navegadores dejará de funcionar).

Para conocer más detalles sobre navegadores compatibles y sus versiones, consulte   [Exploradores admitidos](../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100).

## API de Adobe Target {#section_88797FA5434049EC89F908853CC76903}

A partir de febrero de 2019, Target dejará de admitir el cifrado TLS 1.0. Los clientes que acceden a la API deben verificar que no se verán afectados.

* Los clientes de API que usen Java 7 con la configuración predeterminada necesitarán modificaciones para ser compatibles con TLS 1.2. Para obtener más información, consulte “[Cambiar la versión del protocolo TLS predeterminado para clientes y extremos activos: de TLS 1.0 a TLS 1.2](https://www.java.com/en/configure_crypto.html)” en el sitio web de Java.
* Los clientes de API que usen Java 8 no deberían tener problemas, ya que la configuración predeterminada es TLS 1.2.
* Los clientes de API que usen otros módulos deben ponerse en contacto con su proveedor para obtener más información acerca de la compatibilidad con TLS 1.2.

## Acceso a interfaces de soluciones de Experience Cloud   {#section_748870ADE77B4CBEB18518DC784E64E5}

Debido a que la interfaz de Target Standard/Premium ya requiere un [explorador web actual](../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100), no se esperan problemas. Si no puede conectarse a Target, deberá actualizar el navegador a la última versión.

## Cómo comprobar la versión de TLS que usa el navegador   {#section_44716DA2CEFF492BABD95AE32B1A3FC6}

Para consultar la versión TLS en su sitio web utilizando Firefox (otros navegadores tienen pasos similares):

1. Abra el sitio web afectado en Firefox.
1. Haga clic en el icono **[!UICONTROL Mostrar información del sitio]en la barra de direcciones del navegador.**

   ![](assets/firefox_more_info.png)

1. Haga clic en **[!UICONTROL Mostrar detalles de conexión]** &gt; **[!UICONTROL Más información]**.

   ![](assets/firefox_more_info_2.png)

1. Examine la información de versión TLS en Detalles técnicos:

   ![](assets/firefox_more_info_3.png)

## Comportamiento esperado con los navegadores compatibles con TLS 1.0 solamente   {#section_B5DA97A34EF248EB927610A5DA71EF2F}

En esta sección se describe qué esperar con los navegadores compatibles con TLS 1.0 solo cuando se utiliza una implementación at.js o mbox.js. Para fines de comparación, en esta sección también se describe qué esperar con los navegadores compatibles con TLS 1.1 y 1.2.

### Puntos finales principales

| Implementación JavaScript de Target | Detalles |
|--- |--- |
| at.js | Con TLS 1.0 habilitado:<ul><li>Al usar herramientas de desarrollo del navegador, en la pestaña Red, verá “200 OK”. Esto significa que la solicitud ha resultado satisfactoria.</li><li>El usuario ve el mensaje “No se puede conectar de forma segura a esta página”. El mensaje explica que esto puede deberse a que el sitio utiliza configuraciones de seguridad TLS no actualizadas o inseguras.</li><li>No se muestran errores de la consola.</li></ul>Con TLS 1.1 o 1.2 habilitado:<ul><li>archivo at.js descargado.</li></ul> |
| mbox.js | Con TLS 1.0 habilitado:<ul><li>Al usar herramientas de desarrollo del navegador, en la pestaña Red, verá “200 OK”. Esto significa que la solicitud ha resultado satisfactoria.</li><li>El usuario ve el mensaje “No se puede conectar de forma segura a esta página”. El mensaje explica que esto puede deberse a que el sitio utiliza configuraciones de seguridad TLS no actualizadas o inseguras.</li><li>No se muestran errores de la consola.</li></ul>Con TLS 1.1 o 1.2 habilitado:<ul><li>archivo mbox.js descargado.</li></ul> |

### Puntos finales de Edge

| Implementación JavaScript de Target | Detalles |
|--- |--- |
| at.js | Con TLS 1.0 habilitado:<ul><li>Al usar herramientas de desarrollo del navegador, en la pestaña Red, verá “200 OK”. Esto significa que la solicitud ha resultado satisfactoria.</li><li>El usuario ve el mensaje “No se puede conectar de forma segura a esta página”. El mensaje explica que esto puede deberse a que el sitio utiliza configuraciones de seguridad TLS no actualizadas o inseguras.</li><li>No se muestran errores de la consola.</li><li>Se proporciona el contenido predeterminado.</li></ul>Con TLS 1.1 o 1.2 habilitado:<ul><li>Se proporciona el contenido de oferta predeterminado.</li></ul> |
| mbox.js | Con TLS 1.0 habilitado:<ul><li>Al usar herramientas de desarrollo del navegador, en la pestaña Red, verá “200 OK”. Esto significa que la solicitud ha resultado satisfactoria.</li><li>El usuario ve el mensaje “No se puede conectar de forma segura a esta página”. El mensaje explica que esto puede deberse a que el sitio utiliza configuraciones de seguridad TLS no actualizadas o inseguras.</li><li>No se muestran errores de la consola.</li><li>Se proporciona el contenido predeterminado.</li></ul>Con TLS 1.1 o 1.2 habilitado:<ul><li>Se proporciona el contenido de oferta predeterminado</li></ul> |

### Actividad segmentada con audiencia de versión del navegador (Internet Explorer, versiones 6, 7 u 8)

>[!NOTE]
>
>Las audiencias dejan de funcionar.

| Implementación JavaScript de Target | Detalles |
|--- |--- |
| at.js | at.js no es compatible con las versiones anteriores a la 10 de Internet Explorer. |
| mbox.js | Con TLS 1.0 habilitado:<ul><li>Se proporciona el contenido predeterminado.</li><li>No se han iniciado solicitudes de Target.</li><li>No se muestran errores de la consola.</li><li>Al usar herramientas de desarrollo del navegador, en la pestaña Red, verá “200 OK”. Esto significa que la solicitud ha resultado satisfactoria.</li></ul>Con TLS 1.1 o 1.2 habilitado:<ul><li>Se proporciona el contenido de oferta predeterminado.</li></ul> |