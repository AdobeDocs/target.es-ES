---
keywords: client care;cname;programa de certificados;nombre canónico;cookies;certificado;amc;adobe managed certificate;digicert;validación de control de dominio;dcv
description: Trabaje con Adobe Client Care para implementar la compatibilidad con CNAME (Nombre canónico) en Adobe [!DNL Target] para manejar los problemas de bloqueo de anuncios o las políticas de cookies relacionadas con ITP.
title: ¿Cómo utilizo CNAME en Target?
feature: Privacidad y seguridad
role: Developer
exl-id: bf533771-6d46-48ba-964c-3ad9ce9f7352
source-git-commit: c78598da8f13f1e2c4489a317ce151779ca4be61
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 2%

---

# CNAME y Target

Instrucciones para trabajar con [!DNL Adobe] ClientCare para implementar la compatibilidad con CNAME (Nombre canónico) en [!DNL Adobe Target]. Utilice CNAME para gestionar problemas de bloqueo de anuncios o directivas de cookies relacionadas con ITP (prevención inteligente del seguimiento). Con CNAME, las llamadas se realizan a un dominio propiedad del cliente en lugar de a un dominio propiedad de [!DNL Adobe].

## Solicitar compatibilidad con CNAME en Target

1. Determine la lista de nombres de host que necesita para su certificado SSL (consulte las preguntas frecuentes a continuación).

1. Para cada nombre de host, cree un registro CNAME en su DNS que apunte a su [!DNL Target] nombre de host `clientcode.tt.omtrdc.net` normal.

   Por ejemplo, si el código de cliente es &quot;cnamecustomer&quot; y el nombre de host propuesto es `target.example.com`, el registro CNAME DNS tiene un aspecto similar a:

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!IMPORTANT]
   >
   >La autoridad de certificación de Adobe, DigiCert, no puede emitir un certificado hasta que se complete este paso. Por lo tanto, [!DNL Adobe] no puede cumplir su solicitud de implementación de CNAME hasta que este paso se complete.

1. [Complete este ](/help/assets/FPC_Request_Form.xlsx) formulario e inclúyalo cuando  [abra un ticket de Adobe Client Care solicitando asistencia](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) CNAME:

   * Código de cliente [!DNL Target] de Adobe:
   * Nombres de host de certificados SSL (ejemplo: `target.example.com target.example.org`):
   * Comprador de certificados SSL (se recomienda encarecidamente el Adobe, consulte Preguntas frecuentes): Adobe/cliente
   * Si el cliente compra el certificado, también conocido como &quot;Traer su propio certificado&quot; (BYOC), rellene estos detalles adicionales:
      * Organización de certificados (ejemplo: Empresa de Ejemplo S.A.):
      * Unidad organizativa del certificado (opcional, ejemplo: Marketing):
      * País del certificado (ejemplo: EE. UU.):
      * Estado o región del certificado (ejemplo: California):
      * Ciudad del certificado (ejemplo: San José):

1. Si [!DNL Adobe] está comprando el certificado, [!DNL Adobe] trabaja con DigiCert para adquirir e implementar el certificado en los servidores de producción de Adobe.

   Si el cliente compra el certificado (BYOC), [!DNL Adobe] Client Care le envía la solicitud de firma de certificado (CSR). Utilice la CSR al adquirir el certificado a través de la autoridad de certificación que elija. Una vez emitido el certificado, envíe una copia del certificado y los certificados intermedios a [!DNL Adobe] Client Care para su implementación.

   [!DNL Adobe] ClientCare le notifica cuando la implementación está lista.

1. Actualice `serverDomain` al nuevo CNAME en at.js.

## Preguntas frecuentes

La siguiente información responde a las preguntas más frecuentes sobre la solicitud e implementación del soporte de CNAME en [!DNL Target]:

### ¿Puedo proporcionar mi propio certificado (Traer su propio certificado o BYOC)?

Puede proporcionar su propio certificado. Sin embargo, [!DNL Adobe] no recomienda esta práctica. La administración del ciclo de vida del certificado SSL es más fácil tanto para [!DNL Adobe] como para usted si [!DNL Adobe] compra y controla el certificado. Los certificados SSL deben renovarse cada año. Por lo tanto, [!DNL Adobe] ClientCare debe ponerse en contacto con usted cada año para obtener un nuevo certificado de forma oportuna. Algunos clientes pueden tener dificultades para producir un certificado renovado de forma oportuna. Su implementación [!DNL Target] se ve en peligro cuando el certificado caduca porque los navegadores rechazan las conexiones.

>[!IMPORTANT]
>
>Si solicita una implementación de CNAME de [!DNL Target] traer su propio certificado, usted es responsable de proporcionar certificados renovados a [!DNL Adobe] Client Care cada año. Si se permite que el certificado CNAME caduque antes de que [!DNL Adobe] pueda implementar un certificado renovado, se interrumpirá la implementación específica de [!DNL Target].

### ¿Cuánto tiempo falta para que caduque mi nuevo certificado SSL?

Los certificados emitidos antes del 1 de septiembre de 2020 son certificados de dos años. Los certificados emitidos el 1 de septiembre de 2020 o después de esa fecha son certificados de un año.

### ¿Qué nombres de host debo elegir? ¿Cuántos nombres de host debo elegir por dominio?

[!DNL Target] Las implementaciones CNAME requieren solo un nombre de host por dominio en el certificado SSL y en el DNS del cliente. Adobe recomienda un nombre de host. Algunos clientes requieren más nombres de host por dominio para sus propios fines (prueba en el entorno de ensayo, por ejemplo), que se admite.

