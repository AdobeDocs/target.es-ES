---
keywords: client care;cname;certificate program;canonical name;cookies;certificate;amc;adobe managed certificate;digicert;domain control validation;dcv
description: Información sobre cómo trabajar con Adobe Client Care para implementar el soporte de CNAME (nombre canónico) en Adobe Target.
title: CNAME y Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: 8267de6c27566ec397651d3bfc88aad0818ed8d2

---


# CNAME y Adobe Target {#cname-and-adobe-target}

Instructions for working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Adobe Target]. Para gestionar mejor los problemas de bloqueo de anuncios o las directivas de cookies relacionadas con ITP, se utiliza un CNAME de modo que las llamadas se realizan a un dominio propiedad del cliente en lugar de a un dominio propiedad de Adobe.

## Solicitar compatibilidad con CNAME

Realice los pasos siguientes para solicitar asistencia de CNAME en [!DNL Target]:

1. La autoridad de certificación de Adobe (DigiCert) debe comprobar que Adobe está autorizado para generar certificados bajo su dominio.

   DigiCert llama a este proceso a Validación del control [de dominio (DCV)](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/)y Adobe no podrá generar un certificado bajo su dominio hasta que se complete este proceso para al menos uno de los siguientes métodos DCV:

   * El método DCV más rápido es el método __CNAME__ DNS, en el que se agrega un registro CNAME DNS (que contiene un token) a su dominio que apunta al nombre de host DCV de DigiCert (dcv.digicert.com). Este registro CNAME indica a DigiCert que Adobe está autorizado para generar el certificado. Adobe Client Care le enviará las instrucciones con los registros DNS necesarios. Un ejemplo:

      ```
      3b0332e02daabf31651a5a0d81ba830a.target.example.com.  IN  CNAME  dcv.digicert.com.
      ```

      >[!NOTE]
      >
      >Estos tokens de DCV caducan pasados 30 días, momento en el que Adobe Client Care se pondrá en contacto con usted mediante tokens actualizados. Para obtener el tiempo más rápido para la resolución de su solicitud CNAME, prepárese para realizar estos cambios de DNS en todos los dominios solicitados antes de enviar la solicitud.

      >[!NOTE]
      >
      >Si su dominio tiene registros [CAA](https://en.wikipedia.org/wiki/DNS_Certification_Authority_Authorization)DNS, deberá agregar `digicert.com` si aún no se ha agregado. Este registro DNS indica qué autoridades de certificados están autorizadas para emitir certificados para el dominio. El registro DNS resultante tendría este aspecto: `example.com. IN CAA 0 issue "digicert.com"`. Puede utilizar [el Cuadro de herramientas](https://toolbox.googleapps.com/apps/dig/#CAA) de G Suite para determinar si su dominio raíz tiene un registro CAA existente. Puedes leer más sobre cómo DigiCert maneja los registros de CAA [aquí](https://docs.digicert.com/manage-certificates/dns-caa-resource-record-check).

   * DigiCert también probará el método __de__ correo electrónico, en el que envía correos electrónicos a las direcciones que se encuentran en la información de WHOIS del dominio, así como a las direcciones de correo electrónico predeterminadas (administrador, administrador, webmaster, anfitrión y postmaster `@[domain_name]`). See the [DCV methods documentation](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/) for more information.

      Para acelerar el proceso de correo electrónico de DCV, DigiCert proporciona la siguiente recomendación:

      &quot;Verifique que su registrador/proveedor WHOIS no haya enmascarado ni eliminado las direcciones [de correo electrónico]relevantes. Si lo están, averigüe si proporcionan una forma (por ejemplo, una dirección de correo electrónico anónima o un formulario web) para permitir que las autoridades [de] certificados accedan a los datos WHOIS de su dominio&quot;.

1. Cree un registro CNAME en el DNS de su dominio que apunte a su nombre de host normal `clientcode.tt.omtrdc.net`. Por ejemplo: si el código de cliente es cnamecustomer y el nombre de host propuesto es `target.example.com`, el registro CNAME DNS debería tener este aspecto:

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

1. Abra un ticket de [Adobe Client Care en el que se solicite la compatibilidad](https://docs.adobe.com/content/help/en/target/using/cmp-resources-and-contact-information.html#reference_ACA3391A00EF467B87930A450050077C) de CNAME con sus [!DNL Target] llamadas.

   Adobe trabajará con DigiCert para adquirir e implementar el certificado en los servidores de producción de Adobe. DigiCert iniciará el proceso de DCV y Adobe Client Care le notificará cuando la implementación esté lista.

1. Después de completar las tareas anteriores y Adobe Client Care le ha notificado que la implementación está lista, debe actualizar `serverDomain` al nuevo CNAME en at.js.

## Preguntas frecuentes

La siguiente información responde a las preguntas más frecuentes sobre la solicitud e implementación de la compatibilidad con CNAME en [!DNL Target]:

### ¿Puedo proporcionar mi propio certificado (también conocido como BYOC)? Si es así, ¿cuál es el proceso?

Sí, puede proporcionar su propio certificado, pero no __se recomienda__. La administración del ciclo vital del certificado SSL es mucho más fácil para Adobe y el cliente cuando Adobe compra y controla el certificado. Los certificados SSL deben renovarse cada año, lo que significa que Adobe Client Care deberá ponerse en contacto con usted cada año para enviar un nuevo certificado a Adobe de forma oportuna. Es posible que algunos clientes tengan dificultades para producir un certificado renovado de manera oportuna cada año, lo que pone en peligro su [!DNL Target] implementación porque los exploradores rechazarán las conexiones cuando caduque el certificado.

>[!NOTE]
>
>Tenga en cuenta que si solicita una implementación CNAME con [!DNL Target] certificado propio, será responsable de proporcionar certificados renovados a Adobe Client Care cada año. Si se permite que el certificado CNAME caduque antes de que Adobe pueda implementar un certificado renovado, se interrumpirá la implementación específica [!DNL Target] .

1. Omita el paso 1 anterior, pero complete los pasos 2 y 3. Cuando abra un ticket de Adobe Client Care (paso 3), dígales que va a proporcionar su propio certificado.

   Adobe generará y le enviará una solicitud de firma de certificado (CSR).

1. Utilice el CSR para comprar el certificado a través de la entidad de certificación (CA) elegida.

1. Envíe el nuevo certificado público a Adobe. Los representantes de Adobe implementarán el certificado público en sus servidores de producción.

1. Complete el paso 4 después de que Adobe Client Care le haya notificado que la implementación está lista.

### ¿Cuánto tiempo falta para que caduque mi nuevo certificado SSL?

Los certificados expedidos antes del 1 de septiembre de 2020 serán certificados de dos años. Los certificados emitidos el 1 de septiembre de 2020 y posteriores serán certificados de un año. Puede leer más sobre el paso a los certificados de 1 año [aquí](https://www.digicert.com/position-on-1-year-certificates).

### ¿Qué nombres de host debo elegir? ¿Cuántos nombres de host debo elegir por dominio?

[!DNL Target] Las implementaciones de CNAME solo requieren un nombre de host por dominio en el certificado SSL y en el DNS del cliente, por lo que es lo que recomendamos. Algunos clientes pueden requerir nombres de host adicionales por dominio para sus propios fines (por ejemplo, prueba en ensayo), lo cual es compatible.

La mayoría de los clientes eligen un nombre de host como `target.example.com`, por lo que es lo que recomendamos, pero la elección es en última instancia tuya. Asegúrese de no solicitar un nombre de host de un registro DNS existente, ya que esto provocaría un conflicto y retrasaría el tiempo de resolución de la solicitud de [!DNL Target] CNAME.

### Ya tengo una implementación CNAME para [!DNL Adobe Analytics], ¿podemos usar el mismo certificado o nombre de host?

No, [!DNL Target] requiere un nombre de host y un certificado independientes.

### ¿La implementación actual del Destinatario se ve afectada por ITP 2.1 o 2.2?

En un navegador Safari, navegue hasta el sitio web en el que tenga una biblioteca JavaScript de Destinatario. If you see a Target cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.1 or 2.2.

Los problemas de ITP se pueden resolver para el Destinatario solo con un CNAME de Analytics. Solo necesitará un CNAME de Destinatario independiente en el caso de escenarios de bloqueo de anuncios en los que se bloquee el Destinatario.

Para obtener más información sobre ITP, consulte [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

### ¿Puede Adobe/DigiCert enviar los correos electrónicos del DCV a otra dirección de correo electrónico `<someone>@example.com`?

No, DigiCert (o cualquier autoridad de certificación) no permitirá que cualquier persona con una dirección de correo electrónico bajo un dominio autorice un certificado SSL bajo ese mismo dominio a menos que esa dirección de correo electrónico también esté incluida en la información WHOIS del dominio o en la lista de direcciones predeterminada (ver arriba). Esto garantiza que solo los individuos autorizados puedan aprobar el DCV para un dominio en particular. Si esto no es posible para usted, le recomendamos que utilice el método DCV CNAME DNS (ver más arriba).

### ¿Cómo puedo validar que la implementación de CNAME esté lista para el tráfico?

Utilice el siguiente conjunto de comandos (en el terminal de línea de comandos de MacOs o Linux, utilizando bash y curl 7.49+):

1. Primero pegue esta función bash en su terminal:

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{17,21,22,26,{28..32},34,35,37,38}.tt.omtrdc.net; do
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
   mboxedge17.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge21.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge22.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge26.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge28.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge29.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge30.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge31.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge32.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge34.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge35.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
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
