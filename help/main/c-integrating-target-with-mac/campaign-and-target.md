---
keywords: Información general y referencia
description: Aprenda a utilizar Adobe [!DNL Target] con Adobe Campaign para optimizar el contenido del correo electrónico.
title: ¿Cómo puedo integrarme? [!DNL Target] con Adobe Campaign?
feature: Integrations
exl-id: 605b8fe4-e32f-43bc-9131-245008b655e1
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 41%

---

# Integrar [!DNL Target] con Adobe Campaign

Uso [!DNL Target] con [!DNL Adobe Campaign] para optimizar el contenido del correo electrónico.

Para optimizar el contenido del correo electrónico, puede crear una oferta de redireccionamiento en [!DNL Target]y, a continuación, utilice [!DNL Adobe Campaign] para administrar las ofertas de correo electrónico. Por ejemplo, puede mostrar diferentes ofertas para destinatarios hombres y mujeres.

La integración tiene lugar cuando se abre el correo electrónico. Cuando el cliente abre el correo electrónico, se realiza una llamada a [!DNL Target] y aparece una versión dinámica del contenido. El contenido está formado por una imagen estática compatible con todos los navegadores. [!DNL Target] hace un seguimiento de la reacción ante la oferta en el nivel de audiencia o de sesión y pone esos datos a su disposición en los informes de [!DNL Target]

[!DNL Target] puede hacer un seguimiento de los datos siguientes:

* Agente de usuario
* Dirección IP
* Ubicación geográfica
* Segmento asociado con el ID del visitante en [!DNL Target] (previa aprobación legal)
* Datos de [!DNL Campaign] Datamart

Existen varias limitaciones:

* Como solo se puede usar una imagen, el contenido no se puede personalizar.
* El seguimiento no está consolidado en [!DNL Adobe Campaign].
* No se puede unificar la experiencia de usuario.

Utilice ambos [!DNL Target] y [!DNL Campaign] para configurar diferentes partes de la integración:

* El cuadro sin procesar y la experiencia en [!DNL Target]

>[!NOTE]
>
>Cuando utilice rawbox y [!DNL Target], consulte el aviso de seguridad importante que encontrará en [Creación de listas de hosts con autorización para enviar llamadas de mbox a Target](/help/main/administrating-target/hosts.md#allowlist).

* La entrega en [!DNL Campaign]

## Antes de empezar {#section_FF19BF1BCA064260930BF6C141313B0E}

Antes de usar [!DNL Adobe Campaign] para configurar las ofertas de correo electrónico dirigidas, configure lo siguiente en [!DNL Target]:

* Dos o más [!DNL Target] ofertas de redireccionamiento

   Consulte [Crear oferta de redireccionamiento](/help/main/c-experiences/c-manage-content/offer-redirect.md).

* A [!DNL Target] actividad con una experiencia para cada oferta y el [métrica de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md).

   Consulte [Redireccionar a una dirección URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md).

Inicie la actividad en [!DNL Target] antes de configurar la variable [!DNL Campaign] de la integración.

## Incluir un [!DNL Target] oferta en una [!DNL Adobe Campaign] email {#section_B201BBE27A704E18AF0D553F35695837}

1. Cree un correo electrónico en [!DNL Adobe Campaign].
1. En las propiedades del correo electrónico, haga clic en **[!UICONTROL Incluir]** > **[!UICONTROL Imagen dinámica proporcionada por Adobe Target]**.
1. Seleccione la imagen predeterminada entre los recursos compartidos.
1. Especifique la ubicación (rawbox).
1. Agregue el resto de los parámetros de toma de decisiones, como puede ser el sexo del destinatario.
1. Seleccione por lo menos un destinatario para cada oferta (en este caso, un hombre y una mujer) y previsualice el correo electrónico.
1. En [!DNL Campaign], defina la variable [!DNL Target] Servidor perimetral que utiliza para controlar la actividad y el nombre del inquilino.
1. Especifique la cuenta externa utilizada para la variable [!DNL Adobe Experience Cloud] para acceder a los recursos de la sección [!DNL Experience Cloud].

Para obtener más información, consulte [!DNL Adobe Campaign] documentación.

## Vídeo: Integrar [!DNL Target] con [!DNL Campaign]

>[!VIDEO](https://video.tv.adobe.com/v/35149)
