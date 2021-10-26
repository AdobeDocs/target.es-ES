---
keywords: client care;cname;programa de certificados;nombre canónico;cookies;certificado;amc;adobe managed certificate;digicert;validación de control de dominio;dcv
description: Trabajar con [!DNL Adobe] Client Care to implement CNAME (Canonical Name) support in [!DNL Adobe Target] para controlar los problemas de bloqueo de anuncios.
title: ¿Cómo utilizo CNAME en Target?
feature: Privacy & Security
role: Developer
exl-id: bf533771-6d46-48ba-964c-3ad9ce9f7352
source-git-commit: 3e15b8d06cb8185be27a8e0210ecfcfc5002b7e7
workflow-type: tm+mt
source-wordcount: '1145'
ht-degree: 1%

---

# CNAME y [!DNL Target]

Instrucciones para trabajar con [!DNL Adobe] ClientCare va a implementar la compatibilidad con CNAME (nombre canónico) en [!DNL Adobe Target]. Utilice CNAME para gestionar problemas de bloqueo de anuncios o directivas de cookies relacionadas con ITP (prevención inteligente del seguimiento). Con CNAME, las llamadas se realizan a un dominio propiedad del cliente en lugar de a un dominio propiedad de [!DNL Adobe].

## Solicitar compatibilidad con CNAME en [!DNL Target]

1. Determine la lista de nombres de host que necesita para su certificado SSL (consulte las preguntas frecuentes a continuación).

1. Para cada nombre de host, cree un registro CNAME en su DNS que apunte a su [!DNL Target] hostname `clientcode.tt.omtrdc.net`.

   Por ejemplo, si el código de cliente es &quot;cnamecustomer&quot; y el nombre de host propuesto es `target.example.com`, su registro CNAME DNS tiene un aspecto similar a:

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!IMPORTANT]
   >
   >[!DNL Adobe]La autoridad de certificación de , DigiCert, no puede emitir un certificado hasta que se complete este paso. Por lo tanto, [!DNL Adobe] no puede realizar la solicitud de una implementación CNAME hasta que se complete este paso.

1. [Rellene este formulario](/help/assets/FPC_Request_Form.xlsx) e inclúyalo cuando [abra un [!DNL Adobe] ticket de ClientCare solicitando asistencia de CNAME](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C):

   * [!DNL Adobe Target] client code:
   * Nombres de host de certificados SSL (ejemplo: `target.example.com target.example.org`):
   * Comprador de certificados SSL ([!DNL Adobe] es muy recomendable, consulte preguntas frecuentes): Adobe/cliente
   * Si el cliente compra el certificado, también conocido como &quot;Traer su propio certificado&quot; (BYOC), rellene estos detalles adicionales:
      * Organización de certificados (ejemplo: Empresa de Ejemplo S.A.):
      * Unidad organizativa del certificado (opcional, ejemplo: Marketing):
      * País del certificado (ejemplo: EE. UU.):
      * Estado o región del certificado (ejemplo: California):
      * Ciudad del certificado (ejemplo: San José):

1. If [!DNL Adobe] compra el certificado, [!DNL Adobe] funciona con DigiCert para adquirir e implementar el certificado en [!DNL Adobe]de los servidores de producción de .

   Si el cliente compra el certificado (BYOC), [!DNL Adobe] ClientCare le envía la solicitud de firma de certificado (CSR). Utilice la CSR al adquirir el certificado a través de la autoridad de certificación que elija. Una vez emitido el certificado, envíe una copia del certificado y de los certificados intermedios a [!DNL Adobe] ClientCare para la implementación.

   [!DNL Adobe] ClientCare le notifica cuando la implementación está lista.

