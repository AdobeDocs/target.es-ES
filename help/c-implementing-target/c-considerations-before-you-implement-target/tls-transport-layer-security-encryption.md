---
keywords: tls;tls 1.0;seguridad de capa de transporte;cifrado;tls 1.1;tls 1.2
description: Descubra cómo [!DNL Target] utiliza el protocolo TLS (Transport Layer Security) para mantener los estándares de seguridad más altos y promover la seguridad de los datos de clientes.
title: ¿Cómo utiliza  [!DNL Target] TLS para proporcionar seguridad?
feature: Privacidad y seguridad
role: Developer
exl-id: 964a642a-830a-4556-a92a-d300670cd2fa
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '1237'
ht-degree: 59%

---

# Cambios en el cifrado de TLS (Seguridad de capa de transporte)

Información sobre cambios en la forma en que [!DNL Adobe] y [!DNL Adobe Target] usan TLS (Seguridad de capa de transporte) para mantener los estándares de seguridad más altos y promover la seguridad de los datos de los clientes.

Seguridad de capa de transporte (TLS) es el protocolo de seguridad más implementado que se usa hoy en día para navegadores web y otras aplicaciones que requieren que los datos se intercambien de forma segura en una red. Adobe tiene estándares de cumplimiento de seguridad que requieren la discontinuación de protocolos más viejos y exigen el uso de TLS 1.2 para tener en uso la versión más actualizada y segura.

>[!IMPORTANT]
>
>A partir del 1 de marzo de 2020, Adobe Target dejará de ser compatible con el cifrado TLS 1.1 para el Compositor de experiencias visuales (VEC), el Compositor de experiencias mejorado (EEC), el envío de actividades, las API, etc. Actualice a TLS 1.2 antes del 1 de marzo de 2020 para evitar problemas.

No esperamos que esto tenga un impacto significativo en los datos de los clientes ni en los informes.

## Compositor de experiencias visuales (VEC) con Compositor de experiencias mejorado (EEC) habilitado {#section_B374B62DEC3344C194AC7BECC2EE0AA0}

TLS 1.2 es el valor predeterminado a partir del 1 de marzo de 2020 y TLS 1.1 ya no será compatible.

Adobe realizará la migración de sus clientes por etapas a TLS 1.2. Para aquellos cuyos dominios ya cumplan con 1.2, los pasaremos a TLS 1.2 sin que usted tenga que hacer ningún cambio. La mayoría de los dominios de los clientes ya admiten TLS 1.2; sin embargo, si su dominio no es compatible con TLS 1.2, conservaremos esos dominios en TLS 1.1 como hoy (hasta marzo de 2020).

No debería tener ningún problema durante esta fase de migración. Si el VEC ha dejado de cargar un sitio que antes funcionaba,   [abra un ticket de Client Care](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) citando esta migración como causa posible.

Sin embargo, si es uno de los clientes que están en TSL 1.1 sin admitir TLS 1.2, debería planificar el movimiento de sus dominios/infraestructura a TLS 1.2. Seguiremos admitiendo el protocolo TLS 1.1 hasta el 1 de marzo de 2020. A partir del 1 de marzo de 2020, Target no admitirá el protocolo TLS 1.1 que se utilizará para el VEC a través de la capacidad del Compositor de experiencias mejorado.

Aunque recomendamos encarecidamente que todos estén en TLS 1.2 de ahora en adelante, si usted es un nuevo cliente, pero *NO* admite TLS 1.2, póngase en contacto con el Servicio de atención al cliente para informarles de que necesita estar en TLS 1.1 para el Compositor de experiencias mejorado. Sin embargo, planifique pasar a TLS 1.2, ya que la compatibilidad con TLS 1.2 no estará disponible a partir del 1 de marzo de 2020.

## Entrega de actividades {#section_46CA5943E4354B259014C2BF340AECD6}

