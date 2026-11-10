---
title: Extensión de marcas para la guía de integración de iOS
description: Obtenga información sobre cómo integrar la extensión Flags con Adobe Experience Platform Mobile SDK en iOS.
badge: label="Beta" type="Informative"
hide: true
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: c1fafcfcd7d5d22781abdd10e6eb3c2b84136c2d
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 3%
---
# Extensión de marcas para iOS {#ios-extension-integration-guide}

En esta guía se describe cómo integrar la extensión Flags con Adobe Experience Platform Mobile SDK en iOS. El código fuente está disponible en el repositorio [aepsdk-flags-ios](https://github.com/adobe/aepsdk-flags-ios).

## Requisitos previos {#prerequisites}

Antes de empezar, asegúrese de que dispone de lo siguiente:

* iOS 12.0 o posterior, y Swift 5.7 o posterior
* Una propiedad móvil en [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/#/data-collection)
* Estas extensiones están instaladas y configuradas en la propiedad móvil:

  | Extensión | Descripción | Versión mínima de SDK |
  |---|---|---|
  | [Núcleo móvil](https://developer.adobe.com/client-sdks/home/base/mobile-core/) | Configuración y procesamiento de eventos | AEPCore 5.8.0 |
  | [Ciclo de vida](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/) | Datos del ciclo vital de aplicación | Igual que AEPCore |
  | [Edge Network](https://developer.adobe.com/client-sdks/edge/edge-network/) | Comunicación con Adobe Experience Platform Edge Network. Requiere una secuencia de datos. | AEPEdge 5.0.2 |
  | [Identidad de Edge Network](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/) | Administración de identidades para Edge Network | AEPEdgeIdentity 5.0.0 |
  | [Indicadores](https://experienceleague.adobe.com/en/docs/target/flags/home) | Evaluación de indicadores de funcionalidad | Ver [Instalación](#installation) |

## Configuración de indicadores en la recopilación de datos {#configure}

### Instalación de la extensión {#install-extension}

1. Inicie sesión en [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection).

1. Seleccione el menú **[!UICONTROL Etiquetas]** y elija su propiedad móvil.

1. Vaya a **[!UICONTROL Extensiones]** > **[!UICONTROL Catálogo]**.

1. Busque **[!DNL Adobe Flags]** y seleccione **[!UICONTROL Instalar]**.

   ![](../assets/extension-install.png)

1. Configure las opciones de extensión:

   * **[!UICONTROL espacio aislado]**: El espacio aislado de Adobe Experience Platform que contiene la configuración de Marcas.
   * **[!UICONTROL ID de aplicación]**: El identificador de su aplicación en Banderas.

1. Seleccione **[!UICONTROL Guardar]**.

1. Siga el [proceso de publicación](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) para actualizar la configuración.

### Obtener el ID del archivo de entorno {#environment-file-id}

1. En su propiedad móvil, vaya a **[!UICONTROL Entornos]**.

1. Seleccione el icono de cuadro en la columna **[!UICONTROL Instalar]** del entorno seleccionado.

   ![](../assets/extension-install-2.png)

1. En el cuadro de diálogo **[!UICONTROL Instrucciones de instalación de Mobile]**, copie el **[!UICONTROL Id. de archivo de entorno]**.

   ![](../assets/extension-install-3.png)

## Instalación {#installation}

Añada la extensión mediante Swift Package Manager o un XCFramework. Utilice un método por destino de aplicación.

### Administrador De Paquetes Swift {#swift-package-manager}

En Xcode:

1. Seleccione **Archivo** > **Agregar dependencias del paquete**.

1. Escriba la dirección URL del paquete: `https://github.com/adobe/aepsdk-flags-ios.git`

1. Para la regla de versión, seleccione **Versión exacta** e introduzca la versión más reciente en la [página de versiones](https://github.com/adobe/aepsdk-flags-ios/releases).

1. Agregue la biblioteca `AEPFlags` al destino de la aplicación.

1. Añada los paquetes de Adobe de los que depende la extensión y añada sus bibliotecas al destino de la aplicación:

   * `https://github.com/adobe/aepsdk-core-ios.git`: `AEPCore`, `AEPLifecycle` y `AEPServices`
   * `https://github.com/adobe/aepsdk-edge-ios.git`: `AEPEdge`
   * `https://github.com/adobe/aepsdk-edgeidentity-ios.git`: `AEPEdgeIdentity`

Si el proyecto usa un archivo de `Package.swift`, agregue las dependencias allí. Reemplazar `<latest-version>` por la última versión de la página de versiones.

```swift
dependencies: [
    .package(url: "https://github.com/adobe/aepsdk-flags-ios.git", exact: "<latest-version>"),
    .package(url: "https://github.com/adobe/aepsdk-core-ios.git", .upToNextMajor(from: "5.8.0")),
    .package(url: "https://github.com/adobe/aepsdk-edge-ios.git", .upToNextMajor(from: "5.0.2")),
    .package(url: "https://github.com/adobe/aepsdk-edgeidentity-ios.git", .upToNextMajor(from: "5.0.0"))
],
targets: [
    .target(
        name: "YourTarget",
        dependencies: [
            .product(name: "AEPFlags", package: "aepsdk-flags-ios"),
            .product(name: "AEPCore", package: "aepsdk-core-ios"),
            .product(name: "AEPLifecycle", package: "aepsdk-core-ios"),
            .product(name: "AEPServices", package: "aepsdk-core-ios"),
            .product(name: "AEPEdge", package: "aepsdk-edge-ios"),
            .product(name: "AEPEdgeIdentity", package: "aepsdk-edgeidentity-ios")
        ]
    )
]
```

### XCFramework {#xcframework}

1. Desde la página de [versiones](https://github.com/adobe/aepsdk-flags-ios/releases), descargue `AEPFlags-<version>.xcframework.zip` y descomprímalo.

1. Descargue los XCFrameworks de los que depende la extensión desde la página de versiones de cada repositorio:

   * [versiones de aepsdk-core-ios](https://github.com/adobe/aepsdk-core-ios/releases): `AEPCore`, `AEPServices`, `AEPLifecycle` y `AEPRulesEngine`
   * [versiones de aepsdk-edge-ios](https://github.com/adobe/aepsdk-edge-ios/releases): `AEPEdge`
   * [versiones de aepsdk-edgeidentity-ios](https://github.com/adobe/aepsdk-edgeidentity-ios/releases): `AEPEdgeIdentity`

1. En Xcode, seleccione el destino de la aplicación y, a continuación, abra **General** > **Marcos, bibliotecas y contenido incrustado**.

1. Agregar `AEPFlags.xcframework` y todos los XCFrameworks dependientes.

1. Establezca cada módulo en **Incrustar y firmar**.

## Inicialización de SDK {#initialize-sdk}

Registre la extensión Flags y, a continuación, inicialice SDK con el ID de archivo de entorno desde la propiedad móvil. `MobileCore.initialize` no registra la extensión Flags por usted, por lo que debe registrarla primero.

>[!BEGINTABS]

>[!TAB Swift]

```swift
import AEPCore
import AEPFlags
import UIKit

class AppDelegate: UIResponder, UIApplicationDelegate {
    func application(
        _ application: UIApplication,
        didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
    ) -> Bool {
        MobileCore.registerExtensions([Flag.self])
        MobileCore.initialize(appId: "<your-environment-file-id>")
        return true
    }
}
```

>[!TAB Objective-C]

```objc
@import AEPCore;
@import AEPFlags;

- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    [AEPMobileCore registerExtensions:@[AEPMobileFlag.class] completion:nil];
    [AEPMobileCore initializeWithAppId:@"<your-environment-file-id>" completion:nil];
    return YES;
}
```

>[!ENDTABS]

### Registro manual de extensiones {#register-manually}

Si registra extensiones usted mismo, registre todas ellas. Llame a `MobileCore.lifecycleStart` cuando la aplicación entre en primer plano y a `MobileCore.lifecyclePause` cuando entre en segundo plano.

Si su aplicación utiliza escenas, realice estas llamadas en `sceneWillEnterForeground(_:)` y `sceneDidEnterBackground(_:)`.

>[!BEGINTABS]

>[!TAB Swift]

```swift
import AEPCore
import AEPEdge
import AEPEdgeIdentity
import AEPFlags
import AEPLifecycle
import UIKit

class AppDelegate: UIResponder, UIApplicationDelegate {
    func application(
        _ application: UIApplication,
        didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
    ) -> Bool {
        MobileCore.registerExtensions([
            Lifecycle.self,
            Edge.self,
            AEPEdgeIdentity.Identity.self,
            Flag.self
        ]) {
            MobileCore.configureWith(appId: "<your-environment-file-id>")
            DispatchQueue.main.async {
                if application.applicationState != .background {
                    MobileCore.lifecycleStart(additionalContextData: nil)
                }
            }
        }
        return true
    }

    func applicationWillEnterForeground(_ application: UIApplication) {
        MobileCore.lifecycleStart(additionalContextData: nil)
    }

    func applicationDidEnterBackground(_ application: UIApplication) {
        MobileCore.lifecyclePause()
    }
}
```

>[!TAB Objective-C]

```objc
@import AEPCore;
@import AEPEdge;
@import AEPEdgeIdentity;
@import AEPFlags;
@import AEPLifecycle;

- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    [AEPMobileCore registerExtensions:@[
        AEPMobileLifecycle.class,
        AEPMobileEdge.class,
        AEPMobileEdgeIdentity.class,
        AEPMobileFlag.class
    ] completion:^{
        [AEPMobileCore configureWithAppId:@"<your-environment-file-id>"];
        dispatch_async(dispatch_get_main_queue(), ^{
            if (application.applicationState != UIApplicationStateBackground) {
                [AEPMobileCore lifecycleStart:nil];
            }
        });
    }];
    return YES;
}

- (void)applicationWillEnterForeground:(UIApplication *)application {
    [AEPMobileCore lifecycleStart:nil];
}

- (void)applicationDidEnterBackground:(UIApplication *)application {
    [AEPMobileCore lifecyclePause];
}
```

>[!ENDTABS]

## Contexto de evaluación {#evaluation-context}

Cada llamada de evaluación toma un `FeatureEvaluationContext`. Contiene los atributos que utilizan las reglas de segmentación de los indicadores.

| Parámetro | Requerido | Descripción |
|---|---|---|
| `attributes` | No | `[String: [String]]`. Cada clave es un nombre de atributo que utilizan las reglas de segmentación de indicadores. Cada valor es la lista de valores del usuario actual. |

* Utilice nombres de atributo y valores que coincidan con las reglas de segmentación definidas en Indicadores.
* Llamar a `withAttributes` como máximo una vez por generador. Una segunda llamada finaliza la aplicación.
* Para evaluar sin atributos, llame a `build()` sin llamar a `withAttributes`.

>[!BEGINTABS]

>[!TAB Swift]

```swift
import AEPFlags

let context = FeatureEvaluationContext.builder()
    .withAttributes([
        "locale": ["en_US"],
        "appVersion": ["3.0.0"]
    ])
    .build()
```

>[!TAB Objective-C]

```objc
@import AEPFlags;

AEPFeatureEvaluationContext *context = [[[AEPFeatureEvaluationContext builder]
    withAttributes:@{
        @"locale": @[@"en_US"],
        @"appVersion": @[@"3.0.0"]
    }]
    build];
```

>[!ENDTABS]

## Identidad personalizada {#custom-identity}

La extensión Flags utiliza la extensión Identity for Edge Network para la resolución de identidades. Se puede cohortar un indicador de funcionalidad en una identidad personalizada (por ejemplo, un ID de CRM o un ID de fidelidad) para que las divisiones de variante y los análisis estén vinculados a la identidad que importa a su aplicación.

El área de nombres de identidad personalizada debe estar seleccionada en la interfaz de usuario de marcas cuando se crea el indicador de funcionalidad. Para evaluar un indicador con respecto a esa identidad, la misma identidad debe estar presente en la identidad de Edge `identityMap` en el dispositivo, utilizando el área de nombres correspondiente. Proporciónelo durante la ejecución con la API Identity for Edge Network `updateIdentities`.

### Añadir la identidad personalizada al mapa de identidad {#add-identity}

Añada la identidad en el mismo área de nombres configurada en el indicador de funcionalidad.

Tenga en cuenta el siguiente comportamiento:

* El área de nombres debe coincidir exactamente con la configurada en el indicador, incluidas las letras mayúsculas y minúsculas.
* Si hay varias identidades en el área de nombres, se utiliza la marcada como principal. Si ninguno está marcado como principal, se utiliza el primero.
* Si falta la identidad, la llamada no falla. El usuario se asigna aleatoriamente a una variante solo para la sesión de aplicación actual y se le puede asignar otra distinta una vez que se reinicie la aplicación. Establezca la identidad antes de evaluar los indicadores que la utilizan.

>[!BEGINTABS]

>[!TAB Swift]

```swift
import AEPEdgeIdentity

let identityMap = IdentityMap()
identityMap.add(
    item: IdentityItem(id: "1111", authenticatedState: .authenticated, primary: true),
    withNamespace: "userCRMId" // must match the namespace configured on the feature flag
)
Identity.updateIdentities(with: identityMap)
```

>[!TAB Objective-C]

```objc
@import AEPEdgeIdentity;

AEPIdentityItem *item = [[AEPIdentityItem alloc] initWithId:@"1111"
                                         authenticatedState:AEPAuthenticatedStateAuthenticated
                                                    primary:YES];
AEPIdentityMap *identityMap = [[AEPIdentityMap alloc] init];
[identityMap addItem:item withNamespace:@"userCRMId"]; // must match the namespace configured on the feature flag
[AEPMobileEdgeIdentity updateIdentities:identityMap];
```

>[!ENDTABS]


## Referencia de API {#api-reference}

### isFeatureEnabled {#is-feature-enabled}

Compruebe si una característica está habilitada para el usuario actual. El resultado es `true` cuando la característica existe, el usuario coincide con sus reglas de segmentación y el usuario no está en un grupo de control. De lo contrario, el resultado es `false`.

>[!BEGINTABS]

>[!TAB Swift]

```swift
static func isFeatureEnabled(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (Bool) -> Void,
    errorCallback: ((AEPError) -> Void)?
)
```

>[!TAB Objective-C]

```objc
+ (void)isFeatureEnabled:(NSString *)featureKey
       evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
              completion:(void (^)(BOOL))completion
           errorCallback:(void (^ _Nullable)(enum AEPError))errorCallback;
```

>[!ENDTABS]

**Parámetros**

| Parámetro | Tipo | Descripción |
|---|---|---|
| `featureKey` | Cadena | Clave de función a evaluar en Indicadores |
| `evaluationContext` | FeatureEvaluationContext | Incluya atributos de segmentación según sea necesario; use `FeatureEvaluationContext.builder().build()` para un contexto vacío. Consulte [Contexto de evaluación](#evaluation-context). |
| `completion` | `(Bool) -> Void` | Se llama con `true` si la característica está habilitada, `false` en caso contrario. |
| `errorCallback` | `((AEPError) -> Void)?` | Opcional. Solo se llama para errores genuinos, como una clave vacía, la falta de configuración, una evaluación fallida o un tiempo de espera. |

**Ejemplos**

>[!BEGINTABS]

>[!TAB Swift]

```swift
Flag.isFeatureEnabled("new-flag", evaluationContext: context) { isEnabled in
    DispatchQueue.main.async {
        if isEnabled {
            // Run the feature-specific behavior
        } else {
            // Run the default behavior
        }
    }
} errorCallback: { _ in
    DispatchQueue.main.async {
        // Run the default behavior
    }
}
```

>[!TAB Objective-C]

```objc
[AEPMobileFlag isFeatureEnabled:@"new-flag"
              evaluationContext:context
                     completion:^(BOOL isEnabled) {
    dispatch_async(dispatch_get_main_queue(), ^{
        if (isEnabled) {
            // Run the feature-specific behavior
        } else {
            // Run the default behavior
        }
    });
} errorCallback:^(enum AEPError error) {
    dispatch_async(dispatch_get_main_queue(), ^{
        // Run the default behavior
    });
}];
```

>[!ENDTABS]

### getFeature {#get-feature}

>[!IMPORTANT]
>
>Las versiones anteriores llamaron a la devolución de llamada de error con `AEPError.unexpected` cuando no se proporcionó una característica. Si la aplicación trató ese error como &quot;falta característica&quot;, controle `nil` en la finalización en su lugar.

Devuelve los detalles de una característica para el usuario actual, incluidos sus metadatos y la variante a la que está asignado el usuario. Utilícelo cuando necesite más de habilitar o deshabilitar.

Se llama a la finalización con un resultado solo cuando la función se proporciona al usuario. Si no se proporciona la característica, se llama a la finalización con `nil`. Este es un resultado normal, no un error, y no se llama a la devolución de llamada de error. Se llama a la finalización con `nil` cuando:

* Ninguna función tiene esta clave.
* El usuario no coincide con las reglas de segmentación.
* El usuario está en un grupo de control.

Se llama a la devolución de llamada de error con `AEPError.unexpected` (u otro `AEPError`) solo cuando algo sale mal: la clave de característica está vacía, falta un valor de configuración requerido, la evaluación falla, no se puede leer la respuesta o se agota el tiempo de espera de la solicitud.

>[!BEGINTABS]

>[!TAB Swift]

```swift
static func getFeature(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (FeatureEvaluationResult?) -> Void,
    errorCallback: ((AEPError) -> Void)?
)
```

>[!TAB Objective-C]

```objc
+ (void)getFeature:(NSString *)featureKey
 evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
        completion:(void (^)(AEPFeatureEvaluationResult * _Nullable))completion
     errorCallback:(void (^ _Nullable)(enum AEPError))errorCallback;
```

>[!ENDTABS]

**Parámetros**

| Parámetro | Tipo | Descripción |
|---|---|---|
| `featureKey` | Cadena | Clave de función a evaluar en Indicadores |
| `evaluationContext` | FeatureEvaluationContext | Incluya atributos de segmentación según sea necesario; use `FeatureEvaluationContext.builder().build()` para un contexto vacío. Consulte [Contexto de evaluación](#evaluation-context). |
| `completion` | `(FeatureEvaluationResult?) -> Void` | Se llama con la carga útil de la función evaluada. Se llama con `nil` cuando la característica no se proporciona al usuario (clave desconocida, segmentación no coincidente o grupo de control). `nil` no es un error. |
| `errorCallback` | `((AEPError) -> Void)?` | Opcional. Solo se llama para errores genuinos, como una clave vacía, la falta de configuración, una evaluación fallida o un tiempo de espera. No se llama cuando la función no está disponible. |

**Respuesta**

*FeatureEvaluationResult*

| Campo | Tipo | Descripción |
|---|---|---|
| `id` | Int | ID de la función |
| `key` | Cadena | La tecla de función |
| `featureGroupKey` | ¿String? | La clave del grupo de funciones que contiene la función |
| `meta` | ¿String? | Los metadatos configurados para la función, como texto. Si los metadatos son JSON, descodifíquelos en la aplicación. |
| `analyticsParam` | ¿AnalyticsParam? | Identificadores de la función y la variante del usuario |

**Ejemplos**

>[!BEGINTABS]

>[!TAB Swift]

```swift
Flag.getFeature("new-flag", evaluationContext: context) { feature in
    DispatchQueue.main.async {
        guard let meta = feature?.meta, !meta.isEmpty else {
            // The feature is not served to this user (feature is nil), or it has no metadata.
            // Run the default behavior
            return
        }
        // Use the metadata to drive the feature behavior
    }
} errorCallback: { _ in
    DispatchQueue.main.async {
        // A genuine failure occurred. Run the default behavior
    }
}
```

>[!TAB Objective-C]

```objc
[AEPMobileFlag getFeature:@"new-flag"
        evaluationContext:context
               completion:^(AEPFeatureEvaluationResult * _Nullable feature) {
    dispatch_async(dispatch_get_main_queue(), ^{
        if (feature.meta.length > 0) {
            // Use the metadata to drive the feature behavior
        } else {
            // Run the default behavior
        }
    });
} errorCallback:^(enum AEPError error) {
    dispatch_async(dispatch_get_main_queue(), ^{
        // Run the default behavior
    });
}];
```

>[!ENDTABS]

### extensionVersion {#extension-version}

Devuelve la versión de la extensión Flags.

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
| `isFeatureEnabled(_:evaluationContext:completion:errorCallback:)` | Booleano hasta la finalización |
| `getFeature(_:evaluationContext:completion:errorCallback:)` | ¿FeatureEvaluationResult? hasta la finalización |
| `extensionVersion` | Cadena |
