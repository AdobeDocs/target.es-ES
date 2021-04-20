---
keywords: atención al cliente;cname;programa de certificado;nombre canónico;cookies;certificado;amc;certificado administrado por adobe;digicert;validación de control de dominio;dcv
description: Trabaje con Adobe Client Care para implementar la compatibilidad con CNAME (Nombre canónico) en Adobe Target para tratar problemas de bloqueo de anuncios o políticas de cookies relacionadas con ITP.
title: ¿Cómo se usa CNAME en el Destinatario?
feature: Privacy & Security
role: Developer
translation-type: tm+mt
source-git-commit: 69677b9d384d9817a39386fc1388a4aa42121713
workflow-type: tm+mt
source-wordcount: '1163'
ht-degree: 2%

---


# CNAME y Adobe Target

Instrucciones para trabajar con [!DNL Adobe] Client Care para implementar la compatibilidad con CNAME (Nombre canónico) en [!DNL Adobe Target]. Utilice CNAME para gestionar problemas de bloqueo de anuncios o directivas de cookies relacionadas con ITP (Intelligent Tracking Prevention). Con CNAME, las llamadas se realizan a un dominio propiedad del cliente en lugar de a un dominio propiedad de [!DNL Adobe].

## Solicitud de compatibilidad con CNAME en Destinatario

1. Determine la lista de nombres de host que necesita para su certificado SSL (consulte las preguntas más frecuentes más adelante).

1. Para cada nombre de host, cree un registro CNAME en el DNS que apunte a su nombre de host [!DNL Target] `clientcode.tt.omtrdc.net` habitual.

   Por ejemplo, si el código de cliente es &quot;cnamecustomer&quot; y el nombre de host propuesto es `target.example.com`, el registro CNAME DNS tiene un aspecto similar al siguiente:

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!IMPORTANT]
   >
   >La autoridad de certificación de Adobe, DigiCert, no puede emitir un certificado hasta que se complete este paso. Por lo tanto, [!DNL Adobe] no puede completar la solicitud de implementación de CNAME hasta que se complete este paso.