A partir del 1 de marzo de 2020, los servidores de Target dejarán de ser compatibles con TLS 1.1. Este cambio significa que los servidores de Target ya no aceptarán solicitudes de visitantes que utilicen dispositivos antiguos o navegadores web incompatibles con TLS 1.2 (o versiones posteriores). Como resultado, los dispositivos y navegadores más antiguos y que solo admitan TLS 1.1 (o que admitan TLS 1.1 de forma predeterminada) no recibirán de Adobe Target contenido de actividades. Se mostrará el contenido predeterminado del sitio.

Algunos de los dispositivos y navegadores antiguos que se verán afectados son:

* Google Chrome (Chrome para Android) versiones 29 y anteriores
* Opera Browser (Opera Mobile) versiones 12.17 y anteriores
* Mozilla Firefox (Firefox para Mobile) versiones 26 y anteriores
* Android 4.3 y versiones anteriores
* Internet Explorer 8-10 en Windows 7 y versiones anteriores
* Internet Explorer 10 en Windows Phone 8.0
* Safari 6.0.4/OS X10.8.4 y versiones anteriores

Mientras planifica este cambio, considere lo siguiente (tenga en cuenta que el plazo del 1 de marzo de 2020 afecta a todos estos elementos):

* Debe asegurarse de que el sitio predeterminado esté listo en una manera que sea utilizable para dispositivos y navegadores que cumplan los requisitos.
* Tenga presente que el número de visitantes de sus informes de Target puede experimentar una caída insignificante en el número de visitantes.
* Es posible que tenga que cambiar las audiencias creadas específicamente para dirigirse a dispositivos o navegadores más antiguos que no sean compatibles con TLS 1.2. La entrega a esos dispositivos y navegadores ya no funcionará.

Para conocer más detalles sobre exploradores compatibles y sus versiones, consulte   [Exploradores admitidos](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100).

## API [!DNL Target] de Adobe {#section_88797FA5434049EC89F908853CC76903}

A partir del 1 de marzo de 2020, las API de Target dejarán de ser compatibles con el cifrado TLS 1.1. Los clientes que acceden a la API deben verificar que no se verán afectados.

