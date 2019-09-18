---
description: Utilice Target con Adobe Campaign para optimizar el contenido del correo electrónico.
keywords: Información general y referencia
seo-description: Utilice Target con Adobe Campaign para optimizar el contenido del correo electrónico.
seo-title: Integración de Target con Adobe Campaign
solution: Target
title: Integración de Target con Adobe Campaign
topic: Standard
uuid: 1a5b70e6-d501-4b52-bec8-4ae2c419d331
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# Integración de Target con Adobe Campaign{#integrate-target-with-adobe-campaign}

Utilice Target con Adobe Campaign para optimizar el contenido del correo electrónico.

Para optimizar el contenido del correo electrónico (por ejemplo, para mostrar diferentes ofertas para destinatarios hombres o mujeres), puede crear una oferta de redireccionamiento en Target y después usar Adobe Campaign para administrar las ofertas de correo electrónico.

La integración tiene lugar cuando se abre el correo electrónico. Cuando el cliente lo abre, se realiza una llamada a Target y aparece una versión dinámica del contenido. El contenido está formado por una imagen estática compatible con todos los navegadores. Target hace un seguimiento de la reacción ante la oferta en el nivel de audiencia o de sesión y pone esos datos a su disposición en los informes de Target.

Target puede hacer un seguimiento de los datos siguientes:

* Agente de usuario
* Dirección IP
* Ubicación geográfica
* Segmento asociado con el ID del visitante en Target (si recibe aprobación legal)
* Datos del datamart de Campaign

Existen varias limitaciones:

* Como solo se puede usar una imagen, el contenido no se puede personalizar.
* El seguimiento no se consolida en Adobe Campaign.
* No se puede unificar la experiencia de usuario.

   Debe usar tanto Target como Campaign para configurar partes diferentes de la integración:

   * El rawbox y la experiencia en Target
   * La entrega en Campaign

## Antes de empezar  {#section_FF19BF1BCA064260930BF6C141313B0E}

Antes de usar Adobe Campaign para configurar las ofertas de correo electrónico segmentadas, configure los elementos siguientes en Target:

* Dos o más ofertas de redireccionamiento de Target

   See [Create redirect offer](/help/c-experiences/c-manage-content/offer-redirect.md).
* Una actividad de Target con una experiencia para cada oferta y la [métrica de éxito](/help/c-activities/r-success-metrics/success-metrics.md) deseada.

   Consulte [Redireccionar a una dirección URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md).

Inicie la actividad en Target antes de configurar la parte de integración de Campaign.

## Incluir una oferta de Target en un correo electrónico de Adobe Campaign  {#section_B201BBE27A704E18AF0D553F35695837}

1. Cree un correo electrónico en Adobe Campaign.
1. En las propiedades del correo electrónico, haga clic en **[!UICONTROL Incluir]** &gt; **[!UICONTROL Imagen dinámica proporcionada por Adobe Target]**.
1. Seleccione la imagen predeterminada entre los recursos compartidos.
1. Especifique la ubicación (rawbox).
1. Agregue el resto de los parámetros de toma de decisiones, como puede ser el sexo del destinatario.
1. Seleccione por lo menos un destinatario para cada oferta (en este caso, un hombre y una mujer) y previsualice el correo electrónico.
1. En Campaign, defina el servidor de Target Edge que va a utilizar para controlar la actividad y el nombre del inquilino.
1. Especifique la cuenta externa que se usa para Experience Cloud, de modo que pueda acceder a los recursos de Experience Cloud.

Para obtener más información, consulte la documentación de Adobe Campaign.