1. [Rellene este ](https://experienceleague.adobe.com/docs/core-services/assets/FPC_Request_Form.xlsx?lang=en) formulario e inclúyalo cuando  [abra un ticket de Adobe Client Care para solicitar asistencia](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) CNAME:

   * Código de cliente de Adobe [!DNL Target]:
   * Nombres de host de certificados SSL (ejemplo: `target.example.com target.example.org`):
   * Comprador de certificados SSL (se recomienda encarecidamente el Adobe, consulte Preguntas más frecuentes): Adobe/cliente
   * Si el cliente compra el certificado, también conocido como &quot;Trae tu propio certificado&quot; (BYOC), rellene estos detalles adicionales:
      * Organización de certificados (ejemplo: Ejemplo de Compañía Inc):
      * Unidad organizativa de certificados (opcional, ejemplo: Marketing):
      * País del certificado (ejemplo: EE.UU.):
      * Estado o región del certificado (ejemplo: California):
      * Ciudad del certificado (ejemplo: San José):

1. Si [!DNL Adobe] está comprando el certificado, [!DNL Adobe] trabaja con DigiCert para comprar e implementar el certificado en los servidores de producción de Adobe.

   Si el cliente compra el certificado (BYOC), [!DNL Adobe] Client Care le envía la solicitud de firma del certificado (CSR). Utilice el CSR cuando compre el certificado a través de la autoridad de certificación elegida. Una vez emitido el certificado, envíe una copia del certificado y los certificados intermedios a [!DNL Adobe] Client Care para su implementación.

   [!DNL Adobe] ClientCare le notifica cuando la implementación está lista.

1. Actualice el `serverDomain` al nuevo CNAME en at.js.

## Preguntas frecuentes

La siguiente información responde a las preguntas más frecuentes sobre la solicitud e implementación de soporte de CNAME en [!DNL Target]:

### ¿Puedo proporcionar mi propio certificado (Traer su propio certificado o BYOC)?

Puede proporcionar su propio certificado. Sin embargo, [!DNL Adobe] no recomienda esta práctica. La administración del ciclo vital del certificado SSL es más fácil para [!DNL Adobe] y para usted si [!DNL Adobe] compra y controla el certificado. Los certificados SSL deben renovarse cada año. Por lo tanto, [!DNL Adobe] Client Care debe ponerse en contacto con usted cada año para obtener un nuevo certificado de manera oportuna. Algunos clientes pueden tener dificultades para producir un certificado renovado de manera oportuna. Su implementación [!DNL Target] se ve en peligro cuando caduca el certificado porque los exploradores rechazan las conexiones.

>[!IMPORTANT]
>
>Si solicita una implementación de [!DNL Target] traer su propio certificado CNAME, es responsable de proporcionar certificados renovados a [!DNL Adobe] Client Care cada año. Permitir que el certificado CNAME caduque antes de que [!DNL Adobe] pueda implementar un certificado renovado provoca una interrupción de la implementación específica [!DNL Target].

### ¿Cuánto tiempo falta para que caduque mi nuevo certificado SSL?

Los certificados expedidos antes del 1 de septiembre de 2020 son certificados de dos años. Los certificados expedidos a partir del 1 de septiembre de 2020 son certificados de un año. Puede leer más sobre el paso a los certificados de un año [aquí](https://www.digicert.com/position-on-1-year-certificates).

### ¿Qué nombres de host debo elegir? ¿Cuántos nombres de host debo elegir por dominio?

[!DNL Target] Las implementaciones de CNAME solo requieren un nombre de host por dominio en el certificado SSL y en el DNS del cliente. Adobe recomienda un nombre de host. Algunos clientes requieren más nombres de host por dominio para sus propios fines (por ejemplo, prueba en ensayo), lo cual es compatible.

La mayoría de los clientes eligen un nombre de host como `target.example.com`. Adobe recomienda seguir esta práctica, pero la elección es en última instancia tuya. No solicite un nombre de host de un registro DNS existente. Al hacerlo, se produce un conflicto y se retrasa el tiempo de resolución de la solicitud [!DNL Target] CNAME.

### Ya tengo una implementación CNAME para [!DNL Adobe Analytics], ¿podemos usar el mismo certificado o nombre de host?

No, [!DNL Target] requiere un nombre de host y un certificado independientes.

### ¿La implementación actual del Destinatario se ve afectada por ITP 2.x?

En un navegador Safari, vaya hasta el sitio web en el que tenga una biblioteca JavaScript de [!DNL Target]. Si ve una cookie [!DNL Target] configurada en el contexto de un CNAME, como `analytics.company.com`, ITP 2.x no le afecta.

Los problemas de ITP se pueden resolver para [!DNL Target] con sólo un [!DNL Analytics] CNAME. Solo necesita un CNAME [!DNL Target] independiente en los escenarios de bloqueo de publicidad donde [!DNL Target] esté bloqueado.

Para obtener más información sobre ITP, consulte [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

### ¿Qué tipo de interrupciones del servicio puedo esperar cuando se implementa mi implementación CNAME?

No hay interrupción del servicio cuando se implementa el certificado (incluidas las renovaciones de certificados).

Sin embargo, después de cambiar el nombre de host en el código de implementación [!DNL Target] (`serverDomain` en at.js) por el nuevo nombre de host CNAME (`target.example.com`), los exploradores Web consideran los visitantes que regresan como nuevos visitantes. Se pierden los datos de perfil de los visitantes que se devuelven porque la cookie anterior no está accesible bajo el nombre de host antiguo (`clientcode.tt.omtrdc.net`). La cookie anterior no es accesible debido a los modelos de seguridad del explorador. Esta interrupción se produce únicamente en el corte inicial del nuevo CNAME. Las renovaciones de certificados no tienen el mismo efecto porque el nombre de host no cambia.

### ¿Qué tipo de clave y algoritmo de firma de certificado se utiliza para mi implementación CNAME?

Todos los certificados son RSA SHA-256 y las claves son RSA de 2048 bits, de manera predeterminada. Actualmente no se admiten tamaños de claves mayores de 2048 bits.

### ¿Cómo puedo validar que la implementación de CNAME esté lista para el tráfico?

Utilice el siguiente conjunto de comandos (en el terminal de la línea de comandos macOS o Linux, utilizando bash y curl 7.49+):

1. Pegue esta función bash en su terminal:

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

   Si la implementación está lista, verá el resultado como se muestra a continuación. La parte importante es que todas las líneas incluyen `CN=target.example.com`, que coincide con el nombre de host deseado. Si alguna línea incluye `CN=*.tt.omtrdc.net`, la implementación está **no** lista.

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

1. Valide el nuevo CNAME DNS con otra solicitud de curl, que también debería mostrar `CN=target.example.com`:

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >Si este comando falla pero el comando `validateEdgeFpsslSni` se ejecuta correctamente, espere a que las actualizaciones DNS se propaguen por completo. Los registros DNS tienen un [TTL (tiempo de vida)](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) asociado que dicta el tiempo de caducidad de la caché para las respuestas DNS de esos registros. Como resultado, es posible que tenga que esperar al menos tanto tiempo como los TTL. Puede utilizar el comando `dig target.example.com` o [el cuadro de herramientas de G Suite](https://toolbox.googleapps.com/apps/dig/#CNAME) para buscar los TTL específicos.

## Limitaciones conocidas

* El modo de control de calidad no es fijo cuando tiene CNAME y at.js 1.x porque se basa en una cookie de terceros. La solución consiste en agregar los parámetros de previsualización a cada dirección URL a la que navegue. El modo de control de calidad es persistente cuando tiene CNAME y at.js 2.x.
* Actualmente, la configuración `overrideMboxEdgeServer` no funciona correctamente con CNAME cuando se utilizan versiones de at.js anteriores a at.js 1.8.2 y at.js 2.3.1. Si utiliza una versión anterior de at.js, esta configuración debe establecerse como `false` para evitar que se produzcan errores en las solicitudes. Como alternativa, debería considerar la posibilidad de [actualizar at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) a una versión más reciente y admitida.
* Al utilizar CNAME, es más probable que aumente el tamaño del encabezado de la cookie para [!DNL Target] llamadas. [!DNL Adobe] recomienda mantener el tamaño de la cookie por debajo de 8 KB.
