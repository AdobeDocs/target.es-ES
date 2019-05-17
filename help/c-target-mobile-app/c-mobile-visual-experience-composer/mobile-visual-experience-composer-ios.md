---
description: El Compositor de experiencias visuales de Adobe Target (VEC) permite a los desarrolladores configurar una sola vez en sus aplicaciones móviles iOS y permitir a los especialistas en marketing utilizar las capacidades del VEC de aplicaciones móviles.
keywords: VEC de aplicación móvil; compositor de experiencias visuales móviles; opciones del compositor de experiencias móviles; configuración; ios; apple
seo-description: El Compositor de experiencias visuales de Adobe Target (VEC) permite a los desarrolladores configurar una sola vez en sus aplicaciones móviles iOS y permitir a los especialistas en marketing utilizar las capacidades del VEC de aplicaciones móviles.
seo-title: 'iOS: configuración de la aplicación móvil'
solution: Target
title: 'iOS: configuración de la aplicación móvil'
topic: Standard
uuid: 6db4f06a-d8f4-4192-af6f-917594e721e6
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# iOS: configuración de la aplicación móvil{#ios-set-up-the-mobile-app}

El Compositor de experiencias visuales de la aplicación móvil de Adobe Target (VEC) permite a los desarrolladores configurar una sola vez en sus aplicaciones móviles iOS y permitir a los especialistas en marketing utilizar las capacidades del VEC de aplicaciones móviles.

Para obtener más información sobre la activación de la extensión VEC de Adobe Target, consulte [Adobe Target Compositor de experiencias visuales](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-target-vec) *en los SDK Mobile de Adobe Experience Platform*.

## Incluir el SDK de Mobile y la biblioteca de Target {#sdk-library}

1. Agregue la biblioteca a su proyecto a través de sus CocoaPods [!DNL Podfile] agregando el pod &#39;`ACPTargetVEC`&#39;.
1. Abra el proyecto Objective-C de la aplicación en XCode.
1. Vaya a la configuración de creación de proyecto y establezca siempre «Incrustar bibliotecas estándar rápidamente» en Sí si ya no está configurada.
1. En la configuración de creación del proyecto, busque “Otros indicadores de enlace” y añada `$(inherited)` si no aparece ahí.
1. Solo para el proyecto Objective-C: cree un archivo Swift para crear el encabezado puente. Configurará el entorno de su aplicación para Swift.
1. Añada el controlador deeplink:

   1. En la configuración del proyecto de la aplicación, haga clic en **[!UICONTROL Información]**.
   1. En Tipos **[!UICONTROL ]** de URL, haga clic en el triángulo para abrirlo y, a continuación, haga clic en el signo más para agregar un nuevo campo.
   1. Agregue la siguiente información:

      * Identificador: `com.adobe.sdktest`
      * Esquemas de URL: `vectester`
      * Rol: Editor
   1. Haga clic fuera de la configuración del proyecto de la aplicación &gt; **[!UICONTROL General]**.
   1. Vuelva a hacer clic en la configuración del proyecto de la aplicación &gt; **[!UICONTROL Información]para asegurarse de que se guardaron los ajustes.**

      Con el tipo de URL de ejemplo, el esquema de URL para la aplicación será:

      ```
      vectester://com.adobe.sdktest
      ```


1. En XCode, abra el archivo [!DNL AppDelegate].
1. En la parte superior del archivo, agregue la línea siguiente al final de las importaciones:

   `#import "ACPTargetVEC.h"`

   Si utiliza Swift, agregue la siguiente línea:

   `import ACPTargetVEC`

