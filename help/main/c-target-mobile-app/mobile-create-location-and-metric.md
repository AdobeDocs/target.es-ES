---
keywords: aplicación móvil;ubicación de aplicación móvil;aplicación móvil de Target;ubicaciones de Target móvil;métricas de éxito de aplicaciones móviles
description: Ver código de muestra para aprender a crear ubicaciones y métricas de éxito en aplicaciones de iOS, para que pueda usar el Adobe [!DNL Target] para personalizar y optimizar su aplicación.
title: ¿Cómo puedo crear? [!DNL Target] ¿Ubicaciones y métricas de éxito en una aplicación de iOS?
feature: Implement Mobile
role: Developer
exl-id: c2f05478-b019-47a7-b1a5-3783929e6732
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 82%

---

# iOS: cree un [!DNL Target] ubicación y métrica de éxito

Para usar Target en una aplicación móvil, cree una ubicación y una métrica de éxito.

Esta sección incluye código de ejemplo que se puede usar como plantilla en la aplicación. Los ejemplos de esta sección contienen código para iOS. Los mismos patrones sirven para Android. La sintaxis de Android se encuentra en la guía [](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/target-main.html)SDK para Android 4.x para soluciones de Experience Cloud.

>[!NOTE]
>
>Consulte la [Documentación móvil](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-target-methods.html) para obtener una lista de todos los métodos de Target disponibles.

Para crear una ubicación de Target en la aplicación y realizar una solicitud, existen dos métodos principales:

* `targetCreateRequestWithName`
* `targetLoadRequest`

1. Cree una ubicación de Target.

   Esta es un ejemplo de llamada para crear una solicitud:

   ```
   // make your request 
   ADBTargetLocationRequest *myRequest = [ADBMobile targetCreateRequestWithName:@"heroBanner" 
                                                    defaultContent:@"default.png" 
                                                    parameters:nil];
   ```

   | Parámetro | Descripción |
   |---|---|
   | `ADBTargetLocationRequest *myRequest` | Sustituya `myRequest` por el nombre de su `targetLocation` en la aplicación. |
   | `targetCreateRequestWithName:@"heroBanner"` | Sustituya `heroBanner` por el nombre de su `targetLocation` en Target. Es igual que el nombre del mbox. Este banner a pantalla completa aparece en la interfaz de Target. |
   | `defaultContent:@"default.png"` | Sustituya `default.png` por el valor que usa la aplicación cuando Target no responde. |
   | `parameters:nil` | Indique los parámetros de perfil o mbox. Encontrará más información en la sección “Pasar datos personalizados”. |

   Esta es un ejemplo de llamada para cargar una solicitud:

   ```
   // load your request 
   [ADBMobile targetLoadRequest:myRequest callback:^(NSString *content) { 
                                        // do something with content 
                                        heroImage.image = [UIImage imageNamed:content]; 
   }];
   ```

   | Parámetro | Descripción |
   |---|---|
   | `targetLoadRequest:myRequest` | Sustituya `myRequest` por el nombre de su `targetLocation` en la aplicación. |
   | `NSString *content` | Sustituya “content” por el contenido que regresa de Adobe. La cadena puede ser XML, JSON o texto sin formato. Use esta sección del código para definir variables, establecer rutas de imágenes, ver flujos de controladores, puntos de transacción o cualquier otra cosa que quiera hacer. Target devolverá el contenido introducido en la interfaz de usuario en el mismo formato. |
   | `heroImage.image = [UIImage imageNamed:content];` | Por ejemplo, tome el contenido y fije una ruta para una imagen a pantalla completa. |

1. Cree una métrica de éxito.

   Se puede usar el método `targetCreateOrderConfirmRequestWithName` para rastrear una métrica de conversión/éxito en la aplicación.

   ```
   ADBTargetLocationRequest *req = [ADBMobile targetCreateOrderConfirmRequestWithName: "orderConfirm" 
                                              orderId: orderId 
                                              orderTotal: @"39.95" 
                                              productPurchasedId: _galleryItem.title 
                                              parameters: nil]; 
   [ADBMobile targetLoadRequest: req callback: nil];
   ```

   | Parámetro | Descripción |
   |---|---|
   | `orderId` | Sustitúyalo por una variable dinámica que represente un ID de pedido único. |
   | `@"39.95"` | Sustitúyalo por una variable dinámica que represente un total de pedido único. |
   | `_galleryItem.title` | Sustitúyala por una variable dinámica que represente una lista de productos comprados separados por comas. |
   | `parameters: nil` | Diccionario opcional de parámetros adicionales. |

1. Compile la aplicación.

   Resultado del paso: cuando haya creado una ubicación de Target y haya etiquetado una métrica de éxito, cree una prueba A/B. La actividad se puede crear con el compositor de experiencias basadas en formulario.