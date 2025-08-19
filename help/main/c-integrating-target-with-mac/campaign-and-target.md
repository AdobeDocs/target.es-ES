---
keywords: Información general y referencia
description: Aprenda a utilizar Adobe [!DNL Target] con Adobe Campaign para optimizar el contenido del correo electrónico.
title: ¿Cómo puedo integrar  [!DNL Target] con Adobe Campaign?
feature: Integrations
exl-id: 605b8fe4-e32f-43bc-9131-245008b655e1
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 32%

---

# Integrar [!DNL Target] con Adobe Campaign

Use [!DNL Target] con [!DNL Adobe Campaign] para optimizar el contenido del correo electrónico.

Para optimizar el contenido del correo electrónico, puede crear una oferta de redireccionamiento en [!DNL Target] y, a continuación, utilizar [!DNL Adobe Campaign] para administrar las ofertas de correo electrónico. Por ejemplo, puede mostrar diferentes ofertas para destinatarios hombres y mujeres.

La integración tiene lugar cuando se abre el correo electrónico. Cuando el cliente abre el correo electrónico, se realiza una llamada a [!DNL Target] y aparece una versión dinámica del contenido. El contenido está formado por una imagen estática compatible con todos los navegadores. [!DNL Target] realiza un seguimiento de la reacción a la oferta en el nivel de audiencia o de sesión, y esos datos están disponibles en [!DNL Target] informes.

[!DNL Target] puede realizar el seguimiento de los siguientes datos:

* Agente de usuario
* Dirección IP
* Ubicación geográfica
* Segmento asociado con el ID del visitante en [!DNL Target] (sujeto a aprobación legal)
* Datos del datamart [!DNL Campaign]

Existen varias limitaciones:

* Como solo se puede usar una imagen, el contenido no se puede personalizar.
* El seguimiento no está consolidado en [!DNL Adobe Campaign].
* No se puede unificar la experiencia de usuario.

Use [!DNL Target] y [!DNL Campaign] para configurar diferentes partes de la integración:

* La casilla sin procesar y la experiencia en [!DNL Target]

>[!NOTE]
>
>Cuando utilice rawbox y [!DNL Target], consulte el aviso de seguridad importante que encontrará en [Creación de listas de hosts con autorización para enviar llamadas de mbox a Target](/help/main/administrating-target/hosts.md#allowlist).

* La entrega en [!DNL Campaign]

## Antes de empezar {#section_FF19BF1BCA064260930BF6C141313B0E}

Antes de usar [!DNL Adobe Campaign] para configurar sus ofertas de correo electrónico de destino, configure lo siguiente en [!DNL Target]:

* Dos o más [!DNL Target] ofertas de redireccionamiento

  Ver [Crear oferta de redireccionamiento](/help/main/c-experiences/c-manage-content/offer-redirect.md).

* Una actividad [!DNL Target] con una experiencia para cada oferta y la [métrica de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md) deseada.

  Consulte [Redireccionar a una dirección URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md).

Inicie la actividad en [!DNL Target] antes de configurar la parte [!DNL Campaign] de la integración.

## Incluir una oferta [!DNL Target] en un correo electrónico [!DNL Adobe Campaign] {#section_B201BBE27A704E18AF0D553F35695837}

1. Crear un correo electrónico en [!DNL Adobe Campaign].
1. En las propiedades del correo electrónico, haga clic en **[!UICONTROL Include]** > **[!UICONTROL Dynamic image served by Adobe Target]**.
1. Seleccione la imagen predeterminada entre los recursos compartidos.
1. Especifique la ubicación (rawbox).
1. Agregue el resto de los parámetros de toma de decisiones, como puede ser el sexo del destinatario.
1. Seleccione por lo menos un destinatario para cada oferta (en este caso, un hombre y una mujer) y previsualice el correo electrónico.
1. En [!DNL Campaign], defina el servidor de Edge [!DNL Target] que está utilizando para controlar la actividad y el nombre del inquilino.
1. Especifique la cuenta externa utilizada para [!DNL Adobe Experience Cloud] para que pueda tener acceso a los recursos en [!DNL Experience Cloud].

Para obtener más información, consulte la documentación de [!DNL Adobe Campaign].

## Vídeo: Integrar [!DNL Target] con [!DNL Campaign]

>[!VIDEO](https://video.tv.adobe.com/v/35149)