1. En su archivo [!DNL AppDelegate], agregue la línea siguiente a `AppDelegate::application:didFinishLaunchingWithOptions:`. Si no se define la función delegada, créela y añada la línea siguiente para Objective-C o para la aplicación Swift, respectivamente:

   ```
   // CONFIGURATION LINE FOR OBJECTIVE C ONLY (Skip any framework which is not applicable for you): 
   [ACPCore configureWithAppId:@"YOUR_ADOBE_LAUNCH_APP_ID"]; 
   [ACPCore setLogLevel:ACPMobileLogLevelDebug]; 
   [ACPLifecycle registerExtension]; 
   [ACPIdentity registerExtension]; 
   [ACPUserProfile registerExtension]; 
   [ACPTarget registerExtension];
   
   [ACPTargetVEC registerExtension];
   [ACPCore start:^{
        [ACPCore lifecycleStart:nil];
   }];
   
   // CONFIGURATION LINE FOR SWIFT ONLY: 
   ACPCore.configure(withAppId: "YOUR_ADOBE_LAUNCH_APP_ID") 
   ACPCore.setLogLevel(ACPMobileLogLevel.debug) 
   ACPLifecycle.registerExtension() 
   ACPIdentity.registerExtension() 
   ACPUserProfile.registerExtension() 
   ACPTarget.registerExtension() 
   
   ACPTargetVEC.registerExtension() 
   
   ACPCore.start {
     ACPCore.lifecycleStart(nil)
   }
   ```

   Por ejemplo, el método debería parecerse a la siguiente muestra:

   ```
   // EXAMPLE OVERRIDE METHOD FOR OBJECTIVE C ONLY: 
   - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions { 
        // Override point for customization after application launch. 
       [ACPCore configureWithAppId:@"YOUR_ADOBE_LAUNCH_APP_ID"]; 
       [ACPCore setLogLevel:ACPMobileLogLevelDebug]; 
       [ACPLifecycle registerExtension]; 
       [ACPIdentity registerExtension]; 
       [ACPUserProfile registerExtension]; 
       [ACPTarget registerExtension]; 
   
       [ACPTargetVEC registerExtension]; 
   
       [ACPCore start:nil]; 
       [ACPCore lifecycleStart:nil]; 
   
      return YES; 
   } 
   
   // EXAMPLE OVERRIDE METHOD FOR SWIFT ONLY: 
   func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey : Any]? = nil) 
   { 
       ACPCore.configure(withAppId: "YOUR_ADOBE_LAUNCH_APP_ID") 
       ACPCore.setLogLevel(ACPMobileLogLevel.debug) 
       ACPLifecycle.registerExtension() 
       ACPIdentity.registerExtension() 
       ACPUserProfile.registerExtension() 
       ACPTarget.registerExtension() 
   
       ACPTargetVEC.registerExtension() 
   
       ACPCore.start(nil) 
       ACPCore.lifecycleStart(nil)
   
       return true 
   
   }
   ```

1. Añada la línea siguiente al comienzo de `AppDelegate:application:openURL`. Si no se define la función delegada, créela y añada la línea siguiente.

   ```
   // URL HANDLER LINE FOR OBJECTIVE C ONLY: 
   [ACPTargetVEC handleDeepLink:url];
   
   // URL HANDLER LINE FOR SWIFT ONLY: 
   ACPTargetVEC.handleDeepLink(url)
   ```

   Por ejemplo, el método debería parecerse a la siguiente muestra:

   ```
   // EXAMPLE OVERRIDE METHOD FOR OBJECTIVE C ONLY:
   -  (BOOL)application:(UIApplication *)application openURL:(NSURL *)url options:(NSDictionary<NSString *, id> *)options {
    [ACPTargetVEC handleDeepLink:url];
    return YES;
   }
   
   // EXAMPLE OVERRIDE METHOD FOR SWIFT ONLY:
   func application(_ app: UIApplication, open url: URL, options: [UIApplication.OpenURLOptionsKey : Any] = [:]) -> Bool {
      ACPTargetVEC.handleDeepLink(url)
      return true;
   }
   ```

1. Cree y ejecute su aplicación y utilícela para probar las capacidades de VEC de aplicaciones móviles.

## Configurar vistas de Target en su aplicación móvil {#views}

El SDK de Adobe Mobile expone un nuevo método para que los desarrolladores activen cada vez que se represente una nueva vista. Lea las directrices generales sobre cómo insertar correctamente las llamadas de la API de vista de Target para una aplicación de iOS. En iOS, todas las vistas de Target se definen en relación con el `UIViewController` donde aparecen. Por tanto, y a diferencia de Android, la inserción de `TargetViews` se limita a las siguientes llamadas.

La aplicación Adobe Mobile App VEC Extension genera nombres para `UIViewControllers` interactuar dentro del marco de VEC de la aplicación móvil, según el nombre de clase de las subclases `UIViewController`. Si desea anular estos nombres, puede llamar al método siguiente en `viewWillAppear``ViewController`la.

```
// TARGET VIEW LINE FOR OBJECTIVE C ONLY 
[ACPTargetVEC setTargetView:@"exampleViewController"]; 
   
// TARGET VIEW LINE FOR SWIFT ONLY 
ACPTargetVEC.setTargetView("exampleViewController")
```

El SDK móvil de Adobe también ofrece un método alternativo para que los desarrolladores segmenten las vistas personalizadas durante el tiempo de ejecución. Como desarrollador, debe asegurarse de que las vistas cuenten con un nombre exclusivo. Llame al siguiente método antes de agregar la vista a `superview`:

```
// EXAMPLE TARGET VIEW FOR A CUSTOM VIEW IN OBJECTIVE C 
CustomPopupView *popupView = [[CustomPopupView alloc] initWithFrame:CGRectMake(0, 0, 300, 200)]; 
[ACPTargetVEC setTargetView:@"myCustomPopupView" forView:popupView];

// EXAMPLE TARGET VIEW FOR A CUSTOM VIEW IN SWIFT 
let popupView = CustomPopupView.init(frame: CGRect(x: 0, y: 0, width: 300, height: 200)) 
ACPTargetVEC.setTargetView("myCustomPopupView", for: popupView)
```

## Configuración de parámetros de perfil y otros parámetros globales {#parameters}