* Los clientes de API que usen Java 7 con la configuración predeterminada necesitarán modificaciones para ser compatibles con TLS 1.2. Para obtener más información, consulte “[Cambiar la versión del protocolo TLS predeterminado para clientes y extremos activos: de TLS 1.0 a TLS 1.2](https://www.java.com/en/configure_crypto.html)” en el sitio web de Java.
* Los clientes de API que usen Java 8 no deberían tener problemas, ya que la configuración predeterminada es TLS 1.2.
* Los clientes de API que usen otros módulos deben ponerse en contacto con su proveedor para obtener más información acerca de la compatibilidad con TLS 1.2.

## Acceso a las interfaces de soluciones de Experience Cloud {#section_748870ADE77B4CBEB18518DC784E64E5}

Debido a que la interfaz de Target Standard/Premium ya requiere un [explorador web actual](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100), no se esperan problemas. Si no puede conectarse a Target, deberá actualizar el navegador a la última versión.

## Cómo comprobar la versión TLS que utiliza su navegador {#section_44716DA2CEFF492BABD95AE32B1A3FC6}

Para comprobar la versión TLS de su sitio web utilizando Google Chrome:

1. Abra el sitio web afectado en Chrome.
1. En el menú Chrome (los tres elipses verticales), haga clic en Más herramientas > Herramientas para desarrolladores.

   ![Herramientas para desarrolladores Chrome](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-developer-tools.png)

1. Abra la pestaña Seguridad y, a continuación, examine la información de la versión TLS en Conexión:

   ![Detalles de la versión de TLS](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-tls-version.png)

>[!NOTE]
>
>Estas instrucciones están actualizadas a partir de la publicación y están sujetas a cambios. Una búsqueda rápida en Internet debería ayudar en caso de que cambien estas instrucciones.  Otros exploradores tienen pasos similares.

## Comportamiento esperado con exploradores que admiten versiones TLS inferiores a 1.2 {#section_B5DA97A34EF248EB927610A5DA71EF2F}

En esta sección se describe qué esperar con los navegadores compatibles con las versiones TLS anteriores a la 1.2 solo cuando se utiliza una implementación at.js o mbox.js . Para fines de comparación, esta sección también describe qué esperar con los exploradores compatibles con TLS 1.2.

### Puntos finales centrales

| Implementación JavaScript de Target | Detalles |
|--- |--- |
| at.js | Con TLS 1.0 o TLS 1.1 habilitado:<ul><li>Al usar herramientas de desarrollo del navegador, en la pestaña Red, verá “200 OK”. Esto significa que la solicitud ha resultado satisfactoria.</li><li>El usuario ve el mensaje “No se puede conectar de forma segura a esta página”. El mensaje explica que esto puede deberse a que el sitio utiliza configuraciones de seguridad TLS no actualizadas o inseguras.</li><li>No se muestran errores de la consola.</li></ul>Con TLS 1.2 habilitado:<ul><li>archivo at.js descargado.</li></ul> |
| mbox.js | Con TLS 1.0 o TLS 1.1 habilitado:<ul><li>Al usar herramientas de desarrollo del navegador, en la pestaña Red, verá “200 OK”. Esto significa que la solicitud ha resultado satisfactoria.</li><li>El usuario ve el mensaje “No se puede conectar de forma segura a esta página”. El mensaje explica que esto puede deberse a que el sitio utiliza configuraciones de seguridad TLS no actualizadas o inseguras.</li><li>No se muestran errores de la consola.</li></ul>Con TLS 1.2 habilitado:<ul><li>archivo mbox.js descargado.</li></ul> |

### Puntos finales de Edge

| Implementación JavaScript de Target | Detalles |
|--- |--- |
| at.js | Con TLS 1.0 o TLS 1.1 habilitado:<ul><li>Al usar herramientas de desarrollo del navegador, en la pestaña Red, verá “200 OK”. Esto significa que la solicitud ha resultado satisfactoria.</li><li>El usuario ve el mensaje “No se puede conectar de forma segura a esta página”. El mensaje explica que esto puede deberse a que el sitio utiliza configuraciones de seguridad TLS no actualizadas o inseguras.</li><li>No se muestran errores de la consola.</li><li>Se proporciona el contenido predeterminado.</li></ul>Con TLS 1.2 habilitado:<ul><li>Se proporciona el contenido de oferta predeterminado.</li></ul> |
| mbox.js | Con TLS 1.0 o TLS 1.1 habilitado:<ul><li>Al usar herramientas de desarrollo del navegador, en la pestaña Red, verá “200 OK”. Esto significa que la solicitud ha resultado satisfactoria.</li><li>El usuario ve el mensaje “No se puede conectar de forma segura a esta página”. El mensaje explica que esto puede deberse a que el sitio utiliza configuraciones de seguridad TLS no actualizadas o inseguras.</li><li>No se muestran errores de la consola.</li><li>Se proporciona el contenido predeterminado.</li></ul>Con TLS 1.2 habilitado:<ul><li>Se proporciona el contenido de oferta predeterminado</li></ul> |

### Actividad segmentada con audiencia de versión de navegador (Internet Explorer, versiones 6, 7 u 8)

>[!NOTE]
>
>Las audiencias dejan de funcionar.

| Implementación JavaScript de Target | Detalles |
|--- |--- |
| at.js | at.js no es compatible con las versiones anteriores a la 10 de Internet Explorer. |
| mbox.js | Con TLS 1.0 o TLS 1.1 habilitado:<ul><li>Se proporciona el contenido predeterminado.</li><li>No se han iniciado solicitudes de Target.</li><li>No se muestran errores de la consola.</li><li>Al usar herramientas de desarrollo del navegador, en la pestaña Red, verá “200 OK”. Esto significa que la solicitud ha resultado satisfactoria.</li></ul>Con TLS 1.2 habilitado:<ul><li>Se proporciona el contenido de oferta predeterminado.</li></ul> |
