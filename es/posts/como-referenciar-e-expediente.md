---
title: "¿Cómo referenciar en el e-expediente?"
description: "¿Qué hay detrás de un nombre?"
tags: ["e-expediente", "fojas", "math", "judisoft", "qr"]
draft: false
date: 2024-03-10
featured_featured_image: "images/papers.png"
slug: "como-referenciar-en-el-expedienté-electronico"
---

## Fojas.

No podemos atarearnos con nada sin nombrarlo. Y el nombre tiene que reunir ciertas características, pero la que nos importa es que sea único dentro del universo de cosas que queremos nombrar, que no dé lugar a equívocos. Un ejemplo famoso es el de Odiseo que se hace nombrar << Nadie >> en la cueva de Polifemo. De esa manera no importa que este grite que << Nadie lo mata >>. Nadie acudirá en su auxilio.

Antes cuando teníamos que nombrar una pieza del expediente ---digamos un escrito que se presentó en autos--- lo único que teníamos que usar era una fórmula tipo << _a_ fojas _x_ de los autos _a_ | desde fojas _x_ a fojas _y_ >>.

Hoy ya no existen tales fojas y seguimos necesitando la referencia. 

Los juzgados mismos lidian con el mismo problema, pero a veces se limitan a poner: estése[^1] como en los viejos tiempos en que el hombre era joven y siempre le sobraban dos soberanos para la cerveza. Y uno no sabe si a cuales de los 10 escritos anteriores se refiere.

[^1]: <<Estése .. $loquesea>> es siempre una providencia que no dice nada y que deberá ser recurrida en aclaratoria sí o sí. Hay otras.

Para muchas personas es suficiente con citar la fecha y transcribir el título del escrito. Y en general estimo que puede ser suficiente.

Claro que pueden echarle un ojo a dos escritos similares pero con horas distintas y QR identicos. La vida no siempre es buena.

[Double, double toil and trouble.](http://304.villalba.is.eu.org/double-trouble/hashes.html)

Pero usualmente, bajo condiciones normales de presión y temperatura, el Judisoft asigna un numero unico: _n_.pdf. Donde _n_ es un número 'integer'.

Así que una buena referencia sería _el escrito de nulidad presentado por la demandada el día 27 de los corrientes bajo el documento 34343.pdf_

## ¿Y los links?

No podemos usarlos porque son internos del Judisoft y solo una persona que esté logueada puede verlos. Y asumimos que personas que no tienen a mano el Judisoft podrían querer verlo.

Una opción válida es usar una carpeta en la red y espejear allí los documentos (recuerden que aún es importante tener nuestra copia, aún las empresas más sofisticadas de almacenamiento han perdido datos de sus clientes por _a_ o _b_ motivo).

## Dime si hay alguna esperanza.

### Storage

Así que no sería malo tener un dominio y una carpeta en la red. Publicidad sigue: en [interserver](https://www.interserver.net/vps/?id=910602) cuesta 3 USD por mes 200M de 'storage' sencillos y claros, pero es muy caro si un lo compara con B2 que por ese precio ---pero pagado por año--- otorga 1 Terabyte, pero quien necesita un Terabyte de almacenamiento en B2? Además, les advierto que usarlo no es algo sencillo de hacer.

Así que la referencia quedaría << $palabras .. cuya copia obra en https://_el-dominio-chungo-que-me-dieron_/caso/34556.pdf >>.

Claro que uno puede adquirir uno propio, por ejemplo: el-segundo-mejor-abogado.com.

### IPFS

Acá olvida dominios.

En el mismo orden de cosas se encuentran los espacios de la IPFS. Todos los `pdfs` del sitio están en la red IPFS, como ven: Algunas veces están caídos. Es porque me excedo en mi cuota. Por lo general, tienen cuotas más que accesibles y las cuentas vienen con espacio gratuito que para nuestro uso profesional es suficiente. Ojo: algun tipo de conocimiento específico es aún necesario:

| 4EVERLAND | FILEBASE |
| ---- | ---- |
| [{{< imgwidth src="https://minimum-tomato-hamster.myfilebase.com/ipfs/QmcG2s1MKy3Joi1DH9Dy3DUz8MPdR4oeQsPMXnYurYupJb/" width="200px" >}}](https://dashboard.4everland.org?invite=ZYIDXZL0)| [{{< imgwidth src="https://console.filebase.com/assets/logo-white-no-background-d9d98f812cad5c5ea23cf7da98a35a12ef0b6ccc7f3e8ad91233aa0e23ddc7d3.svg/" width="200px" >}}](https://console.filebase.com/signup?ref=d3981dab17bd) |

Son los dos recomendaria por su facilidad de uso.

### Tradicional

El tradicional web-hosting es usualmente uno que tiene aceso limitada a un servidor Apache y php. Pero el php` corre de manera bastante ilimitada. Actualment existe versiones pagas de esta clase de hosting y en cantidades muchas.

## Más datos.

Al final de cada escrito que presentamos hay un número. 

{{< img src="https://bafkreidgns2w2rqpdtciju6o5weyxxuh57ixrn5hh4hxbcstjy6thptbqy.ipfs.nftstorage.link/" >}}

En este caso es:

```
6E5B993F99C32EC5D2C61AB8DF0796
E86E5B993F99C32EC5D2C61AB8DF07
96E86E5B993F99C32EC5D2C61AB8DF
0796E86E5B993F99C32EC5D2C61AB8
DF0796E86E5B993F99C32EC5D2C61A
B8DF0796E86E5B993F99C32EC5D2C
```

Es fácil ver que no es sino 6E5B993F99C32EC5D2C61AB8DF0796E8 que se repite una y otra vez. ¿Qué es? Si alguien sabe que me lo cuente. Probablemente es un [hash](https://cau.sci.uma.es/faq/index.php?action=artikel&cat=60&id=181&artlang=es), pero de qué. Sí sé para qué sirve aunque no recuerdo la manera en que llegué a ello. Ese número valida nuestra presentación. Si se fijan en la '''e-Acordada''', la misma habla de una cosa así.

> Postdata urgente!
> Bajo ninguna circunstancia se debe volver a usar el link validador. El Servidor lo reporta como ataque! 
> [6E5B993F99C32EC5D2C61AB8DF0796E8](https://villalba.is)

El link que produce nos muestra algunos datos de nuestra presentación, no nuestro escrito. Esto merece un comentario, pero si desean conocer detalles pueden escribir en la caja de abajo.

Este link también nos puede servir para referenciar un escrito. 

## El extraño indescifrable QR al final del arco iris.

Pero al lado hay un QR. Que no se puede leer. Como no se si está movido de propósito, no quiero ahondar en el tema. Porque si está movido de propósito señala una intención la de ocultar, siquiera de manera parcial, un dato. Aunque nadie pone un QR si no quiere que se lo escanee.

Como dicen los malos vendedores o estafadores de las redes sociales: ¡al inbox!


