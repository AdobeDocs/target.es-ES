---
description: Use un redirector de forma similar a como se usa un mbox en las pruebas.
keywords: Implementación;mbox.js sin javascript;redirector;costes por clic;ingresos por clic
seo-description: Use un redirector de forma similar a como se usa un mbox en las pruebas.
seo-title: Trabajar con redirectores
solution: Target
subtopic: Primeros pasos
title: Trabajar con redirectores
topic: Standard
uuid: 79d7caf6-5693-4bb3-9131-8d1ae420fa5e
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Trabajar con redirectores{#work-with-redirectors}

Use un redirector de forma similar a como se usa un mbox en las pruebas.

Los redirectores se crean con una dirección URL de redirector especial que carga un mbox de redirector en su cuenta. Use este redirector de forma similar a como se usa un mbox en las pruebas. Envíe la dirección URL del redirector a la red de publicidad como vínculo de destino de la publicidad.

Use el redirector para   hacer lo siguiente:

* Rastrear los clics de los anuncios en pantalla en su sitio
* Crear un único informe centralizado para rastrear los clics efectuados en los anuncios en pantalla de las redes de publicidad múltiple
* Modificar los destinos de los anuncios en pantalla

   Por ejemplo, el mismo titular aterriza en la página principal, la página de categorías y la página de productos.

* Averigüe cuál es la página de aterrizaje que produce el mayor número de conversiones

Para obtener ayuda para decidir la configuración adecuada, consulte   [Implementaciones no basadas en JavaScript](../../c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4).

## Cree un redirector {#task_76608B0F73FC45C4A9F125B894DCF821}

Antes de poder usar un redirector, debe crearlo.

1. Determine las variaciones de destino de la publicidad, incluido el destino predeterminado.
1. Cree la dirección URL del redirector.

   ```
   https://<your_testandtarget_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox
   /​page?mbox=redirectorlink_456
   &mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm
   ```

   * Donde `yourclientcode` es el código de cliente de su empresa. El código de cliente de su empresa está por completo en minúscula y carece de caracteres especiales.

      * **at.js:** El código de cliente se encuentra disponible en la parte superior de la página de la interfaz de [!UICONTROL  en ]Configuración &gt; Implementación &gt; Editar la configuración de at.js[!DNL Target].

      * **mbox.js**: el código de cliente se encuentra disponible en la parte superior de la página en [!UICONTROL Configuración &gt; Implementación &gt; Editar la configuración de mbox.js].
   * `redirectorlink_456` es el nombre del mbox de redirector que aparecerá en la cuenta para usarlo en campañas y pruebas.

      Aunque se muestran como cualquier otro mbox en la cuenta, los redirectores funcionan de manera distinta a otros mboxes. Asigne un nombre al redirector que permita distinguirlo fácilmente de los mboxes estándar en la cuenta.  Se recomienda comenzar el nombre del mbox con “redirectorlink”.

   * Donde `http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm` es el destino predeterminado.

      Debe tener codificación de dirección URL y ser una referencia absoluta. Puede utilizar la Referencia de codificación URL [HTML](https://www.w3schools.com/tags/ref_urlencode.asp) para codificar rápidamente las direcciones URL. |



1. Valide el redirector.
   1. Inserte la dirección URL del redirector en un navegador y actualícelo.
   1. Inicie sesión en la cuenta, actualice la lista de mboxes y confirme que el nuevo redirector aparece enumerado en la cuenta.
1. Si va a comprobar diferentes destinos para un anuncio, cree [Ofertas de redireccionamiento](../../c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA) para cada versión.
1. Cree la campaña.

   Consulte [Implementaciones no basadas en JavaScript](../../c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4) para saber cuál es la configuración apropiada para alcanzar sus metas.
1. Lleve a cabo un control de calidad en la campaña.

   Cree una página ficticia con un `<a href>` que contenga la dirección URL del redirector. Ejemplo:

   ```
   <a href=https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=
   
   redirectorlink_456&mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2F​usualdestination%2Ehtm>
   ```

1. Confirme que todas las experiencias, el contenido predeterminado y los informes se comportan del modo esperado en todos los tipos de navegador y en cualquier entorno.

   >[!NOTE] {class=&quot;- topic/note &quot;}
   >
   >* Los redirectores no son compatibles con las vistas previas de ofertas o con la exploración en busca de mboxes. Obtenga una vista previa de las experiencias directamente en un navegador.
   >* `mboxDebug` no funciona con los redirectores.


1. Envíe la dirección URL completa del redirector a la red de anuncios en pantalla como destino de la publicidad.

## Uso de un redirector para pasar los costes por clic y los ingresos por clic {#concept_3078EF48E9C44B34992D62AAB9628853}

Información acerca de cómo utilizar un redirector para pasar los costes por clic y los ingresos por clic.

### Paso de los costes por clic {#section_DEB889470F7D4360B5CEA85FD05DEDFA}

Use un redirector para pasar los costes por clic.

>[!NOTE]
>
>Lo mejor es averiguar el valor de costo mediante la métrica de compromiso **Puntaje por visita** , tal como se describe en [Participación](https://marketing.adobe.com/resources/help/en_US/tnt/help/c_Capturing_Engagement.html).

Añada `&mboxPageValue=-value` a la dirección URL. Observe el valor negativo.

Ejemplo: para un costo por clic de 0,10 céntimos:

```
https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=redirectorlink_456
&mboxPageValue=-0.1&mboxDefault=​https://www.yourcompany.com/usualdestination.htm
```

### Paso de los ingresos por clic   {#section_3E48AC465E7D42DAAC51B4BFF83F64B1}

Use un redirector para pasar los ingresos por clic.

>[!NOTE]
>
>Lo mejor es averiguar el valor de los ingresos mediante la métrica de compromiso **Puntaje por visita** , tal como se describe en [Participación](https://marketing.adobe.com/resources/help/en_US/tnt/help/c_Capturing_Engagement.html).

Añada `&mboxPageValue=value` a la dirección URL.

Ejemplo: para unos ingresos por clic de 0,10 céntimos:

```
https://<​your_clientcode>​​​​.tt​​.omtrdc​.net/​​m2/​yourclientcode/​ubox/​​​page?mbox=redirectorlink_456
&mboxPageValue=0.1​&mbox​Default=​​http%3A%2F%2Fwww%2E​yourcompany%2Ecom​%2Fusualdestination%2Ehtm
```
