---
keywords: client care;cname;certificate program;canonical name;cookies;certificate;amc;adobe managed certificate;digicert;domain control validation;dcv
description: Información sobre cómo trabajar con Adobe Client Care para implementar el soporte de CNAME (nombre canónico) en Adobe Target.
title: CNAME y Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: 45bd128a01dcb8d4d8d330d8ed4a4df04b98a612
workflow-type: tm+mt
source-wordcount: '1183'
ht-degree: 3%

---


# CNAME y Adobe Target {#cname-and-adobe-target}

Instructions for working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Adobe Target]. Para gestionar mejor los problemas de bloqueo de anuncios o las directivas de cookies relacionadas con ITP, se utiliza un CNAME de modo que las llamadas se realizan a un dominio propiedad del cliente en lugar de a un dominio propiedad de Adobe.

## Solicitar compatibilidad con CNAME

Realice los pasos siguientes para solicitar asistencia de CNAME en [!DNL Target]:

1. Determine la lista de nombres de host que necesita para su certificado SSL (consulte Preguntas más frecuentes).

1. Para cada nombre de host, cree un registro CNAME en el DNS que apunte a su nombre de host normal [!DNL Target] `clientcode.tt.omtrdc.net`.

   Por ejemplo: si el código de cliente es &quot;cnamecustomer&quot; y el nombre de host propuesto es `target.example.com`, el registro CNAME DNS debería tener este aspecto:

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!NOTE]
   >
   >* La autoridad de certificación de Adobe, DigiCert, no puede emitir un certificado hasta que se complete este paso. Por lo tanto, Adobe no puede satisfacer su solicitud de implementación de CNAME hasta que se complete este paso.


1. [Rellene este formulario](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/assets/FPC_Request_Form.xlsx) e inclúyalo cuando [abra un ticket de Adobe Client Care para solicitar asistencia](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)CNAME:

   * Adobe [!DNL Target] client code:
   * Nombres de host de certificados SSL (ejemplo: `target.example.com target.example.org`):
   * Comprador de certificados SSL (se recomienda encarecidamente el Adobe, consulte Preguntas más frecuentes): Adobe/cliente
   * Si el cliente compra el certificado (también conocido como BYOC), rellene estos detalles adicionales:
      * Organización de certificados (ejemplo: Ejemplo de Compañía Inc):
      * Unidad organizativa de certificados (opcional, ejemplo: Marketing):
      * País del certificado (ejemplo: EE.UU.):
      * Estado o región del certificado (ejemplo: California):
      * Ciudad del certificado (ejemplo: San José):

1. Si Adobe compra el certificado, Adobe trabajará con DigiCert para adquirir e implementar el certificado en los servidores de producción de Adobe.

   Si el cliente compra el certificado (BYOC), Adobe Client Care le enviará la solicitud de firma del certificado (CSR), que deberá utilizar al comprar el certificado a través de la autoridad de certificación elegida. Una vez emitido el certificado, debe enviar una copia del certificado y los certificados intermedios a Adobe Client Care para su implementación.

   Adobe Client Care le avisará cuando la implementación esté lista.

1. Después de completar las tareas anteriores y de que Adobe Client Care le haya notificado que la implementación está lista, debe actualizar `serverDomain` al nuevo CNAME en at.js.

## Preguntas frecuentes

La siguiente información responde a las preguntas más frecuentes sobre la solicitud e implementación de la compatibilidad con CNAME en [!DNL Target]:

### ¿Puedo proporcionar mi propio certificado (o BYOC)?

Sí, puede proporcionar su propio certificado; sin embargo, no se recomienda. La administración del ciclo vital del certificado SSL es mucho más fácil tanto para el Adobe como para el usuario cuando el Adobe compra y controla el certificado. Los certificados SSL deben renovarse cada año, lo que significa que Adobe Client Care debe ponerse en contacto con usted cada año para enviar un nuevo certificado a Adobe de manera oportuna. Es posible que algunos clientes tengan dificultades para producir un certificado renovado en forma oportuna cada año, lo que pone en peligro su [!DNL Target] implementación porque los exploradores rechazarán las conexiones cuando caduque el certificado.

>[!IMPORTANT]
>
>Tenga en cuenta que si solicita una implementación [!DNL Target] de CNAME con certificado propio, es responsable de proporcionar certificados renovados a Adobe Client Care cada año. Si se permite que el certificado CNAME caduque antes de que Adobe pueda implementar un certificado renovado, se interrumpirá la implementación específica [!DNL Target] .

### ¿Cuánto tiempo falta para que caduque mi nuevo certificado SSL?

