---
description: La nueva biblioteca de SDK de Target permite a los desarrolladores realizar una única configuración de sus aplicaciones móviles Android, mientras que los expertos en marketing pueden utilizar las capacidades del nuevo Compositor de experiencias visuales (VEC) móvil.
keywords: vec móvil;compositor de experiencias visuales móvil;opciones del compositor de experiencias móvil;configuración;android
seo-description: La nueva biblioteca de SDK de Target permite a los desarrolladores realizar una única configuración de sus aplicaciones móviles Android, mientras que los expertos en marketing pueden utilizar las capacidades del nuevo Compositor de experiencias visuales (VEC) móvil.
seo-title: 'Android: configuración de la aplicación móvil'
solution: Target
title: 'Android: configuración de la aplicación móvil'
topic: Standard
uuid: 39938ec2-b12e-44cf-9218-69195fba0ff7
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Android: configuración de la aplicación móvil{#android-set-up-the-mobile-app}

El Compositor de experiencias visuales de la aplicación móvil de Adobe Target (VEC) permite a los desarrolladores configurar una sola vez en sus aplicaciones móviles Android y permitir a los especialistas en marketing utilizar las capacidades del VEC de aplicaciones móviles.

Para obtener más información sobre la activación de la extensión VEC de Adobe Target, consulte [Adobe Target Compositor de experiencias visuales](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-target-vec) *en los SDK Mobile de Adobe Experience Platform*.

## Incluir el SDK de Mobile y la biblioteca de Target {#sdk-library}

1. Para obtener información sobre la inicialización de SDK V5, consulte [Inicializar el SDK y configurar el seguimiento](https://aep-sdks.gitbook.io/docs/getting-started/initialize-the-sdk).
1. Agregue la línea siguiente a la sección de dependencias:

   ```
   implementation 'com.adobe.marketing.mobile:target-vec:1.+'
   ```

1. El VEC de aplicación móvil requiere que se incluyan los siguientes artefactos como dependencia `build.gradle`en.

   ```
    implementation 'com.google.code.gson:gson:2.8.2'
    implementation 'android.arch.lifecycle:extensions:1.1.1'
    implementation('io.github.sac:SocketclusterClientJava:1.7.5')
    implementation 'com.android.support:support-annotations:28.0.0'
    implementation 'com.android.support:support-compat:28.0.0'
    implementation 'com.android.support:design:28.0.0'
   ```

1. Agregue un filtro de intenciones en `AndroidManifest.XML` el archivo, eligiendo un esquema único de vínculos profundos para la creación de VEC de aplicación móvil (por ejemplo `[sdkbetabus://com.adobe.sdkbetabus](sdkbetabus://com.adobe.sdkbetabus)`,):

   ```
   <activity 
       android:name=".listing.MoviesListingActivity" 
       android:launchMode="singleTask"> 
       <intent-filter> 
           <action android:name="android.intent.action.VIEW" /> 
   
           <category android:name="android.intent.category.DEFAULT" /> 
           <category android:name="android.intent.category.BROWSABLE" /> 
   
           <data 
               android:host="com.adobe.sdkbetabus" 
               android:scheme="sdkbetabus" /> 
       </intent-filter> 
   </activity>
   ```

1. Vaya al proyecto móvil e inserte las siguientes líneas al final del `Application::onCreate override`

   ```
   public class SDKTest extends MultiDexApplication { 
   
       @Override 
       public void onCreate() { 
           /* Put Your App's implementation */ 
           MobileCore.setApplication(this); 
           MobileCore.setLogLevel(LoggingMode.DEBUG); 
           MobileCore.configureWithAppID("YOUR_ADOBE_LAUNCH_APP_ID"); 
   
           ... 
           try { 
               TargetVEC.registerExtension(); //Single line code to initialize TargetVEC
               Target.registerExtension();
               Identity.registerExtension();
               Lifecycle.registerExtension();
               Signal.registerExtension();
               MobileCore.start(new AdobeCallback () {
                  @Override
                  public void call(Object o) {
                     MobileCore.configureWithAppID("launch-EN4e833d644d1949e39e985ddad4f52bd4-development");
                  }
               });
           } catch (InvalidInitException e) { 
             .. 
           }
       }
   
   /* Rest of Application test goes here ... */
   ```

1. Si su compilación no funciona, revise los proyectos de ejemplo que se proporcionan más abajo y que deberían compilarse de forma predeterminada y revise cambios en las siguientes ubicaciones:

   1. `Application::OnCreate override`
   1. `AndroidManifest.XML`
   1. `build.gradle` de la aplicación Android

## Configurar vistas de Target en su aplicación móvil {#views}

El SDK de Adobe Mobile expone un nuevo método para que los desarrolladores activen cada vez que se represente una nueva vista. Como desarrollador, debe asegurarse de que las vistas tengan nombres únicos y que la llamada `targetView` esté en el hilo principal de la interfaz del usuario. En esta sección, primero demostraremos cómo insertar estas llamadas con dos aplicaciones de demostración diferentes y analizaremos las directrices generales sobre cómo insertar correctamente las llamadas de API de vista de Target para cualquier aplicación de Android.

>[!NOTE]
>
>Si no `targetView function` se activa, la extensión VEC intenta identificar la vista desde la actividad de Android. Para las aplicaciones que no tienen vistas dinámicas, éste puede ser un paso opcional.

Una vista de objetivo se puede activar con una llamada de función. Se puede proporcionar opcionalmente cualquier parámetro de objetivo con la vista.

```
public class TargetVEC { 
   
   /** 
    * Marks a view hierarchy for editing in Mobile App VEC.  Call must insert when the view hierarchy 
    * is memory and committed to being shown, but not yet shown on the screen. 
    * 
    * @param viewName the unique Target View Name 
    */ 
   public static void targetView(String viewName); 
  
  /** 
   * Trigger Target view 
   * Triggering a Target view may cause Target offers to be applied on the current container component. 
   * Note that Target offers are applied from local Target cache, so flicker should be negligible. 
   * 
   * @param viewName Mandatory Target View name, which must be unique at app level 
   * @param parameters Parameters to be included in the next Target call 
   */ 
  
    public static void targetView(String viewName, TargetParameters parameters); 
}
```

Nuestro primer proyecto de ejemplo es una maqueta de aplicación de programación de autobuses sencilla. Para configurar esta aplicación para utilizarla en el VEC de aplicaciones móviles:

1. En Android Studio, abra el proyecto con el archivo `build.gradle` en el subdirectorio del paquete `BusBooking`.
1. En el método `DemoApplication::OnCreate`, agregue `TargetVEC.registerExtension()` para registrar la extensión VEC de Target junto con otras extensiones.
1. Compile y ejecute la aplicación.
1. Para entrar al modo de creación VEC de la aplicación móvil, use [!DNL sdkbetabus://com.adobe.sdkbetabus] como esquema de URL y abra el vínculo profundo generado en el dispositivo (consulte las instrucciones siguientes).

Desde esta sencilla aplicación para búsqueda de autobuses, usamos todas las vistas de Target generadas automáticamente que estén asociadas con el ciclo de vida de actividad. Además, demostramos la flexibilidad de la API al llamar a la API de vista de Target en un elemento de vista personalizada que se agrega dinámicamente cuando se hace clic en un botón oculto (la imagen de oferta en la pantalla). Esta nueva vista de Target se implementa al insertar una llamada de la API en el código en `OfferDetailsActivity.java:40`. Cuando se hace clic en el botón, se dispara un nuevo evento de vista de Target llamado “SURPRISE_VIEW”, lo que permite que el distribuidor cambie el objetivo con más precisión en la experiencia de la aplicación.

Inserción de vista dinámica con objetivo:

```
package com.adobe.target.examples.bus; 
   
import android.app.DialogFragment; 
import android.os.Bundle; 
import android.os.Handler; 
import android.support.v7.app.AppCompatActivity; 
import android.support.v7.widget.Toolbar; 
import android.view.View; 
import android.view.ViewGroup; 
import android.widget.LinearLayout; 
import android.widget.Toast; 
   
import com.adobe.target.mobile.TargetVEC; 
   
/** 
 * This activity class is responsible to show offer details 
 */ 
public class OfferDetailsActivity extends AppCompatActivity { 
    @Override 
    protected void onCreate(Bundle savedInstanceState) { 
        super.onCreate(savedInstanceState); 
        setContentView(R.layout.activity_offer_details); 
        setUpToolBar(); 
        final Handler mainHandler = new Handler(getApplicationContext().getMainLooper()); 
   
        final View surpriseView = getLayoutInflater().inflate(R.layout.suprise_layout, 
                (ViewGroup) findViewById(android.R.id.content), false); 
   
        final View imagePresentView = this.findViewById(R.id.image_present); 
        final LinearLayout currentLayout = this.findViewById(R.id.offer_layout); 
   
        imagePresentView.setOnClickListener(new View.OnClickListener() { 
            @Override 
            public void onClick(View v) { 
                Toast.makeText(getApplicationContext(),"Surprise!", Toast.LENGTH_SHORT).show(); 
                mainHandler.post(new Runnable() { 
                    @Override 
                    public void run() { 
                        currentLayout.addView(surpriseView); 
                        TargetVEC.targetView("SURPRISE_VIEW"); 
                        currentLayout.invalidate(); 
                    } 
                }); 
                // One-shot.  Remove clicker afterwards. 
                imagePresentView.setOnClickListener(null); 
            } 
        }); 
    } 
   
    private void setUpToolBar() { 
        Toolbar toolbar = findViewById(R.id.toolbar); 
        toolbar.setNavigationIcon(R.drawable.abc_ic_ab_back_material); 
        toolbar.setTitle("Buy 1 Get 1"); 
        toolbar.setNavigationOnClickListener(new View.OnClickListener() { 
            @Override 
            public void onClick(View v) { 
                onBackPressed(); 
            } 
        }); 
    } 
   
    @Override 
    protected void onPause() { 
        super.onPause();
        MobileCore.lifecyclePause();
    } 
   
    @Override 
    protected void onResume() { 
        super.onResume();
        MobileCore.lifecycleStart(null);
    } 
}
```

## Configuración de parámetros de perfil y otros parámetros globales {#parameters}

Ahora es compatible con configurar parámetros globales que se pasarán en cada llamada de API, así como pasar parámetros de mbox/vista a las vistas correspondientes.

Entre los parámetros se incluyen:

* parámetros mbox/view
* parámetros de perfil
* parámetros de producto
* parámetros de orden

**Soporte de parámetro global:**

```
Map<String, String> mboxParams = new HashMap<>();  //Mbox or view params 
mboxParams.put("mboxparam1", "mboxvalue1"); 
Map<String, String> profileParams = new HashMap<>();  //Profile params 
profileParams.put("profilekey1", "profilevalue1"); 
  
TargetVEC.setGlobalRequestParameters(new TargetParameters.Builder() 
        .parameters(mboxParams) 
        .profileParameters(profileParams) 
        .product(new TargetProduct("1234", "furniture")) 
        .order(new TargetOrder("12343", 123.45, Arrays.asList("100", "200"))) 
        .build());
```

**Pasar parámetros para el activador de vista siguiente:**

Hemos proporcionado algunas vistas automáticas que se crean de forma predeterminada, como &quot;`AUTO_<activity|fragment name>`por cada actividad y fragmento presente en la aplicación. Si desea pasar estos parámetros, puede llamar a la API siguiente:

```
Map<String, String> mboxParams = new HashMap<>();  //Mbox or view params 
mboxParams.put("viewKey1", "viewparam1"); 
Map<String, String> profileParams = new HashMap<>();  //Profile params 
profileParams.put("profilekeyforview1", "profilevalueforview1"); 
  
TargetVEC.setRequestParameters(new TargetParameters.Builder() 
        .parameters(mboxParams) 
        .profileParameters(profileParams) 
        .product(new TargetProduct("1234", "furniture")) 
        .order(new TargetOrder("12343", 123.45, Arrays.asList("100", "200"))) 
        .build());
```

**Pasar parámetros a una vista específica:**

Hemos observado que la API activó las vistas `TargetVEC.targetView("view_name")`de activación. También puede pasar parámetros que son específicos de la vista particular, como se muestra a continuación:

```
Map<String, String> profileParams = new HashMap<>(); 
profileParams.put("surprisekey1", "surprisevalue1");  //ProfileParams 
TargetVEC.targetView("SURPRISE_VIEW", 
        new TargetParameters.Builder() 
                .profileParameters(profileParams) 
                .product(new TargetProduct("3354", "kitchen")) 
                .build());
```

## Llamar de forma explícita a la API de recuperación previa {#section_2D02B74558474D3BA9F25E4D25E7C7E3}

Puede haber ciertas situaciones en las que desee volver a llamar a la API de recuperación previa para actualizar las ofertas almacenadas en la memoria caché. Se exponen las siguientes API, que se describen como:

* **prefetchOffers**

   ```
   /** 
    * Prefetch Target offers. 
    * Note that calling this will pre-hide the current layout, until Target offers are prefetched 
    * and applied to currently visible Target views, possibly causing flicker, thus it's recommended 
    * to call this method inside the containing component's onCreate() lifecycle method 
    */ 
   public static void prefetchOffers();
   ```

* **prefetchOffersBackground**

   ```
   /** 
    * Prefetch Target offers in the background. 
    * Note, that in contrast to prefetchOffers(), calling this method will NOT pre-hide 
    * the current layout, instead prefetched Target offers will be only be cached and will subsequently 
    * be applied as Target Views are being triggered. 
    */ 
   public static void prefetchOffersBackground();
   ```

