---
keywords: aplicación móvil;enviar datos de aplicación móvil;aplicación móvil de target;datos de usuario móviles personalizados;datos personalizados de aplicación móvil
description: Obtenga información sobre cómo enviar información adicional sobre la ubicación o el usuario al Adobe [!DNL Target] como pares nombre-valor para ayudarle a crear audiencias personalizadas.
title: ¿Cómo puedo enviar datos de usuario personalizados en una aplicación de iOS?
feature: Implement Mobile
role: Developer
exl-id: c64219ec-8d60-4d05-b2b8-103e8ffcaefc
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 90%

---

# iOS: enviar datos de usuario personalizados

Puede enviar información adicional sobre la ubicación o el usuario a Target como pares de nombre-valor.

Esta información se puede usar para compilar audiencias personalizadas (por ejemplo, de usuarios que estén a más de 25 000 millas) y en la creación de informes.

Con una llamada de Target se puede enviar dos tipos de parámetros:

* Parámetros de mbox

   Los parámetros de mbox no se conservan de una sesión a otra.
* Parámetros de perfil

   Los parámetros de perfil se almacenan en el almacén de perfiles del visitante y se conservan de una sesión a otra. Los parámetros de mbox no se conservan. Aunque algunas claves se reservan, tanto los parámetros de perfil como los de mbox pueden ser pares personalizados de clave-valor.

Aunque hay algunas claves reservadas, tanto los parámetros de perfil como los de mbox pueden contener pares personalizados de clave-valor.

1. Cree un diccionario.

   Primero, cree un diccionario con los valores que quiere enviar para pasárselos a Target. Para mayor comodidad, añádalo dentro del método `welcomeMessageCampaign` para no tener que preocuparse del ámbito.

   A continuación, le mostramos un diccionario de ejemplo. Puede copiarlo y pegarlo en `(void)welcomeMessageCampaign`. En este ejemplo, los valores de claves como `userLevel` y `userMiles` están insertados en el código. En general, se pasan las variables correspondientes.

   ```
   NSDictionary *targetParams = [[NSDictionary alloc] initWithObjectsAndKeys: 
                                 @"platinum",@"userLevel", 
                                 @26500,@"userMiles", 
                                 @"1067007",@"entity.id", 
                                 @"dealsapp.qa", @"host", 
                                 @"fashion",@"entity.categoryId", 
                                 @"millenial", @"profile.persona", 
                                 @"cohort_5", @"profile.cohort", 
                                 nil];
   ```

   * Las claves que tienen el prefijo “profile” (por ejemplo, `profile.persona`) se almacenan en el perfil del usuario.

      Estos atributos de perfil se pueden usar en una variedad de actividades y canales.

   * Las claves que no tienen prefijo (por ejemplo, `userMiles`) son parámetros de mbox.

      Estos parámetros solo están disponibles durante la sesión.

   * Las claves que tienen el prefijo “entity” (por ejemplo, `entity.category.id`) se usan en las recomendaciones de productos.

1. Compruebe los datos.
   1. En la aplicación `didFinishLaunchingWithOptions`, quite la marca de comentario o añada `[ADBMobile setDebugLogging:YES];`.

      De este modo, se imprimen registros de depuración detallados.
   1. Compile la aplicación.
   1. Compruebe que los parámetros se pasen en la llamada de Target.

      Busque el nombre de la ubicación de Target en la consola de depuración. Verá una llamada a `YOUR-CLIENT-CODE.tt.omtrdc.net` con todos los parámetros que acaba de pasar.

      ![](assets/mobile-debug.png)
   Puede compilar audiencias y restringir o segmentar la visualización de contenido mediante estos parámetros en Target Standard.