Los certificados expedidos antes del 1 de septiembre de 2020 serán certificados de dos años. Los certificados expedidos el 1 de septiembre de 2020 o después de esa fecha serán certificados de un año. Puede leer más sobre el paso a los certificados de un año [aquí](https://www.digicert.com/position-on-1-year-certificates).

### ¿Qué nombres de host debo elegir? ¿Cuántos nombres de host debo elegir por dominio?

[!DNL Target] Las implementaciones de CNAME solo requieren un nombre de host por dominio en el certificado SSL y en el DNS del cliente, por lo que es lo que recomendamos. Algunos clientes pueden requerir nombres de host adicionales por dominio para sus propios fines (por ejemplo, pruebas en ensayo), lo cual es compatible.

La mayoría de los clientes eligen un nombre de host como `target.example.com`, por lo que es lo que recomendamos, pero la elección es en última instancia tuya. Asegúrese de no solicitar un nombre de host de un registro DNS existente, ya que esto provocaría un conflicto y retrasaría el tiempo de resolución de la solicitud de [!DNL Target] CNAME.

### Ya tengo una implementación CNAME para [!DNL Adobe Analytics], ¿podemos usar el mismo certificado o nombre de host?

No, [!DNL Target] requiere un nombre de host y un certificado independientes.

### ¿La implementación actual del Destinatario se ve afectada por ITP 2.x?

En un navegador Safari, navegue hasta el sitio web en el que tenga una biblioteca JavaScript de Destinatario. If you see a Target cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.x.

Los problemas de ITP se pueden resolver para el Destinatario solo con un CNAME de Analytics. Solo necesitará un CNAME de Destinatario independiente en el caso de escenarios de bloqueo de anuncios en los que se bloquee el Destinatario.

Para obtener más información sobre ITP, consulte [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

### ¿Qué tipo de interrupciones del servicio puedo esperar cuando se implementa mi implementación CNAME?

No hay interrupción del servicio cuando se implementa el certificado (incluidas las renovaciones de certificados). Sin embargo, cuando cambie el nombre de host en el código de [!DNL Target] implementación (`serverDomain` en at.js) por el nuevo nombre de host CNAME (`target.example.com`), los exploradores Web tratarán los visitantes que regresan como nuevos visitantes y se perderán los datos de perfil porque la cookie anterior no será accesible bajo el nombre de host antiguo (`clientcode.tt.omtrdc.net`) debido a los modelos de seguridad del explorador. Se trata de una interrupción única solo en el corte inicial del nuevo CNAME. Las renovaciones de certificados no tienen el mismo efecto, ya que el nombre de host no cambia.

### ¿Qué tipo de clave y algoritmo de firma de certificado se utilizarán para la implementación de CNAME?

Todos los certificados son RSA SHA-256 y las claves son RSA de 2048 bits, de manera predeterminada. Actualmente no se admiten tamaños de claves mayores de 2048 bits.

### ¿Cómo puedo validar que la implementación de CNAME esté lista para el tráfico?

Utilice el siguiente conjunto de comandos (en el terminal de línea de comandos de MacOs o Linux, utilizando bash y curl 7.49+):

1. Primero pegue esta función bash en su terminal:

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{31,32,{34..38}}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. Luego pegue este comando (reemplazando `target.example.com` por su nombre de host):

   ```
   validateEdgeFpsslSni target.example.com
   ```

   Si la implementación está lista, debería ver el resultado como se muestra a continuación. La parte importante es que todas las líneas se muestren `CN=target.example.com`, lo cual coincide con nuestro nombre de host deseado. Si alguno de ellos se muestra `CN=*.tt.omtrdc.net`, la implementación **no está** lista.

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
   >Si este comando falla pero el `validateEdgeFpsslSni` comando anterior se ejecuta correctamente, es posible que tenga que esperar a que las actualizaciones DNS se propaguen por completo. Los registros DNS tienen un [TTL (tiempo de vida)](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) asociado que determina el tiempo de caducidad de la caché para las respuestas DNS de esos registros, por lo que es posible que tenga que esperar al menos mientras los TTLs. Puede utilizar el `dig target.example.com` comando o [el Cuadro de herramientas](https://toolbox.googleapps.com/apps/dig/#CNAME) de G Suite para buscar los TTL específicos.

## Limitaciones conocidas

* El modo de control de calidad no será persistente cuando tenga CNAME y at.js 1.x porque se basa en una cookie de terceros. La solución consiste en agregar los parámetros de previsualización a cada dirección URL a la que navegue. El modo de control de calidad es persistente cuando tiene CNAME y at.js 2.x.
* Actualmente, la `overrideMboxEdgeServer` configuración no funciona correctamente con CNAME. Esto debe establecerse como `false` para evitar que las solicitudes falle.
* Cuando se utiliza CNAME es más probable que aumente el tamaño del encabezado de la cookie para las llamadas de Destinatario. Se recomienda mantener el tamaño de la cookie por debajo de 8 KB.
