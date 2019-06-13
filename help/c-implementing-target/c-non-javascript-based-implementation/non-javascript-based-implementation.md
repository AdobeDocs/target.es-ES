---
description: Información acerca de la implementación de Target en situaciones sin JavaScript, como el uso de un AdBox o un redirector.
keywords: implementación;mbox.js no javascript;AdBox;redirector;mbox
seo-description: Información acerca de la implementación de Target en situaciones sin JavaScript, como el uso de un AdBox o un redirector.
seo-title: Implementación del correo electrónico en Target
solution: Target
subtopic: Primeros pasos
title: Implementación del correo electrónico en Target
topic: Standard
uuid: 07abc419-0253-47c6-80b8-0bd0734d2c9d
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Correo electrónico: implementación de Target{#email-implement-target}

Información acerca de la implementación de Target en situaciones sin JavaScript, como el uso de un AdBox o un redirector.

Puede realizar un seguimiento de las visitas a los anuncios y otro contenido sin conexión. También se puede identificar al mismo usuario en el sitio y fuera de él y ofrecer una experiencia coherente en la web. Con una sola dirección URL, el AdBox permite realizar pruebas sin JavaScript, [!DNL at.js] o [!DNL mbox.js].

Un AdBox es útil para sitios que no tienen [!DNL at.js] o [!DNL mbox.js], como los de empresas afiliadas. En caso de que la actividad necesite elementos creativos dinámicos (por ejemplo, debe mostrar un producto en la publicidad que no llegó a completarse en el carro de compras), no podrá usar un AdBox.

Tanto la publicidad de AdBox como redirector se pueden usar en cualquier tipo de actividad. En la siguiente tabla se comparan un redirector y un AdBox, y se indica cuándo usar cada uno de ellos:

|  | Finalidad | Cuándo se utiliza | Estructura de la dirección URL | Tipo de oferta | Contenido de la oferta |
|--- |--- |--- |--- |--- |--- |
| AdBox | Devuelve distintas imágenes a la publicidad | Cambiar el contenido de una publicidad | `clientcode​.tt.​omtrdc​.net/​m2​/​clientcode/ubox/​image?` | oferta de redireccionamiento | Dirección URL de una imagen |
| Redirector | Redirige a un visitante a otra página Web | Cambiar la página de aterrizaje de una publicidad | `clientcode​.tt.omtrdc.net/​m2/clientcode​/ubox/page?` | oferta de redireccionamiento | Dirección URL de una página |

## Restricciones {#section_38F559DCF1324271926608BCD4AB1227}

* No existe la posibilidad de que se produzcan tiempos de espera de lado de cliente, como sucede con los mboxes estándar. Si Target está completamente inactivo, los visitantes de la publicidad no verán ningún contenido, ni siquiera el predeterminado.
* Para realizar el seguimiento de las visitas se emplean cookies de terceros. Si los PCId son distintos, de forma predeterminada las cookies de terceros del visitante se combinan con cualquier perfil de origen existente.
* Para usar cookies de origen en el propio AdBox, será necesario transmitir la sesión de mBox en la dirección URL. Póngase en contacto con el representante de la cuenta para llevar esto a cabo.
* Para usar cookies de origen con objeto de rastrear clics de publicidad, transmita la sesión de mbox en la dirección URL. Póngase en contacto con el representante de la cuenta para llevar esto a cabo.
* Para usar más de un AdBox en la misma página, deberá transmitir la sesión de mbox en la dirección URL. Póngase en contacto con el representante de la cuenta para llevar esto a cabo. Se puede tener un AdBox y un vínculo de redirector en la misma página (ya que, en realidad, el redirector se encuentra en otra página).

