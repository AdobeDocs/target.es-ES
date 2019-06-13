---
description: Para usar Target en una aplicación móvil, cree una ubicación y una métrica de éxito.
keywords: aplicación móvil;ubicación de aplicación móvil;aplicación móvil de Target;ubicaciones de Target móvil;métricas de éxito de aplicaciones móviles
seo-description: Para usar Target en una aplicación móvil, cree una ubicación y una métrica de éxito.
seo-title: 'iOS: crear una ubicación y una métrica de éxito de Target'
title: 'iOS: crear una ubicación y una métrica de éxito de Target'
topic: Target
uuid: dc39260c-8222-42b3-9f6b-f83be30e3210
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# iOS: crear una ubicación y una métrica de éxito de Target{#ios-create-a-target-location-and-success-metric}

Para usar Target en una aplicación móvil, cree una ubicación y una métrica de éxito.

Esta sección incluye código de ejemplo que se puede usar como plantilla en la aplicación. Los ejemplos de esta sección contienen código para iOS. Los mismos patrones sirven para Android. La sintaxis específica de Android se encuentra en la guía de soluciones [Android SDK 4.x para Experience Cloud](https://marketing.adobe.com/resources/help/es_ES/mobile/android/target_main.html).

>[!NOTE]
>
>Consulte la [Documentación móvil ](https://marketing.adobe.com/resources/help/es_ES/mobile/ios/c_target_methods.html) para obtener una lista de todos los métodos de Target disponibles.

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
