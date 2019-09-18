---
description: Los atributos de perfil son parámetros específicos del visitante. Estos atributos se almacenan en el perfil del visitante para proporcionar información acerca de ese visitante que puede utilizar en sus actividades de Adobe Target.
keywords: Script de perfil;atributos de script de perfil;prácticas recomendadas de script de perfil;depurar;depuración
seo-description: Los atributos de perfil son parámetros específicos del visitante. Estos atributos se almacenan en el perfil del visitante para proporcionar información acerca de ese visitante que puede utilizar en sus actividades de Adobe Target.
seo-title: Atributos de perfil en Adobe Target
solution: Target
title: Atributos de perfil
topic: Advanced,Standard,Classic
uuid: a76ed523-32cb-46a2-a2a3-aba7f880248b
translation-type: tm+mt
source-git-commit: 2aa63623b4d2ca38ec96c51402ee483a918dd3ae

---


# Atributos de perfil{#profile-attributes}

Los atributos de perfil son parámetros específicos de un visitante. Estos atributos se almacenan en el perfil del visitante para proporcionar información acerca de ese visitante que puede utilizar en sus actividades.

Cuando un visitante navega por su sitio web o regresa para otra sesión, los valores de atributos de perfil guardados se pueden utilizar para segmentar el contenido o registrar información para filtrar segmentos.

Para configurar atributos de perfil, haga clic en **[!UICONTROL Audiencias]** &gt; **[!UICONTROL Scripts de perfil.]**

![Pestaña Scripts de perfil](/help/c-target/c-visitor-profile/assets/profile-scripts.png)

Se encuentran disponibles los siguientes tipos de atributos de perfil:

| Tipo de parámetro | Descripción |
|--- |--- |
| Mbox | Se pasan directamente a través del código de la página cuando el mbox se crea. Consulte [Pasar parámetros a un mbox global](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md).<br>**Nota**: Target tiene un límite de 50 atributos de perfil únicos por llamada de mbox. Si necesita pasar más de 50 atributos de perfil a Target, puede hacerlo por medio del método de API Profile Update. Para obtener más información, consulte [Profile Update en la documentación de la API de Adobe Target](http://developers.adobetarget.com/api/#updating-profiles). |
| Script | Definido directamente con un fragmento de código de JavaScript. Pueden almacenar totales acumulados (como, por ejemplo, el importe total que un usuario ha gastado) y se ejecutan en cada solicitud de mbox. Consulte Atributos de script de perfil a continuación. |

## Atributos de script de perfil {#concept_8C07AEAB0A144FECA8B4FEB091AED4D2}

Defina un atributo de script de perfil con su fragmento de código de JavaScript asociado.

Los scripts de perfil se pueden usar para capturar atributos de visitantes en varias visitas. Son fragmentos de código definidos en Target que utilizan un tipo de JavaScript del servidor. Por ejemplo, puede usar un script de perfil para capturar la frecuencia con que una persona visita su sitio y ver cuándo fue la última vez que lo hizo.

Los scripts de perfil no son lo mismo que los parámetros de perfil. Los parámetros de perfil capturan información sobre los visitantes mediante la implementación con código de mbox de Target.

>[!NOTE]
>
>[!DNL Target] tiene un límite de 1000 scripts de perfil por cuenta.

## Creación de scripts de perfil {#section_CB02F8B97CAF407DA84F7591A7504810}

Los scripts de perfil están disponibles en la ficha [!UICONTROL Audiencias] de la interfaz de [!DNL Target].

Para agregar un nuevo script de perfil, haga clic en la pestaña **[!UICONTROL Scripts de perfil]** y en **[!UICONTROL Crear script]**. A continuación, escriba el script.

O

Para copiar un script de perfil existente, en la lista [!UICONTROL Scripts de perfil], pase el ratón sobre el script que quiera y luego haga clic en el icono **[!UICONTROL Copiar]**: (assets/icon_copy.png).

Luego puede editar la audiencia para crear otra parecida.

![Cuadro de diálogo Crear script de perfil](assets/profile-script.png)

Los scripts ejecutan “catchers” de atributos de perfil en cada solicitud de ubicación. Cuando se recibe una solicitud de ubicación, Target determina la actividad que debe ejecutarse y muestra el contenido apropiado para esa actividad y esa experiencia, rastrea el éxito de la actividad y ejecuta todos los script de perfil pertinentes. Esto le permite rastrear información sobre la visita como, por ejemplo, la ubicación del visitante, la hora del día, la cantidad de veces que el visitante ha estado en el sitio, si había realizado compras con anterioridad, etc. A continuación, esta información se agrega al perfil del visitante con el objetivo de rastrear mejor su actividad en el sitio.

Los atributos de script de perfil tienen la etiqueta `user.` insertada antes del nombre de atributo. Por ejemplo:

```
if (mbox.name == 'Track_Interest') { 
    if (profile.get('model') == "A5" &&; profile.get('subcat') == "KS6") { 
        return (user.get('A5KS6') || 0) + 1; 
    } 
}
```

* Haga referencia a los atributos de script de perfil (incluido el que se está usando) en el código con `user.get('parameterName')`.
* Guarde las variables a las que posiblemente se vaya a tener acceso la próxima vez que se ejecute el script (en la siguiente solicitud de mbox) con `user.setLocal('variable_name', 'value')`. Haga referencia a la variable con `user.getLocal('variable_name')`. Esto es práctico en situaciones en las que se quiere remitir a la fecha y hora de la última solicitud.
* Los parámetros y valores hacen distinción de mayúsculas y minúsculas. Haga que las mayúsculas y minúsculas de los parámetros y valores que va a recibir durante la actividad o prueba sean las mismas.
* Consulte la sección “Referencia JavaScript para parámetros de perfil de secuencia de comandos” para obtener más sintaxis de JavaScript.

## Visualización de tarjetas de información de scripts de perfil {#section_18EA3B919A8E49BBB09AA9215E1E3F17}

Puede ver tarjetas emergentes con información sobre scripts de perfil similares a las tarjetas de información de ofertas. Estas tarjetas le permiten ver la lista de actividades que hacen referencia al script de perfil seleccionado, además de otros metadatos útiles.

Por ejemplo, a la siguiente tarjeta de información se accede pasando el cursor sobre un script de perfil en la lista Scripts de perfil (Audiencias &gt; Scripts de perfil) y, a continuación, haciendo clic en el icono Información.

La pestaña [!UICONTROL Información de script] contiene la siguiente información: Nombre, Estado, Tipo de token, ID de script, Registro de cambios y Descripción.

![Tarjeta de información de script de perfil](assets/profile_script_info_card.png)

La pestaña [!UICONTROL Uso del script] enumera las actividades (y sus espacios de trabajo) que hacen referencia al script de perfil seleccionado.

![Tarjeta de información de script de perfil &gt; Pestaña Uso de script](assets/profile_script_info_card_usage_tab.png)

>[!Note]
>
>La pestaña Uso del script no muestra las actividades que hacen referencia al script de perfil seleccionado en las situaciones siguientes:
> * La actividad se encuentra en estado de Borrador.
> * El contenido u oferta utilizado en la actividad emplea variables de script (una oferta en línea dentro de la actividad o una oferta de la biblioteca de ofertas).



## Target deshabilita los scripts de perfil en determinadas situaciones {#section_C0FCB702E60D4576AD1174D39FBBE1A7}

[!DNL Target] deshabilitará automáticamente los scripts de perfil en determinadas situaciones, como cuando tardan mucho en ejecutarse o tienen demasiadas instrucciones.

Cuando se deshabilita un script de perfil, aparece un icono de alerta amarillo junto al script del perfil en la interfaz de usuario de Target, como se muestra a continuación:

![](assets/profile_script_invalid.png)

Al pasar el ratón por encima, aparecen los detalles del error, como se muestra a continuación:

![](assets/profile_script_hover.png)

Estas son las razones habituales por las que el sistema deshabilita los scripts de perfil:

* Se hace referencia a una variable sin definir.
* Se hace referencia a un valor no válido. Esto suele deberse a valores de redirección URL y otros datos introducidos por el usuario sin la validación adecuada.
* Se están utilizando demasiadas instrucciones JavaScript. Target tiene un límite de 2000 instrucciones JavaScript por script, pero esto no se puede calcular simplemente de forma manual leyendo el JavaScript. Por ejemplo, Rhino trata todas las llamadas de función y “nuevas” llamadas como 100 instrucciones. Además, el tamaño de los datos de entrada, como los valores URL, puede afectar a la contabilización de instrucciones.
* Elementos no destacados en la sección [prácticas recomendadas](../../c-target/c-visitor-profile/profile-parameters.md#section_64AFE5D2B0C8408A912FC2A832B3AAE0) a continuación.

## Prácticas recomendadas {#best}

Las siguientes directrices pretenden ayudarle a escribir secuencias de comandos de perfil simplificadas que tengan la menor probabilidad de caer en errores mientras escribe el código que falla, por lo que se procesa sin forzar una parada de secuencia de comandos del sistema. Estas instrucciones son el resultado de las prácticas recomendadas cuya eficacia ha sido demostrada. Estas directrices se tiene que aplicar junto a los principios y recomendaciones descritos por la comunidad de desarrollo Rhino.

* Establezca el valor del script actual en una variable local del script de usuario; establezca una conmutación por error a una cadena en blanco.
* Valide la variable local y asegúrese de que no se trate de una cadena en blanco.
* Utilice funciones de manipulación basadas en cadenas en lugar de expresiones regulares.
* Utilice bucles limitados en lugar de bucles sin fin o continuos.
* No supere los 1300 caracteres o las 50 repeticiones de bucle.
* No supere las 2000 instrucciones de JavaScript. Target tiene un límite de 2000 instrucciones JavaScript por script, pero esto no se puede calcular simplemente de forma manual leyendo el JavaScript. Por ejemplo, Rhino trata todas las llamadas de función y “nuevas” llamadas como 100 instrucciones. Además, el tamaño de los datos de entrada, como los valores URL, puede afectar a la contabilización de instrucciones.
* Tenga en cuenta no solo el rendimiento del script, sino también el rendimiento combinado de todos los scripts. Como práctica recomendada, debería utilizarse un máximo de 5000 instrucciones en total. La recuento de instrucciones no es obvio, pero el dato que es importante recordar es que los scripts que exceden los 2 KB se desactivan automáticamente. No hay límite al número de scripts que se pueden ejecutar, pero cada uno de ellos se ejecuta con cada llamada de mbox. Ejecute solo los scripts necesarios.
* En un regex, tener punto-star al principio (p. ej.: `/.*match/`, `/a|.*b/`) casi nunca se necesita. La búsqueda regex comienza desde todas las posiciones de una cadena (a menos que esté enlazada con `^`), por lo que ya se da por supuesto la estrella de punto. La ejecución de la secuencia de comandos puede interrumpirse si este tipo de regex coincide con datos de entrada lo suficientemente largos (que pueden ser tan bajos como varios cientos de caracteres).
* Si falla todo, ajuste el script a un try/catch.
* See the JS Rhino engine documentation for more information: [https://www.mozilla.org/rhino/doc.html](https://www.mozilla.org/rhino/doc.html).

## Scripts de perfil para probar actividades mutuamente exclusivas {#section_FEFE50ACA6694DE7BF1893F2EFA96C01}

Puede usar atributos de perfil para definir pruebas que comparen dos o más actividades, pero sin permitir que los mismos visitantes participen en cada una de ellas.

La prueba de actividades mutuamente exclusivas evita que un visitante de una campaña afecte a los resultados de la prueba para el resto de actividades. Cuando un visitante participa en diversas actividades, puede resultar difícil determinar si se ha producido un alza positiva o negativa de la experiencia del visitante con una actividad o si interacciones entre varias actividades han afectado a los resultados de una o más actividades.

Por ejemplo, puede probar dos áreas del sistema de comercio electrónico. Es posible que desee probar a crear un botón Agregar al carro de compras rojo en lugar de azul. También puede desear probar un nuevo proceso de cierre de compra que reduzca el número de pasos de cinco a dos. Si ambas actividades tienen el mismo evento de éxito (una compra completada), puede resultar difícil determinar si el botón rojo mejora las conversiones o si las mismas conversiones también aumentan debido al proceso de cierre de compra mejorado. Al separar las pruebas en actividades mutuamente exclusivas, puede probar cada fase de forma independiente.

Tenga en cuenta la siguiente información cuando utilice uno de los siguientes scripts de perfil:

* La secuencia de comandos de perfil debe ejecutarse antes de que la actividad se inicie y la secuencia de comandos no debe modificarse mientras dure la actividad.
* Esta técnica reducirá la cantidad de tráfico en la actividad, lo que podría requerir que la actividad se ejecute durante más tiempo. Debe tener en cuenta este hecho cuando calcule la duración de la actividad.

### Configuración de dos actividades

Para clasificar los visitantes en grupos para que cada uno de ellos vea una actividad diferente, debe crear un atributo de perfil. Un atributo de perfil puede clasificar a un visitante en uno de dos o más grupos. Para definir un atributo de perfil denominado “twogroups”, cree la secuencia de comandos siguiente:

```
if (!user.get('twogroups')) { 
    var ran_number = Math.floor(Math.random() * 99); 
    if (ran_number <= 49) { 
        return 'GroupA'; 
    } else { 
        return 'GroupB'; 
    } 
}
```

`if (!user.get('twogroups'))` determina si el atributo de perfil *twogroups* se establece para el visitante actual. Si es así, no es necesario realizar ninguna otra acción.

`var ran_number=Math.floor(Math.random() *99)` declara una nueva variable denominada ran_number, configura su valor en un decimal aleatorio entre 0 y 1 y, a continuación, lo multiplica por 99 y lo redondea a la baja para crear un rango de 100 (0-99) que resulta útil para especificar el porcentaje de visitantes que ven la actividad.

`if (ran_number <= 49)` comienza una rutina que determina el grupo al que pertenece el visitante. Si el número devuelto está entre 0 y 49, el visitante se asigna a GrupoA. Si el número devuelto está entre 50 y 99, el visitante se asigna a GrupoB. El grupo determina qué actividad ve el visitante.

Una vez creado el atributo de perfil, ajuste la primera actividad para que se dirija a la población que desee a través de la solicitud de que el parámetro de perfil de usuario user.twogroups coincida con el valor especificado para GrupoA.

>[!NOTE]
>
>Seleccione uno de los primeros mbox de la página. Este código determina si un visitante experimenta la campaña. Siempre que el navegador encuentre primero un mbox, se puede utilizar para definir este valor.

Defina la segunda campaña de forma que el parámetro de perfil de usuario `user.twogroups` coincida con el valor especificado para GrupoB.

### Configuración de tres o más actividades

La configuración de tres o más actividades mutuamente exclusivas es similar a la configuración de dos, pero debe modificar el atributo de perfil de JavaScript para crear un grupo independiente para cada actividad y determinar quién ve cada una de ellas. La generación de números aleatorios es diferente en función de si crea un número par o impar de grupos.

Por ejemplo, para crear cuatro grupos, use el siguiente JavaScript:

```
if (!user.get('fourgroups')) { 
    var ran_number = Math.floor​(Math.random() * 99); 
    if (ran_number <= 24) { 
        return 'GroupA'; 
    } else if (ran_number <= 49) { 
        return 'GroupB'; 
    } else if (ran_number <= 74) { 
        return 'GroupC'; 
    } else { 
        return 'GroupD'; 
    } 
}
```

En este ejemplo, la coincidencia que se utiliza para generar el número aleatorio que asigna un visitante a un grupo es la misma que con solo dos grupos. Se genera un decimal aleatorio y, a continuación, se redondea a la baja para crear un número entero.

Si crea un número impar de grupos, o cualquier número que no se divida por 100 de forma equitativa, no deberá redondear el decimal a la baja para obtener un número entero. La falta de redondeo del decimal permite especificar rangos de números no enteros. Para ello, cambie esta línea:

`var ran_number=Math.floor(Math.random()*99);`

a:

`var ran_number=Math.random()*99;`

Por ejemplo, para colocar a los visitantes en tres grupos iguales, use el siguiente código:

```
if (!user.get('threegroups')) { 
    var ran_number = Math.random() * 99; 
    if (ran_number <= 32.33) { 
        return 'GroupA'; 
    } else if (ran_number <= 65.66) { 
        return 'GroupB'; 
    } else { 
        return 'GroupC'; 
    } 
}
```

## Depuración de scripts de perfil {#section_E9F933DE47EC4B4E9AF2463B181CE2DA}

Se pueden utilizar los métodos siguientes para depurar scripts de perfil:

>[!NOTE]
>
>El uso de [!DNL console.log] en un script de perfil no genera el valor del perfil, ya que los scripts de perfil se ejecutan en el servidor.

* **Agregar scripts de perfil como tokens de respuesta para depurar scripts de perfil:**

   En Target, haga clic en **[!UICONTROL Configuración]** y en **[!UICONTROL Tokens de respuesta]**. Después, active el script de perfil que desea depurar.

   Cada vez que carga para el sitio una página que incluye Target, parte de la respuesta de Target contendrá su valor para el script de perfil dado, como se muestra a continuación:

   ![](assets/debug_profile_script_1.png)

* **Utilice la herramienta de depuración mboxTrace para depurar scripts de perfil.**

   Este método requiere un token de autorización que puede generarse haciendo clic en **[!UICONTROL Target]** &gt; **[!UICONTROL Configuración]** &gt; **[!UICONTROL Implementación]** &gt; **[!UICONTROL Generar token de autorización]**.

   A continuación, agregue estos dos parámetros a la URL de su página después de “?”: `mboxTrace=window&authorization=YOURTOKEN`.

   Proporciona algo más de información que el token de respuesta porque se obtiene una instantánea de su perfil anterior a la ejecución y otra posterior a la ejecución. También muestra todos los perfiles disponibles.

   ![](assets/debug_profile_script_2.png)

## Preguntas más frecuentes sobre scripts de perfil {#section_1389497BB6D84FC38958AE43AAA6E712}

**¿Es posible utilizar scripts de perfil para capturar información de una página que reside en una capa de datos?**

Los scripts de perfil no pueden leer la página directamente porque se ejecutan en el lado del servidor. Los datos se deben pasar a través de una solicitud de mbox o a través de otros [métodos de obtención de datos en Target](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17). Una vez que los datos están en Target, los scripts de perfil pueden leer los datos como un parámetro de mbox o un parámetro de perfil.

## Referencia de JavaScript para parámetros de perfil de secuencia de comandos

Se requiere de conocimiento básico de Javascript para utilizar de forma eficaz los parámetros de perfil de secuencia de comandos. Esta sección sirve como referencia rápida para aumentar su productividad con esta funcionalidad en solo unos minutos.

Los parámetros de perfil de secuencia de comandos se encuentran en la pestaña mboxes/perfiles. Puede escribir programas Javascript que devuelvan cualquier tipo de Javascript (cadena, número entero, matriz, etc.).

### Ejemplos de parámetros de perfil de secuencia de comandos

**Nombre:** *user.recency*

```
var dayInMillis = 3600 * 24 * 1000;
if (mbox.name == 'orderThankyouPage') {
    user.setLocal('lastPurchaseTime', new Date().getTime());
}
var lastPurchaseTime = user.getLocal('lastPurchaseTime');
if (lastPurchaseTime) {
    return ((new Date()).getTime() - lastPurchaseTime) / dayInMillis;
}
```

Crea una variable por día según se mide en milisegundos. Si el nombre del mbox es `orderThankyouPage`, establece un atributo de perfil de usuario local (invisible) denominado `lastPurchaseTime` para que se tome el valor de la fecha y la hora actuales. El valor de la última compra se lee y, si se define, devuelve el tiempo que ha pasado desde la última compra, dividido por el número de milisegundos en un día (lo que resulta en el número de días desde la última compra).

**Nombre:** *user.frequency*

```
var frequency = user.get('frequency') || 0;
if (mbox.name == 'orderThankyouPage') {
    return frequency + 1;
}
```

Crea una variable denominada frecuencia, iniciándola en el valor anterior o 0, si no había ningún valor anterior. Si el nombre del mbox es `orderThankyouPage`, se devuelve el valor incrementado.

**Nombre:** *user.monetaryValue*

```
var monetaryValue = user.get('monetaryValue') || 0;
if (mbox.name == 'orderThankyouPage') {
    return monetaryValue + parseInt(mbox.param('orderTotal'));
}
```

Crea una variable llamada `monetaryValue`, buscando el valor actual para un visitante determinado (o configurándolo en 0 si no había ningún valor anterior). Si el nombre del mbox es `orderThankyouPage`, se devuelve un nuevo valor monetario sumando el valor anterior y el valor del parámetro `orderTotal` que se pasa al mbox.

### Objetos y métodos

Los parámetros de perfil de secuencia de comandos pueden hacer referencia a las siguientes propiedades y métodos:

| Objeto o método | Detalles |
| --- | --- |
| `page.url` | La dirección URL actual |
| `page.protocol` | El protocolo usado para la página (http o https). |
| page.domain | El dominio URL actual (todo antes de la primera barra). Por ejemplo, `www.acme.com` en `http://www.acme.com/categories/men_jeans?color=blu e&size=small`. |
| `page.query` | La cadena de consulta de la página actual. Todo después de “?”. Por ejemplo, `blue&size=small` en `http://www.acme.com/categories/mens_jeans?color=blue&size=small`. |
| `page.param(‘<par_name>’)` | El valor del parámetro indicado por `<par_name>`. Si la dirección URL actual es la página de búsqueda de Google y había introducido `page.param('hl')`, obtendrá “en” para la dirección URL `http://www.google.com/search?hl=en& q=what+is+asdf&btnG=Google+Search`. |
| `page.referrer` | El mismo conjunto de operaciones que se aplica arriba se aplica al referente y al aterrizaje (por ejemplo, referrer.url será la dirección URL del referente). |
| `landing.url`, `landing.protocol`, `landing.query`, y `landing.param` | Similar a la de la página, pero para la página de aterrizaje. |
| `mbox.name` | El nombre del mbox activo. |
| `mbox.param(‘<par_name>’)` | Un parámetro de mbox por el nombre dado en el mbox activo. |
| `profile.get(‘<par_name>’)` | El parámetro de perfil de usuario creado por el cliente por el nombre `<par_name>`. Por ejemplo, si el usuario configura un parámetro de perfil denominado “gender”, el valor se puede extraer usando “profile.gender”. Devuelve el valor de “`profile.<par_name>`” configurado para el visitante actual; devuelve nulo si no se ha establecido ningún valor. |
| `user.get(‘<par_name>’)` | Devuelve el valor de “`user.<par_name>`” configurado para el visitante actual; devuelve nulo si no se ha establecido ningún valor. |
| `user.categoryAffinity` | Devuelve el nombre de la mejor categoría. |
| `user.categoryAffinities` | Devuelve una matriz con las mejores categorías. |
| `user.isFirstSession` | Devuelve verdadero si es la primera sesión del visitante. |
| `user.browser` | Devuelve el agente de usuario en el encabezado HTTP. Como por ejemplo, puede crear un objetivo de expresión únicamente dirigido a los usuarios de Safari: `if (user.browser != null && user.browser.indexOf('Safari') != -1) { return true; }` |

### Operadores comunes


Todos los operadores de JavaScript estándar están presentes y pueden utilizarse. Los operadores JavaScript se pueden utilizar en cadenas y números (así como en otros tipos de datos). Una breve explicación:

| Operador | Descripción |
| --- | --- |
| `==` | Indica igualdad. Es verdadero cuando los operandos de ambos lados son iguales. |
| `!=` | Indica desigualdad. Es verdadero cuando los operandos de ambos lados no son iguales. |
| `<` | Indica que la variable a la izquierda es menor que la variable de la derecha. Evaluará en falso si las variables son iguales. |
| `>` | Indica que la variable a la izquierda es mayor que la variable de la derecha. Evaluará en falso si las variables son iguales. |
| `<=` | Igual que `<`, excepto si las variables son iguales, que entonces se evaluará en verdadero. |
| `>=` | Igual que `>`, excepto si las variables son iguales, que entonces se evaluará en verdadero. |
| `&&` | Lógicamente “Y” las expresiones a la izquierda y a la derecha de la misma, son solo verdaderas cuando ambos lados son verdaderos (falso en caso contrario). |
| `||` | Lógicamente “O” las expresiones a la izquierda y a la derecha de la misma, son solo verdaderas si uno de los lados es verdadero (falso en caso contrario). |
| `//` | Comprueba si la fuente contiene todos los elementos que el booleano de destino contiene (origen de matriz, destino de matriz).<br>`//` extrae la subcadena de destino (correspondiente a regexp) y la descodifica `Array/*String*/ decode(String encoding, String regexp, String target)`.<br>La función también es compatible con el uso de valores de cadena constantes, agrupación (`condition1 || condition2) && condition3` y expresiones regulares (`/[^a-z]$/.test(landing.referring.url)`. |

## Vídeo de formación: Scripts de perfil

En este vídeo se explica cómo usar y crear scripts de perfil.

* Explicar qué es un script de perfil
* Explicar en qué se diferencia un script de perfil de un parámetro de perfil
* Crear un script de perfil simple
* Usar el menú Token disponible para acceder a las opciones disponibles
* Habilitar y deshabilitar scripts de perfil

>[!VIDEO](https://video.tv.adobe.com/v/17394?captions=spa)