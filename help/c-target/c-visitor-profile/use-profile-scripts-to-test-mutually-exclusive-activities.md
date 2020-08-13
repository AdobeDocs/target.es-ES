---
keywords: Profile script;profile script attributes;mutually exclusive activities
description: Puede usar atributos de perfil para definir pruebas que comparen dos o más actividades, pero sin permitir que los mismos visitantes participen en cada una de ellas.
title: Utilice secuencias de comandos de perfil para probar actividades mutuamente excluyentes
feature: visitor profiles
topic: Advanced,Standard,Classic
uuid: a76ed523-32cb-46a2-a2a3-aba7f880248b
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 81%

---


# Use profile scripts to test mutually exclusive activities {#section_FEFE50ACA6694DE7BF1893F2EFA96C01}

Puede usar atributos de perfil para definir pruebas que comparen dos o más actividades, pero sin permitir que los mismos visitantes participen en cada una de ellas.

La prueba de actividades mutuamente exclusivas evita que un visitante de una campaña afecte a los resultados de la prueba para el resto de actividades. Cuando un visitante participa en diversas actividades, puede resultar difícil determinar si se ha producido un alza positiva o negativa de la experiencia del visitante con una actividad o si interacciones entre varias actividades han afectado a los resultados de una o más actividades.

Por ejemplo, puede probar dos áreas del sistema de comercio electrónico. Es posible que desee probar haciendo que el botón &quot;Añadir al carro&quot; sea rojo en lugar de azul. También puede desear probar un nuevo proceso de cierre de compra que reduzca el número de pasos de cinco a dos. Si ambas actividades tienen el mismo evento de éxito (una compra completada), puede resultar difícil determinar si el botón rojo mejora las conversiones o si esas mismas conversiones también se incrementaron debido al proceso de cierre de compra mejorado. Al separar las pruebas en actividades mutuamente exclusivas, puede probar cada fase de forma independiente.

Tenga en cuenta la siguiente información cuando utilice uno de los siguientes scripts de perfil:

* La secuencia de comandos de perfil debe ejecutarse antes de que la actividad se inicie y la secuencia de comandos no debe modificarse mientras dure la actividad.
* Esta técnica reduce la cantidad de tráfico en la actividad, lo que puede requerir que la actividad se ejecute durante más tiempo. Debe tener en cuenta este hecho cuando calcule la duración de la actividad.

## Configuración de dos actividades

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

* `if (!user.get('twogroups'))` determina si el atributo de perfil *twogroups* se establece para el visitante actual. Si es así, no es necesario realizar ninguna otra acción.

* `var ran_number=Math.floor(Math.random() *99)` declara una nueva variable denominada ran_number, configura su valor en un decimal aleatorio entre 0 y 1 y, a continuación, lo multiplica por 99 y lo redondea a la baja para crear un rango de 100 (0-99) que resulta útil para especificar el porcentaje de visitantes que ven la actividad.

* `if (ran_number <= 49)` comienza una rutina que determina el grupo al que pertenece el visitante. Si el número devuelto está entre 0 y 49, el visitante se asigna a GrupoA. Si el número devuelto está entre 50 y 99, el visitante se asigna a GrupoB. El grupo determina qué actividad ve el visitante.

After you create the profile attribute, set up the first activity to target the desired population by requiring that the user profile parameter `user.twogroups` matches the value specified for GroupA.

>[!NOTE]
>
>Seleccione uno de los primeros mbox de la página. Este código determina si un visitante experimenta la actividad. Siempre que el navegador encuentre primero un mbox, se puede utilizar para definir este valor.

Defina la segunda campaña de forma que el parámetro de perfil de usuario `user.twogroups` coincida con el valor especificado para GrupoB.

## Configuración de tres o más actividades

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