Ahora se admiten parámetros globales que se pasan en cada llamada de API y en cada llamada de API, así como pasar parámetros de mbox o vista a las vistas correspondientes.

Entre los parámetros se incluyen:

* parámetros mbox/view
* parámetros de perfil
* parámetros de producto
* parámetros de orden

**Soporte de parámetro global:**

```
//For Objective-c 
NSDictionary *mboxParams = @{@"mboxparam1":@"mboxvalue1"}; //mbox or view params 
NSDictionary *profileParams = @{@"profilekey1":@"profilevalue1"}; //profile params 
  
ACPTargetProduct *product = [ACPTargetProduct targetProductWithId:@"1234" categoryId:@"furniture"]; 
ACPTargetOrder *order = [ACPTargetOrder targetOrderWithId:@"12343" total:@(123.45) purchasedProductIds:@[@"100",@"200"]]; 
ACPTargetParameters *targetParams = [ACPTargetParameters targetParametersWithParameters:mboxParams 
                                                                      profileParameters:profileParams 
                                                                                product:product 
                                                                                  order:order]; 
[ACPTargetVEC setGlobalRequestParameters:targetParams];

//For Swift 
var mboxParams = ["mboxparam1":"mboxvalue1"] 
var profileParams = ["profilekey1":"profilevalue1"] 
var product : ACPTargetProduct = ACPTargetProduct.init(id: "1234", categoryId: "furniture") 
var order : ACPTargetOrder = ACPTargetOrder.init(id: "12345", total: 123.45, purchasedProductIds: ["100", "200"]) 
var targetParams : ACPTargetParameters = ACPTargetParameters.init(parameters: mboxParams, profileParameters: profileParams, product: product, order: order) 
ACPTargetVEC.setGlobalRequest(targetParams)
```

**Pasar parámetros para el activador de vista siguiente:**

Hemos proporcionado algunas vistas automáticas que se crean de forma predeterminada, como &quot;`AUTO_<viewControllerName>`por cada controlador de vista presente en la aplicación. Si desea pasar estos parámetros, puede llamar a la API siguiente:

```
//For Objective-c 
NSDictionary *mboxParams = @{@"viewparam1":@"viewvalue1"}; //mbox or view params 
NSDictionary *profileParams = @{@"profilekeyforview1":@"profilevalueforview1"}; //profile params 
  
ACPTargetProduct *product = [ACPTargetProduct targetProductWithId:@"1234" categoryId:@"furniture"]; 
ACPTargetOrder *order = [ACPTargetOrder targetOrderWithId:@"12343" total:@(123.45) purchasedProductIds:@[@"100",@"200"]]; 
ACPTargetParameters *targetParams = [ACPTargetParameters targetParametersWithParameters:mboxParams 
                                                                      profileParameters:profileParams 
                                                                                product:product 
                                                                                  order:order]; 
[ACPTargetVEC setGlobalRequestParameters:targetParams];

//For Swift 
var mboxParams = ["mboxparam1":"mboxvalue1"] 
var profileParams = ["profilekey1":"profilevalue1"] 
var product : ACPTargetProduct = ACPTargetProduct.init(id: "1234", categoryId: "furniture") 
var order : ACPTargetOrder = ACPTargetOrder.init(id: "12345", total: 123.45, purchasedProductIds: ["100", "200"]) 
var targetParams : ACPTargetParameters = ACPTargetParameters.init(parameters: mboxParams, profileParameters: profileParams, product: product, order: order) 
ACPTargetVEC.setRequest(targetParams)
```

**Pasar parámetros a una vista específica:**

Hemos observado que la API activó las vistas `TargetVEC.targetView("view_name")`de activación. También puede pasar parámetros que son específicos de la vista particular, como se muestra a continuación:

```
//For Objective-c 
[ACPTargetVEC setTargetView:@"VIEW_NAME" withParameters:TARGET_PARAMS];

//FOR SWIFT 
ACPTargetVEC.setTargetView("VIEW_NAME", with: TARGET_PARAMS)
```

## Llamar de forma explícita a la API de recuperación previa {#section_373DB4527FC649C58FBA3DF0C18C9836}

Puede haber ciertas situaciones en las que desee volver a llamar a la API de recuperación previa para actualizar las ofertas almacenadas en la memoria caché. Se exponen las siguientes API, que se describen como:

**Ofertas de recuperación previa:**

```
/** 
 * Prefetch all offers for all views in the cache. It will remove existing offers and changes for the current view will be 
 refreshed only when the view is triggered. This call happens on the main thread blocking the UI. 
 */ 
+ (void) prefetchOffers;
```

**Ofertas de recuperación previa en segundo plano:**

```
/** 
 * Prefetch all offers for all views in the cache. It will remove existing offers and changes for the current view will be 
 refreshed only when the view is triggered. This call happens on the background thread so doesn't block UI. 
 */ 
+ (void) prefetchOffersBackground;
```

