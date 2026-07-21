---
title: Extensión de marcas para la guía de integración de iOS
description: Obtenga información sobre cómo integrar la extensión Flags con Adobe Experience Platform Mobile SDK en iOS.
hide: true
source-git-commit: eeba7af62ab101e687852ce993a001832ce4a83b
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 5%

---

# Extensión de marcas para iOS {#ios-extension-integration-guide}

En esta guía se describe cómo integrar la extensión Flags con Adobe Experience Platform Mobile SDK en iOS.

## Requisitos previos {#prerequisites}

Antes de implementar la extensión Banderas, asegúrese de lo siguiente:

* Una propiedad móvil configurada en [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/#/data-collection)
* La extensión de marcas instalada y configurada en la propiedad móvil
* Un ID de organización de Adobe Experience Cloud
* Destino mínimo de implementación: iOS 12.0

## Dependencias de extensión {#extension-dependencies}

La extensión Flags requiere las siguientes extensiones de Adobe Experience Platform:

| Extensión | Descripción | Requerido |
|---|---|---|
| Mobile Core | Proporciona funcionalidad principal, incluida la configuración y el procesamiento de eventos | Sí |
| Ciclo de vida | Recopila datos sobre el ciclo vital y la sesión de la aplicación para Mobile SDK | Sí |
| Edge Network | Habilita la comunicación con Adobe Experience Platform Edge Network | Sí |
| Edge Identity | Habilita la administración de identidades desde una aplicación móvil al usar la extensión de Edge Network | Sí |

Asegúrese de que estas extensiones estén instaladas en la propiedad móvil de recopilación de datos y se incluyan en las dependencias de la aplicación.

## Configuración de la extensión Flags en la recopilación de datos {#configure}

### Instalación de la extensión {#install-extension}

1. Inicie sesión en [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection).
1. Seleccione la ficha **Etiquetas** y elija su propiedad móvil.
1. Vaya a **Extensiones** > **Catálogo**.
1. Busque **extensión Flags** y seleccione **Instalar**.
1. Configure las opciones de extensión:

   | Configuración | Descripción |
   |---|---|
   | ID de la aplicación | Un identificador único para su aplicación en Banderas |

1. Seleccione **Guardar**.
1. Siga el [proceso de publicación](https://experienceleague.adobe.com/es/docs/experience-platform/tags/publish/overview) para actualizar la configuración.

### Obtener el ID del archivo de entorno {#environment-file-id}

1. En su propiedad móvil, vaya a **Entornos**.
1. Seleccione el icono de cuadro debajo de la columna **Instalar** para su entorno.
1. En el cuadro de diálogo **Instrucciones de instalación de Mobile**, copie el **Id. de archivo de entorno**.

## Añadir la extensión de marcas a la aplicación {#add-to-app}

### Añadir dependencias {#add-dependencies}

Agregue las dependencias de Mobile SDK al proyecto. La extensión Flags requiere Mobile Core y las extensiones relacionadas con Edge que se enumeran a continuación.

#### Uso Del Administrador De Paquetes Swift {#swift-package-manager}

En Xcode, seleccione **Archivo** > **Agregar paquetes** y agregue las siguientes direcciones URL del paquete de Adobe Experience Platform Mobile SDK:

| Paquete | Dirección URL |
|---|---|
| AEPCore | `https://github.com/adobe/aepsdk-core-ios.git` |
| AEPEdge | `https://github.com/adobe/aepsdk-edge-ios.git` |
| AEPdgeIdentity | `https://github.com/adobe/aepsdk-edgeidentity-ios.git` |

Cuando se le solicite, seleccione las siguientes bibliotecas para añadirlas a su destino:

* `AEPCore`, `AEPLifecycle` (de `aepsdk-core-ios`)
* `AEPEdge` (de `aepsdk-edge-ios`)
* `AEPEdgeIdentity` (de `aepsdk-edgeidentity-ios`)

Utilice AEPCore 5.8.0 o posterior.

>[!NOTE]
>
>Al agregar un paquete en Xcode, elija una regla de dependencia para cada paquete (por ejemplo **Hasta la siguiente versión principal**), que recoge nuevas versiones menores y de parches automáticamente al excluir la siguiente versión principal. Para ver las últimas versiones, consulte la página de versiones de cada extensión en GitHub.

### Adición del paquete Flags {#add-flags-package}

Utilice el paquete Swift o el método de integración XCFramework para un destino de aplicación, no ambos.

#### Para un proyecto Xcode sin un archivo Package.swift {#xcode-project}

1. En Xcode, seleccione **Archivo** > **Agregar paquetes**.
1. Seleccione **Agregar local**.
1. Seleccione el directorio `Packages/AEPFlags` proporcionado que contiene `Package.swift`.
1. Agregue la biblioteca `AEPFlags` al destino de la aplicación.

Xcode almacena la referencia de paquete local en el proyecto, por lo que la aplicación no necesita su propio archivo `Package.swift`.

#### Para un proyecto con un archivo Package.swift {#package-swift-project}

En el manifiesto existente, agregue `AEPFlags` a las dependencias de destino de la aplicación y agregue el destino binario mediante la dirección URL y la suma de comprobación del manifiesto proporcionado:

```swift
targets: [
    .target(
        name: "YourApp",
        dependencies: [
            "AEPFlags"
        ]
    ),
    .binaryTarget(
        name: "AEPFlags",
        url: "<AEPFlags binary URL>",
        checksum: "<AEPFlags binary checksum>"
    )
]
```

Swift Package Manager resuelve el destino binario para las compilaciones de Xcode, CI y archivo locales.

#### Agregar directamente el XCFramework {#xcframework}

También puede arrastrar el(la) `AEPFlags.xcframework` proporcionado(a) al navegador del proyecto Xcode y agregarlo a su destino de aplicación. En **General** > **Marcos, bibliotecas y contenido incrustado**, establezca el marco de trabajo en **Incrustar y firmar**.

### Inicialización de SDK {#initialize-sdk}

Registre las extensiones de Mobile SDK en `AppDelegate` antes de llamar a cualquier API de Flags. Registre `Flag` después de usar Identity, Edge y Lifecycle y, a continuación, configure SDK con el ID de archivo de entorno de su propiedad móvil.

#### Registro y configuración de extensiones {#register-configure}

>[!IMPORTANT]
>
>Para aplicaciones de producción, use solo el nivel de registro `.error`; no use `.debug` ni `.trace` en compilaciones de versiones.

**Swift**

```swift
// AppDelegate.swift
import AEPCore
import AEPLifecycle
import AEPEdge
import AEPEdgeIdentity
import AEPFlags
import UIKit

final class AppDelegate: NSObject, UIApplicationDelegate {

    func application(_: UIApplication,
                      didFinishLaunchingWithOptions _: [UIApplication.LaunchOptionsKey: Any]? = nil) -> Bool {
        // Production: use .error only. Do not use .debug or .trace in release builds.
        MobileCore.setLogLevel(.error)

        MobileCore.registerExtensions([
            Identity.self,
            Edge.self,
            Lifecycle.self,
            Flag.self
        ]) {
            MobileCore.configureWith(appId: "YOUR_ENVIRONMENT_FILE_ID")
            MobileCore.lifecycleStart(additionalContextData: nil)
        }

        return true
    }
}
```

**Objective-C**

```objc
// AppDelegate.m
#import "AppDelegate.h"
@import AEPCore;
@import AEPLifecycle;
@import AEPEdge;
@import AEPEdgeIdentity;
@import AEPFlags;

@implementation AppDelegate

- (BOOL)application:(UIApplication *)application
    didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {

    // Production: use AEPLogLevelError only. Do not use Debug or Trace in release builds.
    [AEPMobileCore setLogLevel:AEPLogLevelError];

    [AEPMobileCore registerExtensions:@[
        AEPMobileEdgeIdentity.class,
        AEPMobileEdge.class,
        AEPMobileLifecycle.class,
        AEPMobileFlag.class
    ] completion:^{
        [AEPMobileCore configureWithAppId:@"YOUR_ENVIRONMENT_FILE_ID"];
        [AEPMobileCore lifecycleStart:nil];
    }];

    return YES;
}

@end
```

## Contexto de evaluación {#evaluation-context}

`FeatureEvaluationContext` incluye atributos de segmentación (utilizados para la coincidencia de reglas de indicador).

| Parámetro | Requerido | Descripción |
|---|---|---|
| `attributes` | No | `[String: [String]]`. Clave es el nombre de atributo de contexto utilizado por las reglas de marcador (por ejemplo `locale`, `platform`, `appVersion`, `deviceType`). Value es la lista de valores de atributos candidatos para esa clave para el usuario o la sesión actual (por ejemplo `["en_US"]` o `["phone"]`). |

**Swift**

```swift
import AEPFlags

let attrs: [String: [String]] = [
    "locale": ["en_US"],
    "platform": ["IOS"],
    "appVersion": ["3.0.0"]
]

let ctx = FeatureEvaluationContext.builder()
    .withAttributes(attrs)
    .build()
```

**Objective-C**

```objc
@import AEPFlags;

NSDictionary<NSString *, NSArray<NSString *> *> *attrs = @{
    @"locale": @[@"en_US"],
    @"platform": @[@"IOS"],
    @"appVersion": @[@"3.0.0"]
};

AEPFeatureEvaluationContextBuilder *builder = [AEPFeatureEvaluationContext builder];
AEPFeatureEvaluationContext *ctx = [[builder withAttributes:attrs] build];
```

### Atributos de segmentación de muestra {#sample-attributes}

| Atributo | Descripción | Valores de ejemplo |
|---|---|---|
| `locale` | Configuración regional/idioma del usuario | `["en_US"]`, `["fr_FR"]` |
| `platform` | Identificador de plataforma | `["IOS"]` |
| `appVersion` | Versión de aplicación | `["3.0.0"]` |
| `deviceType` | Tipo de dispositivo | `["phone"]`, `["tablet"]` |

### Identidad personalizada {#custom-identity}

La extensión Flags utiliza la extensión Identity for Edge Network para la resolución de identidades. Se puede cohortar un indicador de funcionalidad en una identidad personalizada (por ejemplo, un ID de CRM o un ID de fidelidad) para que las divisiones de variante y los análisis estén vinculados a la identidad que importa a su aplicación.

El área de nombres de identidad personalizada debe estar seleccionada en la interfaz de usuario de marcas cuando se crea el indicador de funcionalidad. Para evaluar un indicador con respecto a esa identidad, la misma identidad debe estar presente en la identidad de Edge `identityMap` en el dispositivo, utilizando el área de nombres correspondiente. Proporciónelo durante la ejecución con la API Identity for Edge Network `updateIdentities`.

#### Añadir la identidad personalizada al mapa de identidad {#add-identity}

Añada la identidad en el mismo área de nombres configurada en el indicador de funcionalidad.

**Swift**

```swift
import AEPEdgeIdentity

let identityMap = IdentityMap()
identityMap.add(item: IdentityItem(id: "1111", authenticatedState: .authenticated, primary: true),
                 withNamespace: "userCRMId") // must match the namespace configured on the feature flag
Identity.updateIdentities(with: identityMap)
```

**Objective-C**

```objc
@import AEPEdgeIdentity;

AEPIdentityItem *item = [[AEPIdentityItem alloc]
    initWithId:@"1111"
    authenticatedState:AEPAuthenticatedStateAuthenticated
    primary:YES];
AEPIdentityMap *identityMap = [[AEPIdentityMap alloc] init];
[identityMap addItem:item withNamespace:@"userCRMId"]; // must match the namespace configured on the feature flag
[AEPMobileEdgeIdentity updateIdentities:identityMap];
```

## Referencia de API {#api-reference}

### isFeatureEnabled {#is-feature-enabled}

`isFeatureEnabled` devuelve si la característica Marcas está activada o desactivada en el contexto determinado. Pase `featureKey`, un `FeatureEvaluationContext` (atributos de segmentación opcionales) y un cierre de finalización. Consulte [Contexto de evaluación](#evaluation-context).

**Firma**

*Swift*

```swift
static func isFeatureEnabled(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (Bool) -> Void
)
```

*Objective-C*

```objc
+ (void)isFeatureEnabled:(NSString *)featureKey
       evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
               completion:(void (^)(BOOL))completion;
```

**Parámetros**

| Parámetro | Tipo | Descripción |
|---|---|---|
| `featureKey` | Cadena | Clave de función a evaluar en Indicadores |
| `evaluationContext` | FeatureEvaluationContext | Incluya atributos de segmentación según sea necesario; use `FeatureEvaluationContext.builder().build()` para un contexto vacío. Consulte [Contexto de evaluación](#evaluation-context). |
| `completion` | `(Bool) -> Void` | Se llama con `true` si la característica está habilitada, `false` en caso contrario. |

**Ejemplos**

*Swift*

```swift
import AEPFlags

Flag.isFeatureEnabled(
    "new-flag",
    evaluationContext: ctx
) { isEnabled in
    if isEnabled {
        // Feature is enabled: run the feature-specific behavior
    } else {
        // Feature is disabled: fall back to the default behavior
    }
}
```

*Objective-C*

```objc
@import AEPFlags;

[AEPMobileFlag isFeatureEnabled:@"new-flag"
              evaluationContext:ctx
                      completion:^(BOOL isEnabled) {
    if (isEnabled) {
        // Feature is enabled: run the feature-specific behavior
    } else {
        // Feature is disabled: fall back to the default behavior
    }
}];
```

### getFeature {#get-feature}

`getFeature` devuelve la carga útil de la característica evaluada para el contexto proporcionado. Utilice esta API cuando necesite más de habilitar/deshabilitar y desee metadatos o valores de características.

**Firma**

*Swift*

```swift
static func getFeature(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (FeatureEvaluationResult?) -> Void
)
```

*Objective-C*

```objc
+ (void)getFeature:(NSString *)featureKey
 evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
        completion:(void (^)(AEPFeatureEvaluationResult * _Nullable))completion;
```

**Parámetros**

| Parámetro | Tipo | Descripción |
|---|---|---|
| `featureKey` | Cadena | Clave de función a evaluar en Indicadores |
| `evaluationContext` | FeatureEvaluationContext | Incluya atributos de segmentación según sea necesario; use `FeatureEvaluationContext.builder().build()` para un contexto vacío. Consulte [Contexto de evaluación](#evaluation-context). |
| `completion` | `(FeatureEvaluationResult?) -> Void` | Se llama con la carga útil de la característica evaluada; `nil` cuando no se encuentra la característica. |

**Respuesta**

*FeatureEvaluationResult*

| Campo | Tipo | Descripción |
|---|---|---|
| `id` | Int | Identificador de función numérica |
| `key` | Cadena | Tecla de función |
| `featureGroupKey` | ¿String? | Tecla de grupo de funciones cuando esté disponible |
| `meta` | ¿String? | Metadatos de funciones opacas cuando están disponibles |
| `analyticsParam` | ¿AnalyticsParam? | Detalles de Analytics para la función evaluada |

*Parámetro de análisis*

| Campo | Tipo | Descripción |
|---|---|---|
| `featureGroupId` | Int | Identificador del grupo de funciones numéricas |
| `featureId` | Int | Identificador de función numérica |
| `variantId` | ¿String? | Identificador de variante |

**Ejemplos**

*Swift*

```swift
import AEPFlags

Flag.getFeature(
    "new-flag",
    evaluationContext: ctx
) { feature in
    guard let meta = feature?.meta, !meta.isEmpty else {
        // No metadata available: fall back to the default behavior
        return
    }
    // Feature metadata is available: use it to drive the feature behavior
}
```

*Objective-C*

```objc
@import AEPFlags;

[AEPMobileFlag getFeature:@"new-flag"
        evaluationContext:ctx
                completion:^(AEPFeatureEvaluationResult * _Nullable feature) {
    NSString *meta = feature.meta;
    if (meta.length > 0) {
        // Feature metadata is available: use it to drive the feature behavior
    } else {
        // No metadata available: fall back to the default behavior
    }
}];
```

### extensionVersion {#extension-version}

Devuelve la cadena de versión de la extensión Flags.

**Sintaxis**

*Swift*

```swift
static var extensionVersion: String
```

*Objective-C*

```objc
+ (nonnull NSString *)flagExtensionVersion;
```

**Ejemplo**

*Swift*

```swift
let version = Flag.extensionVersion
```

*Objective-C*

```objc
NSString *version = [AEPMobileFlag flagExtensionVersion];
```

## Resumen de API {#api-summary}

| de visitante | Devuelve |
|---|---|
| `isFeatureEnabled(_:evaluationContext:completion:)`. `FeatureEvaluationContext` lleva atributos de segmentación para las reglas. Consulte [isFeatureEnabled](#is-feature-enabled). | Bool a través del cierre de finalización |
| `getFeature(_:evaluationContext:completion:)`. Devuelve la carga útil de la función evaluada para el contexto determinado. Ver [getFeature](#get-feature). | ¿FeatureEvaluationResult? mediante cierre |
| `extensionVersion` | Cadena |

## Consulte también {#see-also}

* [Aplicaciones móviles](../../integrate/mobile-applications.md)
* [SDK](../../integrate/sdks.md)
* [Guía de integración de Android extension](../android/android-extension-integration-guide.md)

<!-- -->