1. Actualice el `serverDomain` ([documentación](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#serverDomain)) al nuevo nombre de host CNAME y establezca `overrideMboxEdgeServer` a `false` ([documentación](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#overridemboxedgeserver)) en la configuración de at.js.

## Preguntas frecuentes

La siguiente información responde a las preguntas más frecuentes sobre la solicitud e implementación de la compatibilidad con CNAME en [!DNL Target]:

### ¿Puedo proporcionar mi propio certificado (Traer su propio certificado o BYOC)?

Puede proporcionar su propio certificado. Sin embargo, [!DNL Adobe] no recomienda esta práctica. La administración del ciclo de vida del certificado SSL es más fácil para ambos [!DNL Adobe] y usted si [!DNL Adobe] compra y controla el certificado. Los certificados SSL deben renovarse cada año. Por lo tanto, [!DNL Adobe] Atención al cliente debe ponerse en contacto con usted cada año para obtener un nuevo certificado de forma oportuna. Algunos clientes pueden tener dificultades para producir un certificado renovado de forma oportuna. Su [!DNL Target] la implementación se ve amenazada cuando el certificado caduca porque los navegadores rechazan las conexiones.

>[!IMPORTANT]
>
>Si solicita una [!DNL Target] traer su propio certificado de implementación de CNAME, usted es responsable de proporcionar certificados renovados a [!DNL Adobe] Atención al cliente cada año. Permitiendo que el certificado CNAME caduque antes de que [!DNL Adobe] puede implementar un certificado renovado en un corte para el [!DNL Target] implementación.

### ¿Cuánto tiempo falta para que caduque mi nuevo certificado SSL?

Todo [!DNL Adobe]-los certificados adquiridos son válidos durante un año. Consulte [Artículo de DigiCert sobre certificados de 1 año](https://www.digicert.com/blog/position-on-1-year-certificates) para obtener más información.

### ¿Qué nombres de host debo elegir? ¿Cuántos nombres de host debo elegir por dominio?

[!DNL Target] Las implementaciones CNAME requieren solo un nombre de host por dominio en el certificado SSL y en el DNS del cliente. [!DNL Adobe] recomienda un nombre de host por dominio. Algunos clientes requieren más nombres de host por dominio para sus propios fines (prueba en el entorno de ensayo, por ejemplo), que se admite.

La mayoría de los clientes eligen un nombre de host como `target.example.com`. [!DNL Adobe] recomienda seguir esta práctica, pero la elección es en última instancia tuya. No solicite un nombre de host de un registro DNS existente. Al hacerlo, se genera un conflicto y se retrasa el tiempo de resolución de [!DNL Target] Solicitud CNAME.

### Ya tengo una implementación CNAME para [!DNL Adobe Analytics], ¿puedo usar el mismo certificado o nombre de host?

No, [!DNL Target] requiere un nombre de host y un certificado independientes.

### ¿Es mi implementación actual de [!DNL Target] ¿se ve afectado por ITP 2.x?

La versión 2.3 de Apple Intelligent Tracking Prevention (ITP) introdujo su función de mitigación de encubrimiento CNAME, que es capaz de detectar [!DNL Adobe Target] Implementaciones CNAME y reduce la caducidad de la cookie a siete días. Actualmente [!DNL Target] no tiene una solución para la mitigación de cierre CNAME de ITP. Para obtener más información sobre ITP, consulte [Prevención inteligente del seguimiento de Apple (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

### ¿Qué tipo de interrupciones del servicio puedo esperar cuando se implementa mi implementación CNAME?

No hay interrupciones en el servicio cuando se implementa el certificado (incluidas las renovaciones de certificados).

Sin embargo, después de cambiar el nombre de host en su [!DNL Target] código de implementación (`serverDomain` en at.js) al nuevo nombre de host CNAME (`target.example.com`), los navegadores web tratan a los visitantes que regresan como nuevos visitantes. Se pierden los datos de perfil de los visitantes que regresan porque no se puede acceder a la cookie anterior bajo el nombre de host antiguo (`clientcode.tt.omtrdc.net`). La cookie anterior es inaccesible debido a los modelos de seguridad del explorador. Esta interrupción solo ocurre en el corte inicial del nuevo CNAME. Las renovaciones de certificados no tienen el mismo efecto porque el nombre de host no cambia.

### ¿Qué tipo de clave y algoritmo de firma de certificado se usan para mi implementación CNAME?

Todos los certificados son RSA SHA-256 y las claves son RSA de 2048 bits, de forma predeterminada. Actualmente no se admiten los tamaños de claves superiores a 2048 bits.

### ¿Cómo puedo validar que mi implementación CNAME esté lista para el tráfico?

Utilice el siguiente conjunto de comandos (en el terminal de línea de comandos de macOS o Linux, utilizando bash y curl >=7.49):

1. Copie y pegue esta función bash en su terminal o pegue la función en su archivo de script de inicio bash (normalmente `~/.bash_profile` o `~/.bashrc`) para que la función esté disponible en las sesiones de terminal:

   ```
   function adobeTargetCnameValidation {
     local hostname="$1"
     if [ -z "$hostname" ]; then
       echo "ERROR: no hostname specified"
       return 1
     fi
   
     local service="Adobe Target CNAME implementation"
     local edges="31 32 34 35 36 37 38"
     local edgeDomain="tt.omtrdc.net"
     local edgeFormat="mboxedge%d%s.$edgeDomain"
     local shardFormat="-alb%02d"
     local shards=5
     local shardsFoundCount=0
     local shardsFound
     local shardsFoundOutput
     local curlRegex="subject:.*CN=|expire date:|issuer:"
     local curlValidation="SSL certificate verify ok"
     local curlResponseValidation='"OK"'
     local curlEndpoint="/uptime?mboxClient=uptime3"
     local url="https://$hostname$curlEndpoint"
     local sslLabsUrl="https://ssllabs.com/ssltest/analyze.html?hideResults=on&latest&d=$hostname"
     local success="✅"
     local failure="🚫"
     local info="🔎"
     local rule="="
     local horizontalRule="$(seq ${COLUMNS:-30} | xargs printf "$rule%.0s")"
     local miniRule="$(seq 5 | xargs printf "$rule%.0s")"
     local curlVersion="$(curl --version | head -1 | cut -d' ' -f2 )"
     local curlVersionRequired=">=7.49"
     local edgeCount="$(wc -w <<< "$edges" | tr -d ' ')"
     local edge
     local shard
     local currEdgeShard
     local dnsOutput
     local cnameExists
     local endToEndTestSucceeded
     local curlResult
   
     for shard in $(seq $shards); do
       if [ "$shardsFoundCount" -eq 0 ]; then
         for edge in $edges; do
           if [ "$shard" -eq 1 ]; then
             currEdgeShard="$(printf "$edgeFormat" "$edge" "")"
           else
             currEdgeShard="$(
               printf "$edgeFormat" "$edge" "$(
                 printf -- "$shardFormat" "$shard"
               )"
             )"
           fi
           curlResult="$(curl -vsm20 --connect-to "$hostname:443:$currEdgeShard:443" "$url" 2>&1)"
           if grep -q "$curlValidation" <<< "$curlResult"; then
             shardsFound+=" $currEdgeShard"
             if grep -q "$curlResponseValidation" <<< "$curlResult"; then
               shardsFoundCount=$((shardsFoundCount+1))
               shardsFoundOutput+="\n\n$miniRule $success $hostname [edge shard: $currEdgeShard] $miniRule\n"
             else
               shardsFoundOutput+="\n\n$miniRule $failure $hostname [edge shard: $currEdgeShard] $miniRule\n"
             fi
             shardsFoundOutput+="$(grep -E "$curlRegex" <<< "$curlResult" | sort)"
             if ! grep -q "$curlResponseValidation" <<< "$curlResult"; then
               shardsFoundOutput+="\nERROR: unexpected HTTP response from this shard using $url"
             fi
           fi
         done
       fi
     done
   
     echo
     echo "$horizontalRule"
     echo
     echo "$service validation for hostname $hostname:"
     dnsOutput="$(dig -t CNAME +short "$hostname" 2>&1)"
     if grep -qFi ".$edgeDomain" <<< "$dnsOutput"; then
       echo "$success $hostname passes DNS CNAME validation"
       cnameExists=true
     else
       echo -n "$failure $hostname FAILED DNS CNAME validation -- "
       if [ -n "$dnsOutput" ]; then
         echo -e "$dnsOutput is not in the subdomain $edgeDomain"
       else
         echo "required DNS CNAME record pointing to <target-client-code>.$edgeDomain not found"
       fi
     fi
   
     curlResult="$(curl -vsm20 "$url" 2>&1)"
     if grep -q "$curlValidation" <<< "$curlResult"; then
       if grep -q "$curlResponseValidation" <<< "$curlResult"; then
         echo -en "$success $hostname passes TLS and HTTP response validation"
         if [ -n "$cnameExists" ]; then
           echo
         else
           echo " -- the DNS CNAME is not pointing to the correct subdomain for ${service}s with Adobe-managed certificates" \
             "(bring-your-own-certificate implementations don't have this requirement), but this test passes as configured"
         fi
         endToEndTestSucceeded=true
       else
         echo -n "$failure $hostname FAILED HTTP response validation --" \
           "unexpected response from $url -- "
         if [ -n "$cnameExists" ]; then
           echo "DNS is NOT pointing to the correct shard, notify Adobe Client Care"
         else
           echo "the required DNS CNAME record is missing, see above"
         fi
       fi
     else
   
       echo -n "$failure $hostname FAILED TLS validation -- "
       if [ -n "$cnameExists" ]; then
         echo "DNS is likely NOT pointing to the correct shard or there's a validation issue with the certificate or" \
           "protocols, see curl output below and optionally SSL Labs ($sslLabsUrl):"
         echo ""
         echo "$horizontalRule"
         echo "$curlResult" | sed 's/^/    /g'
         echo "$horizontalRule"
         echo ""
       else
         echo "the required DNS CNAME record is missing, see above"
       fi
     fi
   
     if [ "$shardsFoundCount" -ge "$edgeCount" ]; then
       echo -n "$success $hostname passes shard validation for the following $shardsFoundCount edge shards:"
       echo -e "$shardsFoundOutput"
       echo
   
       if [ -n "$cnameExists" ] && [ -n "$endToEndTestSucceeded" ]; then
         echo "$horizontalRule"
         echo ""
         echo "  For additional TLS/SSL validation, including detailed browser/client support,"
         echo "  see SSL Labs (click the first IP address if prompted):"
         echo ""
         echo "    $info  $sslLabsUrl"
         echo ""
         echo "  To check DNS propagation around the world, see whatsmydns.net:"
         echo ""
         echo "    $info  DNS A records:     https://whatsmydns.net/#A/$hostname"
         echo "    $info  DNS CNAME record:  https://whatsmydns.net/#CNAME/$hostname"
       fi
     else
       echo -n "$failure $hostname FAILED shard validation -- shards found: $shardsFoundCount," \
         "expected: $edgeCount"
       if bc -l <<< "$(cut -d. -f1,2 <<< "$curlVersion") $curlVersionRequired" 2>/dev/null | grep -q 0; then
         echo -n " -- insufficient curl version installed: $curlVersion, but this script requires curl version" \
           "$curlVersionRequired because it uses the curl --connect-to flag to bypass DNS and directly test" \
           "each Adobe Target edge shards' SNI confirguation for $hostname"
       fi
       if [ -n "$shardsFoundOutput" ]; then
         echo -e ":\n$shardsFoundOutput"
       fi
       echo
     fi
     echo
     echo "$horizontalRule"
     echo
   }
   ```

1. Pegar este comando (reemplazar `target.example.com` con su nombre de host):

   ```
   adobeTargetCnameValidation target.example.com
   ```

   Si la implementación está lista, verá los resultados como se muestra a continuación. La parte importante es que todas las líneas de estado de validación muestren `✅` en lugar de `🚫`. Cada [!DNL Target] el elemento compartido CNAME perimetral debería mostrarse `CN=target.example.com`, que coincide con el nombre de host principal del certificado solicitado (los nombres de host SAN adicionales del certificado no se imprimen en esta salida).

   ```
   $ adobeTargetCnameValidation target.example.com
   
   ==========================================================
   
   Adobe Target CNAME implementation validation for hostname target.example.com:
   ✅ target.example.com passes DNS CNAME validation
   ✅ target.example.com passes TLS and HTTP response validation
   ✅ target.example.com passes shard validation for the following 7 edge shards:
   
   ===== ✅ target.example.com [edge shard: mboxedge31-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge32-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge34-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge35-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge36-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge37-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge38-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ==========================================================
   
     For additional TLS/SSL validation, including detailed browser/client support,
     see SSL Labs (click the first IP address if prompted):
   
       🔎  https://ssllabs.com/ssltest/analyze.html?hideResults=on&latest&d=target.example.com
   
     To check DNS propagation around the world, see whatsmydns.net:
   
       🔎  DNS A records:     https://whatsmydns.net/#A/target.example.com
       🔎  DNS CNAME record:  https://whatsmydns.net/#CNAME/target.example.com
   
   ==========================================================
   ```

   >[!NOTE]
   >
   >Si este comando de validación falla en la validación de DNS pero ya ha realizado los cambios de DNS necesarios, es posible que tenga que esperar a que las actualizaciones de DNS se propaguen por completo. Los registros DNS tienen asociado un [TTL (tiempo de vida)](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) que dicta el tiempo de caducidad de la caché para las respuestas DNS de esos registros. Como resultado, es posible que tenga que esperar al menos mientras los TTL sean. Puede usar la variable `dig target.example.com` comando o [G Suite Toolbox](https://toolbox.googleapps.com/apps/dig/#CNAME) para buscar los TTL específicos. Para comprobar la propagación de DNS en todo el mundo, consulte [whatsmydns.net](https://whatsmydns.net/#CNAME).

### ¿Cómo utilizo un vínculo de no participación con CNAME?

Si utiliza CNAME, el vínculo de no participación debe contener &quot;client=`clientcode` , por ejemplo:
`https://my.cname.domain/optout?client=clientcode`.

Reemplazar `clientcode` con el código de cliente, agregue el texto o la imagen que se vinculará a la variable [URL de exclusión](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#reference_E7A62B7B99C94B3A806CB262D16E27FC).

## Limitaciones conocidas

* El modo de control de calidad no es persistente cuando tiene CNAME y at.js 1.x porque se basa en una cookie de terceros. La solución es añadir los parámetros de vista previa a cada URL a la que navegue. El modo de control de calidad es persistente cuando tiene CNAME y at.js 2.x.
* Al utilizar CNAME, es más probable que el tamaño del encabezado de la cookie para [!DNL Target] las llamadas a aumentan. [!DNL Adobe] recomienda mantener el tamaño de la cookie por debajo de 8 KB.