La mayoría de los clientes eligen un nombre de host como `target.example.com`. Adobe recomienda seguir esta práctica, pero la elección es en última instancia tuya. No solicite un nombre de host de un registro DNS existente. Al hacerlo, se genera un conflicto y se retrasa el tiempo de resolución de la solicitud de CNAME [!DNL Target].

### Ya tengo una implementación CNAME para [!DNL Adobe Analytics], ¿podemos usar el mismo certificado o nombre de host?

No, [!DNL Target] requiere un nombre de host y un certificado independientes.

### ¿Mi implementación actual de [!DNL Target] se ve afectada por ITP 2.x?

En un navegador Safari, vaya hasta el sitio web en el que tenga una biblioteca JavaScript de [!DNL Target]. Si ve una cookie [!DNL Target] configurada en el contexto de un CNAME como `analytics.company.com`, ITP 2.x no le afectará.

Los problemas de ITP se pueden resolver para [!DNL Target] con un [!DNL Analytics] CNAME. Necesita un CNAME [!DNL Target] independiente solo en escenarios de bloqueo de anuncios donde [!DNL Target] está bloqueado.

Para obtener más información sobre ITP, consulte [Prevención inteligente del seguimiento de Apple (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

### ¿Qué tipo de interrupciones del servicio puedo esperar cuando se implementa mi implementación CNAME?

No hay interrupciones en el servicio cuando se implementa el certificado (incluidas las renovaciones de certificados).

Sin embargo, después de cambiar el nombre de host del código de implementación [!DNL Target] (`serverDomain` en at.js) por el nuevo nombre de host CNAME (`target.example.com`), los exploradores web tratan a los visitantes que regresan como nuevos visitantes. Se pierden los datos de perfil de los visitantes que regresan porque no se puede acceder a la cookie anterior bajo el nombre de host antiguo (`clientcode.tt.omtrdc.net`). La cookie anterior es inaccesible debido a los modelos de seguridad del explorador. Esta interrupción solo ocurre en el corte inicial del nuevo CNAME. Las renovaciones de certificados no tienen el mismo efecto porque el nombre de host no cambia.

### ¿Qué tipo de clave y algoritmo de firma de certificado se usan para mi implementación CNAME?

Todos los certificados son RSA SHA-256 y las claves son RSA de 2048 bits, de forma predeterminada. Actualmente no se admiten los tamaños de claves superiores a 2048 bits.

### ¿Cómo puedo validar que mi implementación CNAME esté lista para el tráfico?

Utilice el siguiente conjunto de comandos (en el terminal de línea de comandos macOS o Linux, usando bash y curl 7.49+):

1. Pegue esta función bash en el terminal:

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{31,32,{34..38}}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. Pegue este comando (reemplazando `target.example.com` por su nombre de host):

   ```
   validateEdgeFpsslSni target.example.com
   ```

   Si la implementación está lista, verá los resultados como se muestra a continuación. La parte importante es que todas las líneas incluyen `CN=target.example.com`, que coincide con el nombre de host deseado. Si alguna línea incluye `CN=*.tt.omtrdc.net`, la implementación está **no** lista.

   ```
   $ validateEdgeFpsslSni target.example.com
   mboxedge31.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge32.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge34.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge35.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge36.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge37.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge38.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   ```

1. Valide el nuevo CNAME DNS con otra solicitud curl, que también debería mostrar `CN=target.example.com`:

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >Si este comando falla pero el comando `validateEdgeFpsslSni` se ejecuta correctamente, espere a que las actualizaciones DNS se propaguen completamente. Los registros DNS tienen un [TTL (tiempo de vida)](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) asociado que dicta el tiempo de caducidad de la caché para las respuestas DNS de esos registros. Como resultado, es posible que tenga que esperar al menos mientras los TTL sean. Puede utilizar el comando `dig target.example.com` o [el Cuadro de herramientas de G Suite](https://toolbox.googleapps.com/apps/dig/#CNAME) para buscar los TTL específicos.

### ¿Cómo utilizo un vínculo de no participación con CNAME?

Si utiliza CNAME, el vínculo de no participación debe contener el parámetro &quot;client=`clientcode`, por ejemplo:
`https://my.cname.domain/optout?client=clientcode`.

Reemplace `clientcode` por su código de cliente y, a continuación, añada el texto o la imagen que se vinculará a la [URL de exclusión](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#reference_E7A62B7B99C94B3A806CB262D16E27FC).

## Limitaciones conocidas

* El modo de control de calidad no es persistente cuando tiene CNAME y at.js 1.x porque se basa en una cookie de terceros. La solución es añadir los parámetros de vista previa a cada URL a la que navegue. El modo de control de calidad es persistente cuando tiene CNAME y at.js 2.x.
* Actualmente, la configuración `overrideMboxEdgeServer` no funciona correctamente con CNAME al usar versiones de at.js anteriores a at.js 1.8.2 y at.js 2.3.1. Si utiliza una versión anterior de at.js, esta configuración debe establecerse como `false` para evitar solicitudes fallidas. Alternativamente, debería considerar la posibilidad de [actualizar at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) a una versión más reciente y compatible.
* Al utilizar CNAME, es más probable que aumente el tamaño del encabezado de la cookie para las llamadas [!DNL Target] . [!DNL Adobe] recomienda mantener el tamaño de la cookie por debajo de 8 KB.
