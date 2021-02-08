---
keywords: implementación;mbox.js no javascript;AdBox;redirector;mbox
description: Obtenga información sobre cómo implementar Adobe Target en situaciones que no sean de JavaScript, como el uso de un adbox o un redirector.
title: ¿Cómo implemento Destinatario para correo electrónico?
feature: Implement Email
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 77%

---


# Correo electrónico: implementación de Target{#email-implement-target}

Información acerca de la implementación de Target en situaciones sin JavaScript, como el uso de un AdBox o un redirector.

Puede realizar un seguimiento de las visitas a los anuncios y otro contenido sin conexión. También se puede identificar al mismo usuario en el sitio y fuera de él y ofrecer una experiencia coherente en la web. Con una sola dirección URL, el AdBox permite realizar pruebas sin JavaScript, [!DNL at.js] o [!DNL mbox.js].

Un AdBox es útil para sitios que no tienen [!DNL at.js] o [!DNL mbox.js], como los de empresas afiliadas. En caso de que la actividad necesite elementos creativos dinámicos (por ejemplo, debe mostrar un producto en la publicidad que no llegó a completarse en el carro de compras), no podrá usar un AdBox.

Tanto la publicidad de AdBox como redirector se pueden usar en cualquier tipo de actividad. En la siguiente tabla se comparan un redirector y un AdBox, y se indica cuándo usar cada uno de ellos:

|  | Finalidad | Cuándo se utiliza | Estructura de la dirección URL | Tipo de oferta | Contenido de la oferta |
|--- |--- |--- |--- |--- |--- |
| AdBox | Devuelve distintas imágenes a la publicidad | Cambiar el contenido de una publicidad | `clientcode&#x200B;.tt.&#x200B;omtrdc&#x200B;.net/&#x200B;m2&#x200B;/&#x200B;clientcode/ubox/&#x200B;image?` | oferta de redireccionamiento | Dirección URL de una imagen |
| Redirector | Redirige a un visitante a otra página Web | Cambiar la página de aterrizaje de una publicidad | `clientcode&#x200B;.tt.omtrdc.net/&#x200B;m2/clientcode&#x200B;/ubox/page?` | oferta de redireccionamiento | Dirección URL de una página |

## Prácticas recomendadas de seguridad {#security}

Tenga en cuenta que con Redirector, puede correr el riesgo de sufrir una vulnerabilidad de redireccionamiento abierto. Para evitar el uso no autorizado de vínculos de redirector por parte de terceros, le recomendamos que utilice &quot;hosts autorizados&quot; para la lista de permitidos de los dominios de URL de redireccionamiento predeterminados. Destinatario utiliza los hosts en dominios de lista de permitidos a los que desea permitir las redirecciones. Para obtener más información, consulte [Creación de Listas de permitidos que especifican hosts autorizados para enviar llamadas de mbox a Destinatario](/help/administrating-target/hosts.md#allowlist) en *Hosts*.

## Restricciones {#section_38F559DCF1324271926608BCD4AB1227}

* No existe la posibilidad de que se produzcan tiempos de espera de lado de cliente, como sucede con los mboxes estándar. Si Target está completamente inactivo, los visitantes de la publicidad no verán ningún contenido, ni siquiera el predeterminado.
* Para realizar el seguimiento de las visitas se emplean cookies de terceros. Si los PCId son distintos, de forma predeterminada las cookies de terceros del visitante se combinan con cualquier perfil de origen existente.
* Para usar cookies de origen en el propio AdBox, será necesario transmitir la sesión de mBox en la dirección URL. Póngase en contacto con el representante de la cuenta para llevar esto a cabo.
* Para usar cookies de origen con objeto de rastrear clics de publicidad, transmita la sesión de mbox en la dirección URL. Póngase en contacto con el representante de la cuenta para llevar esto a cabo.
* Para usar más de un AdBox en la misma página, deberá transmitir la sesión de mbox en la dirección URL. Póngase en contacto con el representante de la cuenta para llevar esto a cabo. Se puede tener un AdBox y un vínculo de redirector en la misma página (ya que, en realidad, el redirector se encuentra en otra página).