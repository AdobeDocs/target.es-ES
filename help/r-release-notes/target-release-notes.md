---
description: Estas notas de revisión proporcionan información sobre características, mejoras y correcciones de las últimas o más próximas [! Versiones de DNL Adobe Target.
keywords: notas de la versión
seo-description: Estas notas de revisión proporcionan información sobre características, mejoras y correcciones de las últimas o más próximas [! Versiones de DNL Adobe Target.
seo-title: Notas de la versión de Adobe Target (versión preliminar)
solution: Target
title: Notas de la versión de Target (versión previa)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 7cdff6e1beca45a4900090bc91a38be7e000f289

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

En estas notas de la versión se proporciona información acerca de las funciones, las mejoras, las correcciones y los problemas conocidos de las últimas o de las próximas versiones de [!DNL Adobe Target].

**Última actualización: 11 de julio de 2019**

>[!NOTE]
>
>Las presentes notas de la versión contienen información previa al lanzamiento. Las fechas de lanzamiento, las funciones y demás información están sujetos a cambios sin previo aviso. Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma o diferente, según la hora de las versiones.
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Target Standard/Premium 19.7.1 (23 de julio de 2019) {#tgt-19-7-1}

Esta versión incorpora las siguientes nuevas funciones y mejoras:

| Función / Mejora | Descripción |
| --- | --- |
| Compositor de experiencias visuales (VEC) | When you click an image then click [!UICONTROL Replace With], two new options display:<ul><li>**HTML**: Puede reemplazar una imagen con HTML para darle un control total del elemento sin necesidad de seleccionar el elemento principal para acceder a la opción HTML.</li><li>**Fragmento de experiencias**: Puede reemplazar una imagen con un fragmento [de experiencia de Adobe Experience Manager (AEM)](/help/c-experiences/c-manage-content/aem-experience-fragments.md) para insertar rápidamente elementos creados en AEM en actividades de Target.</li></ul>(TGT-34097) |
| Compositor de experiencias visuales para aplicaciones móviles | Aparece un nuevo panel Modificaciones en el VEC de la aplicación móvil que muestra los elementos configurados para el rastreo de clics. (TGT-31741) |
| ![Premium badgerecommendations](/help/assets/premium.png)<br>in A/B Test and Experience Targeting (XT) actividades | El estado Oferta de Recommendations (algoritmo) aparece en la página Información general de las actividades de prueba A/B y XT que contienen ofertas de Recomendaciones. Los estados incluyen: Resultados Ready, Resultados no preparados y Error de fuente. (TGT-33649) |
| Compatibilidad de seguimiento entre dominios para at. js 2.0 + a través de la biblioteca Experience Cloud ID (ECID) | Anteriormente, el seguimiento entre dominios no era compatible con at. js 2.*x*. Con esta versión, los clientes que utilizan at. js 2.0 o superior pueden utilizar el seguimiento entre dominios a través de la biblioteca ECID. La biblioteca ECID debe instalarse en la página junto con at. js 2.0 o superior para que funcione el seguimiento entre dominios. [Se debe usar la biblioteca de ID de Experience Cloud 4.3.0 +](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) . |
| Compatibilidad de Target con ITP 2.1 y ITP 2.2 de Apple a través de la biblioteca Experience Cloud ID (ECID) 4.3 | Actualmente, los clientes de Target pueden mitigar ITP 2.1 y ITP 2.2 de Apple mediante el uso del programa de certificación CNAME de Adobe. With this release, Target introduces a seamless integration with the ECID library 4.3, which leverages a server-side cookie to mitigate ITP 2.1 and ITP 2.2. It is highly recommended that Target customers deploy [ECID library 4.3+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) in conjunction with Target’s JavaScript library to mitigate any future ITP releases. La biblioteca ECID continuará perfeccionando las mejoras que proporcionan una solución sólida para las políticas de cookie que cambian constantemente ingresadas por los navegadores. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
