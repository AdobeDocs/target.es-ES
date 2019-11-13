---
keywords: client care;cname;programa de certificado;nombre canónico;cookies;certificado;amc;certificado administrado por adobe;digicert;validación de control de dominio;dcv
description: Información sobre cómo trabajar con Adobe Client Care para implementar el soporte de CNAME (nombre canónico) en Adobe Target.
title: CNAME y Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: 117e4c8712d49a284331552268cec42bb34cf013

---


# CNAME y Adobe Target {#cname-and-adobe-target}

Instructions about working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Adobe Target]. Para gestionar mejor los problemas de bloqueo de anuncios o las directivas de cookies relacionadas con ITP, se utiliza un CNAME de modo que las llamadas se realizan a un dominio propiedad del cliente en lugar de a un dominio propiedad de Adobe.

## Solicitar compatibilidad con CNAME

Realice los pasos siguientes para solicitar asistencia de CNAME en [!DNL Target]:

1. La autoridad de certificación de Adobe (DigiCert) debe comprobar que Adobe está autorizado para generar certificados bajo su dominio.

   DigiCert llama a este proceso a Validación [del control de](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/) dominio (DCV) y Adobe no podrá generar un certificado bajo su dominio hasta que se complete este proceso.

   DCV utiliza algunos métodos y puede realizar algunas acciones antes de abrir un ticket de Adobe Client Care (paso 3) para ayudarle a acelerar el proceso de DCV:

   * DigiCert probará primero el método de correo electrónico, en el que envía correos electrónicos a las direcciones que se encuentran en la información de WHOIS del dominio, así como a las direcciones de correo electrónico predeterminadas (administrador, administrador, webmaster, anfitrión y postmaster `@[domain_name]`). See the [DCV methods documentation](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/) for more information.

      Para acelerar el proceso de correo electrónico de DCV, DigiCert proporciona la siguiente recomendación:

      "Verifique que su registrador/proveedor WHOIS no haya enmascarado ni eliminado las direcciones [de correo electrónico]relevantes. Si lo están, averigüe si proporcionan una forma (por ejemplo, una dirección de correo electrónico anónima o un formulario web) para permitir que las autoridades [de] certificados accedan a los datos WHOIS de su dominio".

   * Si el método de correo electrónico DCV no es una opción para usted, el siguiente método es el método TXT DNS, en el que se agrega un registro TXT DNS al dominio con un valor hash. Este registro TXT indica a DigiCert que Adobe está autorizado para generar el certificado. Si necesita utilizar este método, informe a Adobe Client Care cuando abra un ticket (paso 3). Esto ayudará a acelerar el proceso de DCV.

1. Cree un registro CNAME en el DNS de su dominio que apunte a su nombre de host normal `clientcode.tt.omtrdc.net`. Por ejemplo: si el código de cliente es cnamecustomer y el nombre de host propuesto es `target.example.com`, el registro CNAME DNS debería tener este aspecto:

   ```
   target.example.com  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

1. Abra un ticket de [Adobe Client Care en el que se solicite la compatibilidad](https://docs.adobe.com/content/help/en/target/using/cmp-resources-and-contact-information.html#reference_ACA3391A00EF467B87930A450050077C) de CNAME con sus [!DNL Target] llamadas.

   Adobe trabajará con DigiCert para adquirir e implementar el certificado en los servidores de producción de Adobe. DigiCert iniciará el proceso de DCV y Adobe Client Care le notificará cuando la implementación esté lista.

1. Después de completar las tareas anteriores y Adobe Client Care le ha notificado que la implementación está lista, debe actualizar `serverDomain` al nuevo CNAME en at.js.

## Preguntas más frecuentes

La siguiente información responde a las preguntas más frecuentes sobre la solicitud e implementación del soporte de CNAM en [!DNL Target]:

### ¿Puedo proporcionar mi propio certificado? Si es así, ¿cuál es el proceso?

Sí, puede proporcionar su propio certificado para hacerlo:

1. Omita el paso 1 anterior, pero complete los pasos 2 y 3. Cuando abra un ticket de Adobe Client Care (paso 3), dígales que va a proporcionar su propio certificado.

   Adobe generará y le enviará una solicitud de firma de certificado (CSR).

1. Utilice el CSR para comprar el certificado a través de la entidad de certificación (CA) elegida.

1. Envíe el nuevo certificado público a Adobe. Los representantes de Adobe implementarán el certificado público en sus servidores de producción.

1. Complete el paso 4 después de que Adobe Client Care le haya notificado que la implementación está lista.

### Ya tengo una implementación CNAME para [!DNL Adobe Analytics], ¿podemos usar el mismo certificado o nombre de host?

No, [!DNL Target] requiere un nombre de host y un certificado independientes.

### ¿Cómo puedo validar que la implementación de CNAME esté lista para el tráfico?

Utilice el siguiente conjunto de comandos (en el terminal de línea de comandos de MacOs o Linux, utilizando bash y curl 7.49+):

1. Primero pegue esta función bash en su terminal:

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{17,21,22,26,{28..33}}.tt.omtrdc.net; do
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
   mboxedge33.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   ```

1. Valide el nuevo CNAME DNS con otra solicitud de curl, que también debería mostrar `CN=target.example.com`:

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >Si este comando falla pero el `validateEdgeFpsslSni` comando anterior se ejecuta correctamente, es posible que tenga que esperar a que las actualizaciones DNS se propaguen por completo.
