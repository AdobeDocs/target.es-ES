---
title: Extensión de marcas para la guía de integración de Android
description: Obtenga información sobre cómo integrar la extensión Flags con Adobe Experience Platform Mobile SDK en Android.
badge: label="Beta" type="Informative"
hide: true
exl-id: 683ef4d4-e637-4b7b-b694-689c7e65a99e
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '984'
ht-degree: 5%

---

# Extensión de marcas para Android {#android-extension-integration-guide}

En esta guía se describe cómo integrar la extensión Flags con Adobe Experience Platform Mobile SDK en Android.

## Requisitos previos {#prerequisites}

Antes de implementar la extensión Banderas, asegúrese de lo siguiente:

* Una propiedad móvil configurada en [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/#/data-collection)
* La extensión de marcas instalada y configurada en la propiedad móvil
* Un ID de organización de Adobe Experience Cloud
* SDK mínimo: API 21 (Android 5.0 Lollipop)

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
1. Siga el [proceso de publicación](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) para actualizar la configuración.

### Obtener el ID del archivo de entorno {#environment-file-id}

1. En su propiedad móvil, vaya a **Entornos**.
1. Seleccione el icono de cuadro debajo de la columna **Instalar** para su entorno.
1. En el cuadro de diálogo **Instrucciones de instalación de Mobile**, copie el **Id. de archivo de entorno**.

## Añadir la extensión de marcas a la aplicación {#add-to-app}

### Añadir dependencias {#add-dependencies}

Agregue las dependencias de Mobile SDK al proyecto. La extensión Flags requiere Mobile Core y las extensiones relacionadas con Edge que se enumeran a continuación.

#### Uso de Gradle con BOM (recomendado) {#gradle-bom}

Agregue las siguientes dependencias al archivo `build.gradle.kts` de su aplicación:

```kotlin
dependencies {
    // Adobe Experience Platform Mobile SDK BOM
    implementation(platform("com.adobe.marketing.mobile:sdkbom:3.+"))

    // Required extensions
    implementation("com.adobe.marketing.mobile:core")
    implementation("com.adobe.marketing.mobile:lifecycle")
    implementation("com.adobe.marketing.mobile:edge")
    implementation("com.adobe.marketing.mobile:edgeidentity")
}
```

#### Uso de Gradle (Groovy) {#gradle-groovy}

```groovy
dependencies {
    // Adobe Experience Platform Mobile SDK BOM
    implementation platform('com.adobe.marketing.mobile:sdkbom:3.+')

    // Required extensions
    implementation 'com.adobe.marketing.mobile:core'
    implementation 'com.adobe.marketing.mobile:lifecycle'
    implementation 'com.adobe.marketing.mobile:edge'
    implementation 'com.adobe.marketing.mobile:edgeidentity'
}
```

>[!IMPORTANT]
>
>Para aplicaciones de producción, Adobe recomienda utilizar números de versión explícitos en lugar de versiones dinámicas. Consulte [Administración de dependencias de Gradle](https://docs.gradle.org/current/userguide/dependency_management.html) para obtener más información.

### Agregar la dependencia Indicadores {#add-flags-dependency}

#### Uso del repositorio de Maven alojado (recomendado) {#hosted-maven}

Agregar el repositorio Maven de marcas al bloque `repositories` en `settings.gradle.kts`:

```kotlin
maven {
    url = uri("<HTTPS Flags Maven repository URL>")
}
```

Para un archivo de `settings.gradle` de Groovy:

```groovy
maven {
    url = uri('<HTTPS Flags Maven repository URL>')
}
```

Reemplace `<HTTPS Flags Maven repository URL>` por la URL del repositorio segura proporcionada para la extensión Flags.

A continuación, agregue la dependencia de marcas con versión a `build.gradle.kts` de la aplicación:

```kotlin
implementation("com.adobe.marketing.mobile:flags:<version>")
```

Para un archivo de `build.gradle` de Groovy:

```groovy
implementation 'com.adobe.marketing.mobile:flags:<version>'
```

Reemplace `<version>` con la versión exacta de la extensión Flags proporcionada para su versión.

#### Uso del paquete de distribución Banderas {#distribution-package}

El paquete de distribución de la extensión Flags incluye:

* `flags-3.x.aar`
* `flags-3.x.module`
* `flags-3.x.pom`

Ponga la extensión a disposición del proyecto de Android mediante uno de los métodos siguientes:

* Publique todos los archivos del paquete de distribución en un repositorio Maven local o privado y configure el proyecto para que utilice ese repositorio.
* Agregue `flags-3.x.aar` directamente al proyecto y declare las dependencias transitivas especificadas en `flags-3.x.pom`.

### Añadir permisos {#add-permissions}

Agregue los siguientes permisos al archivo `AndroidManifest.xml`:

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

### Inicialización de SDK {#initialize-sdk}

Inicialice Mobile SDK en la clase `Application` antes de llamar a las API de extensión Flags. Use el identificador de archivo de entorno de su propiedad móvil con `MobileCore.initialize` para que la aplicación recoja la configuración de marcas que publicó en la recopilación de datos.

#### Uso de MobileCore.initialize {#mobile-core-initialize}

Esta API, disponible a partir de la versión 3.8.0 de Android BOM, inicializa SDK con el archivo de entorno de recopilación de datos.

>[!IMPORTANT]
>
>Para aplicaciones de producción, use `LoggingMode.ERROR` solamente; no use `DEBUG` ni `VERBOSE` en compilaciones de versiones.

**Kotlin**

```kotlin
import android.app.Application
import com.adobe.marketing.mobile.LoggingMode
import com.adobe.marketing.mobile.MobileCore

class MainApplication : Application() {

    override fun onCreate() {
        super.onCreate()

        // Production: use LoggingMode.ERROR only. Do not use DEBUG or VERBOSE in release builds.
        MobileCore.setLogLevel(LoggingMode.ERROR)

        // Initialize with your Environment File ID from Data Collection
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID")
    }
}
```

**Java**

```java
import android.app.Application;
import com.adobe.marketing.mobile.LoggingMode;
import com.adobe.marketing.mobile.MobileCore;

public class MainApplication extends Application {

    @Override
    public void onCreate() {
        super.onCreate();

        // Production: use LoggingMode.ERROR only. Do not use DEBUG or VERBOSE in release builds.
        MobileCore.setLogLevel(LoggingMode.ERROR);

        // Initialize with your Environment File ID from Data Collection
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID", null);
    }
}
```

### Registrar la clase Application {#register-application}

Registre su clase `Application` en `AndroidManifest.xml`:

```xml
<application
    android:name=".MainApplication"
    ... >
</application>
```

## Contexto de evaluación {#evaluation-context}

La clase `FeatureEvaluationContext` incluye atributos de segmentación (utilizados para la coincidencia de reglas de indicador).

| Método | Requerido | Descripción |
|---|---|---|
| `withAttributes(map)` | No | `Map<String, List<String>>`. Clave es el nombre de atributo de contexto utilizado por las reglas de marcador (por ejemplo `locale`, `platform`, `appVersion`, `deviceType`). Value es la lista de valores de atributos candidatos para esa clave para el usuario o la sesión actual (por ejemplo `["en_US"]` o `["phone"]`). |

**Kotlin**

```kotlin
import com.adobe.marketing.mobile.flags.FeatureEvaluationContext

val attrs = mapOf(
    "locale" to listOf("en_US"),
    "platform" to listOf("ANDROID")
)

val ctx = FeatureEvaluationContext.builder()
    .withAttributes(attrs)
    .build()
```

**Java**

```java
import com.adobe.marketing.mobile.flags.FeatureEvaluationContext;
import java.util.Arrays;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

Map<String, List<String>> attrs = new HashMap<>();
attrs.put("locale", Arrays.asList("en_US"));
attrs.put("platform", Arrays.asList("ANDROID"));

FeatureEvaluationContext ctx = FeatureEvaluationContext.builder()
        .withAttributes(attrs)
        .build();
```

### Identidad personalizada {#custom-identity}

La extensión Flags utiliza la extensión Identity for Edge Network para la resolución de identidades. Se puede cohortar un indicador de funcionalidad en una identidad personalizada (por ejemplo, un ID de CRM o un ID de fidelidad) para que las divisiones de variante y los análisis estén vinculados a la identidad que importa a su aplicación.

El área de nombres de identidad personalizada debe estar seleccionada en la interfaz de usuario de marcas cuando se crea el indicador de funcionalidad. Para evaluar un indicador con respecto a esa identidad, la misma identidad debe estar presente en la identidad de Edge `identityMap` en el dispositivo, utilizando el área de nombres correspondiente. Proporciónelo durante la ejecución con la API Identity for Edge Network `updateIdentities`.

#### Añadir la identidad personalizada al mapa de identidad {#add-identity}

Añada la identidad en el mismo área de nombres configurada en el indicador de funcionalidad.

**Kotlin**

```kotlin
import com.adobe.marketing.mobile.edge.identity.AuthenticatedState
import com.adobe.marketing.mobile.edge.identity.Identity
import com.adobe.marketing.mobile.edge.identity.IdentityItem
import com.adobe.marketing.mobile.edge.identity.IdentityMap

val identityMap = IdentityMap()
identityMap.addItem(
    IdentityItem("1111", AuthenticatedState.AUTHENTICATED, true),
    "userCRMId" // must match the namespace configured on the feature flag
)
Identity.updateIdentities(identityMap)
```

**Java**

```java
import com.adobe.marketing.mobile.edge.identity.AuthenticatedState;
import com.adobe.marketing.mobile.edge.identity.Identity;
import com.adobe.marketing.mobile.edge.identity.IdentityItem;
import com.adobe.marketing.mobile.edge.identity.IdentityMap;

final IdentityItem item = new IdentityItem("1111", AuthenticatedState.AUTHENTICATED, true);
final IdentityMap identityMap = new IdentityMap();
identityMap.addItem(item, "userCRMId"); // must match the namespace configured on the feature flag
Identity.updateIdentities(identityMap);
```

## Referencia de API {#api-reference}

### isFeatureEnabled {#is-feature-enabled}

`isFeatureEnabled` devuelve si la característica Marcas está activada o desactivada en el contexto determinado. Pase `featureKey`, un `FeatureEvaluationContext` (atributos de segmentación opcionales) y una llamada de retorno. Consulte [Contexto de evaluación](#evaluation-context).

**Firma**

*Kotlin*

```kotlin
Flag.isFeatureEnabled(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<Boolean>
)
```

*Java*

```java
Flag.isFeatureEnabled(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<Boolean> callback);
```

**Parámetros**

| Parámetro | Tipo | Descripción |
|---|---|---|
| `featureKey` | Cadena | Clave de función a evaluar en Indicadores |
| `evaluationContext` | FeatureEvaluationContext | Incluya atributos de segmentación según sea necesario; use `FeatureEvaluationContext.builder().build()` para un contexto vacío. Consulte [Contexto de evaluación](#evaluation-context). |
| `callback` | AdobeCallback&lt;Boolean> | Se invocó con `true` si la característica está habilitada; de lo contrario, `false`. También puede pasar `AdobeCallbackWithError<Boolean>` al identificador `fail(...)`. |

**Ejemplos**

*Kotlin*

```kotlin
import com.adobe.marketing.mobile.AdobeCallback
import com.adobe.marketing.mobile.flags.Flag

Flag.isFeatureEnabled(
    "new-flag",
    ctx,
    object : AdobeCallback<Boolean> {
        override fun call(isEnabled: Boolean?) {
            if (isEnabled == true) {
                // run the feature-specific behavior
            } else {
                // fall back to the default behavior
            }
        }
    }
)
```

*Java*

```java
import com.adobe.marketing.mobile.AdobeCallback;
import com.adobe.marketing.mobile.flags.Flag;

Flag.isFeatureEnabled(
    "new-flag",
    ctx,
    new AdobeCallback<Boolean>() {
        @Override
        public void call(Boolean isEnabled) {
            if (Boolean.TRUE.equals(isEnabled)) {
                // run the feature-specific behavior
            } else {
                // fall back to the default behavior
            }
        }
    }
);
```

### getFeature {#get-feature}

`getFeature` devuelve la carga útil de la característica evaluada para el contexto proporcionado. Utilice esta API cuando necesite más de habilitar/deshabilitar y desee metadatos o valores de características.

**Firma**

*Kotlin*

```kotlin
Flag.getFeature(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<FeatureEvaluationResult>
)
```

*Java*

```java
Flag.getFeature(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<FeatureEvaluationResult> callback);
```

**Parámetros**

| Parámetro | Tipo | Descripción |
|---|---|---|
| `featureKey` | Cadena | Clave de función a evaluar en Indicadores |
| `evaluationContext` | FeatureEvaluationContext | Incluya atributos de segmentación según sea necesario; use `FeatureEvaluationContext.builder().build()` para un contexto vacío. Consulte [Contexto de evaluación](#evaluation-context). |
| `callback` | AdobeCallback&lt;FeatureEvaluationResult> | Se invocó con la carga útil de la característica evaluada; puede ser `null` cuando no se encuentra la característica. También puede pasar `AdobeCallbackWithError<FeatureEvaluationResult>` al identificador `fail(...)`. |

**Respuesta**

*FeatureEvaluationResult*

| Campo | Tipo | Descripción |
|---|---|---|
| `id` | Int | Identificador de función numérica |
| `key` | Cadena | Tecla de función |
| `featureGroupKey` | ¿String? | Tecla de grupo de funciones cuando esté disponible |
| `meta` | ¿String? | Los metadatos de la función como una cadena JSON cuando están disponibles |
| `analyticsParam` | ¿AnalyticsParam? | Detalles de Analytics para la función evaluada |

*Parámetro de análisis*

| Campo | Tipo | Descripción |
|---|---|---|
| `featureGroupId` | Int | Identificador del grupo de funciones numéricas |
| `featureId` | Int | Identificador de función numérica |
| `variantId` | ¿String? | Identificador de variante |

**Ejemplos**

*Kotlin*

```kotlin
import com.adobe.marketing.mobile.AdobeCallback
import com.adobe.marketing.mobile.flags.FeatureEvaluationResult
import com.adobe.marketing.mobile.flags.Flag

Flag.getFeature(
    "new-flag",
    ctx,
    object : AdobeCallback<FeatureEvaluationResult> {
        override fun call(feature: FeatureEvaluationResult?) {
            val meta = feature?.meta
            if (!meta.isNullOrEmpty()) {
                // Feature metadata is available: use it to drive the feature behavior
            } else {
                // No metadata available: fall back to the default behavior
            }
        }
    }
)
```

*Java*

```java
import com.adobe.marketing.mobile.AdobeCallback;
import com.adobe.marketing.mobile.flags.FeatureEvaluationResult;
import com.adobe.marketing.mobile.flags.Flag;

Flag.getFeature(
    "new-flag",
    ctx,
    new AdobeCallback<FeatureEvaluationResult>() {
        @Override
        public void call(FeatureEvaluationResult feature) {
            String meta = feature != null ? feature.getMeta() : null;
            if (meta != null && !meta.isEmpty()) {
                // Feature metadata is available: use it to drive the feature behavior
            } else {
                // No metadata available: fall back to the default behavior
            }
        }
    }
);
```

### extensionVersion {#extension-version}

Devuelve la cadena de versión de la extensión Flags.

**Sintaxis**

```kotlin
Flag.extensionVersion(): String
```

**Ejemplo**

*Kotlin*

```kotlin
val version = Flag.extensionVersion()
```

*Java*

```java
String version = Flag.extensionVersion();
```

## Resumen de API {#api-summary}

| de visitante | Devuelve |
|---|---|
| `isFeatureEnabled(featureKey, evaluationContext, callback)`. `FeatureEvaluationContext` lleva atributos de segmentación para las reglas. Consulte [Evaluación de características](#is-feature-enabled). | Booleano mediante llamada de retorno |
| `getFeature(featureKey, evaluationContext, callback)`. Devuelve la carga útil de la función evaluada para el contexto determinado. Ver [getFeature](#get-feature). | FeatureEvaluationResult mediante llamada de retorno |
| `extensionVersion()` | Cadena |

## Consulte también {#see-also}

* [Aplicaciones móviles](../../integrate/mobile-applications.md)
* [SDK](../../integrate/sdks.md)

<!-- -->
