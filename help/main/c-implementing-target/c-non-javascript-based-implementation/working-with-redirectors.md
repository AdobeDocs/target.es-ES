---
keywords: Implementación;mbox.js sin javascript;redirector;costes por clic;ingresos por clic
description: Aprenda a utilizar redirectores en implementaciones de correo electrónico, de forma similar a como se usa un mbox en el Adobe [!DNL Target] actividades.
title: ¿Cómo trabajo con los redirectores?
feature: Implement Email
role: Developer
exl-id: 1e7b99e4-857b-4d0f-afbd-2c5ce6bf0557
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 71%

---

# Trabajar con redirectores

Use un redirector de forma similar a como se usa un mbox en las pruebas.

Los redirectores se crean con una dirección URL de redirector especial que carga un mbox de redirector en su cuenta. Use este redirector de forma similar a como se usa un mbox en las pruebas. Envíe la dirección URL del redirector a la red de publicidad como vínculo de destino de la publicidad.

Use el redirector para   hacer lo siguiente:

* Rastrear los clics de los anuncios en pantalla en su sitio
* Crear un único informe centralizado para rastrear los clics efectuados en los anuncios en pantalla de las redes de publicidad múltiple
* Modificar los destinos de los anuncios en pantalla

   Por ejemplo, el mismo titular aterriza en la página principal, la página de categorías y la página de productos.

* Averigüe cuál es la página de aterrizaje que produce el mayor número de conversiones

Para obtener ayuda para decidir la configuración adecuada, consulte   [Implementaciones no basadas en JavaScript](/help/main/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4).

## Crear un redirector {#redirector}

Antes de poder usar un redirector, debe crearlo.

1. Determine las variaciones de destino de la publicidad, incluido el destino predeterminado.
1. Cree la dirección URL del redirector.

   ```
   https://<your_testandtarget_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox
   /​page?mbox=redirectorlink_456
   &mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm
   ```

   * Donde `yourclientcode` es el código de cliente de la empresa. El código de cliente de su compañía está por completo en minúscula y carece de caracteres especiales.

      El código de cliente se encuentra disponible en la parte superior del [!UICONTROL Administración > Implementación] de [!DNL Target] interfaz.

   * `redirectorlink_456` es el nombre del mbox de redirector que aparecerá en la cuenta para usarlo en campañas y pruebas.

      Aunque se muestran como cualquier otro mbox en la cuenta, los redirectores funcionan de manera distinta a otros mboxes. Asigne un nombre al redirector que permita distinguirlo fácilmente de los mboxes estándar en la cuenta.  Se recomienda comenzar el nombre del mbox con “redirectorlink”.

   * Donde `http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm` es el destino predeterminado.

      Debe tener codificación de dirección URL y ser una referencia absoluta. Puede usar la variable [Referencia de codificación de URL de HTML](https://www.w3schools.com/tags/ref_urlencode.asp) para codificar rápidamente sus URL.

      >[!IMPORTANT]
      >
      >Tenga en cuenta que con Redirector puede estar expuesto al riesgo de una vulnerabilidad de redireccionamiento abierto. Para evitar el uso no autorizado de vínculos de redirector por terceros, recomendamos utilizar &quot;hosts autorizados&quot; para la lista de permitidos de los dominios de URL de redireccionamiento predeterminados. Target usa hosts para la lista de permitidos de dominios a los que desea permitir redirecciones. Para obtener más información, consulte [Creación de listas de permitidos que especifiquen hosts con autorización para enviar llamadas de mbox a Target](/help/main/administrating-target/hosts.md#allowlist) en *Hosts*.

1. Valide el redirector.
   1. *Práctica recomendada de seguridad*: Asegúrese de que el dominio utilizado en el redirector esté incluido en la lista de permitidos, tal como se ha indicado anteriormente. Si utiliza un dominio que no está incluido en la lista de permitidos, el Adobe bloqueará cualquier llamada a ese dominio para evitar que los actores maliciosos utilicen el redirector para redireccionar a dominios potencialmente maliciosos.
   1. Inserte la dirección URL del redirector en un navegador y actualícelo.
   1. Inicie sesión en la cuenta, actualice la lista de mboxes y confirme que el nuevo redirector aparece enumerado en la cuenta.
1. Si va a comprobar diferentes destinos para un anuncio, cree [Ofertas de redireccionamiento](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA) para cada versión.
1. Cree la campaña.

   Consulte [Implementaciones no basadas en JavaScript](/help/main/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4) para saber cuál es la configuración apropiada para alcanzar sus metas.
1. Lleve a cabo un control de calidad en la campaña.

   Cree una página ficticia con un `<a href>` que contenga la dirección URL del redirector. Ejemplo:

   ```
   <a href=https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=
   
   redirectorlink_456&mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2F​usualdestination%2Ehtm>
   ```

1. Confirme que todas las experiencias, el contenido predeterminado y los informes se comportan del modo esperado en todos los tipos de navegador y en cualquier entorno.

   >[!NOTE]
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
>Una práctica recomendada es determinar el valor de coste utilizando la variable **Puntuación por visita** métrica de participación.

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
>Una práctica recomendada es determinar el valor de los ingresos mediante la variable **Puntuación por visita** métrica de participación.

Añada `&mboxPageValue=value` a la dirección URL.

Ejemplo: para unos ingresos por clic de 0,10 céntimos:

```
https://<​your_clientcode>​​​​.tt​​.omtrdc​.net/​​m2/​yourclientcode/​ubox/​​​page?mbox=redirectorlink_456
&mboxPageValue=0.1​&mbox​Default=​​http%3A%2F%2Fwww%2E​yourcompany%2Ecom​%2Fusualdestination%2Ehtm
```