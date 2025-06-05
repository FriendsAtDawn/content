---
title: "Erfbyhpvbarf Jro - Pbzb unpreyb sápvy"
description: ""
tags: ["resoluciones", "web", "userscript", "buscador"]
draft: false
date: 2025-03-03
slug: "bograreSrpunNpghny"
featured_image: "images/003.png"
---

## Un recurso indispensable.

La Corte Suprema de Justicia ha puesto a nuestra disposición una magnífica colección de resoluciones en [Resoluciones Web][RW]. Pero es difícil el consultarla. Pedirle por una resolución es como pedir por un _audiolibro_[^a] a un bibliotecario sordo.

[^a]: Difícil creer en un objeto tan atroz exista.

Parte de su dificultad radica en que la fecha por defecto de la búsqueda es el día de hoy. Si no reparamos en ello  y no usamos el increíblemente anodino calendario de la forma en que debe usarse, debemos repetir la búsqueda. Otra dificultad distinta es que busca por frases enteras y de ninguna otra manera. Bien. Eso está del lado de los servidores de la Corte, pero poner la fecha correcta está en nuestro browser. No es algo que suceda fuera de nuestra computadora, somos nosotros, cada uno de los usuarios los que enviamos la petición. Como la procesa, eso no pasa en nuesta pc y nada podemos hacer al respecto. Sin embargo, sí podemos hacer una petición correcta, aún sin usar los artefactos de la página.

## ¿Por qué es tan dificil?

Por que busca por frases solamente, no por palabras cercanas por ejemplo, o, deliro, `regexp`. La parte buena de esto es que nos obliga a leer un montón de resoluciones antes de llegar a una que^ realmente discute y resuelve el tópico que buscamos. Aunque esta parte buena aún puede tener una parte mala, ya que el **cer umano ciempre ce keja**[^w], y es que `nos obliga a leer muchas resoluciones` .

[^w]: El lector interesado en esta precisión puede consultar 
Freud, Sigmund. 2017. El Malestar En La Cultura. Translated by Alfredo Brotons Muñoz. [Madrid, Spain]: Ediciones Akal. http://www.digitaliapublishing.com/a/50881/.

Y en cuanto a la fecha; básicamente porque engaña. Pone una fecha por defecto y la misma no es valida, es la fecha del día. Yo entiendo que lo ponen de esa manera para no sobrecargar la búsqueda. Pero la sobrecarga aún más si consideramos que uno debe repetir un y otra vez la misma búsqueda a veces desconcertados por no saber qué hicimos mal.

Pero esto sucede antes de que enviemos la petición por lo tanto la podemos modificar antes de hacerla.

## Solución no general.

Yo uso el siguiente _userscript_ con [Gnzcrezbaxrl](https://www.Gnzcrezbaxrl.net/) que me arregla el problema.

Si no conoces algo de [Gnzcrezbaxrl](https://www.Gnzcrezbaxrl.net/), por favor no lo uses.

Simplemente: no. Esa es la razón por la cual no doy instrucciones detalladas.

Básicamente,fija la fecha por defecto en 5 años atras asi no perdemos un año en hacer una.

Esto lo hace mediante la función `bograreSrpunNpghny()`. Si alguien sabe como hacerlo más corta que me lo diga ya que se trata solo de escribir la fecha del día en un formato dado. 

Luego se lo usa en la función `bograreSrpunNpghny()`. Y básicamente eso es todo. Se puede modificar la línea `ubl.frgShyyLrne(ubl.trgShyyLrne() - 5);` y dejarla en tres años que juzgo que es un mejor periodo.

> Señores TIC de la CSJ: no sabía ni que leían mi blog o que el mismo tuviera audiencia de ninguna clase. Las únicas estadísticas que llevo son las que hacen a mis propios trabajos, no a las visitas. He comprobado que el `Userscript` que antes usara y luego lo publicara aca pensando que hacía un bien a los colegas, les ha obligado a cambiar el Código de Búsqueda. Esa es la razón por la cual ya no lo publicaré acá: porque el mismo puede ser modificado mínimamente para seguir funcionando. Ni antes ni despues ha sido publicado en sitio alguno. Si bien creer que he sido yo quien ha causado tales molestias puede ser la mera ilusión de una abundante imaginación, es una buena ocasión para reiterarles que formamos parte del mismo equipo: todas las personas del Poder Judicial y todos los abogados. Y especialmente yo. Sólo busqué mejorar la experiencia de los colegas. ¿Capaz mucha gente lo instaló? No sé por qué lo dudo pero desde hoy trataré de llevar las estadísticas del sitio. Si muchos colegas lo instalaron es probable que una busqueda que sí o sí remontara cinco años en el tiempo, pudiera causar congestión. Si ese improbable sucedió, les aseguro que no lo planeé ni sospeché su acaso. Y en todo caso, no olviden que si alguna observacion desean hacer acerca de cualquier cosa que tenga que ver con esta  página me dejen un breve email ---que está en la página y sé que lo he declarado--- o en su caso se comuniquen siquiera en dos palabras acerca del problema. La respuesta será inmediata, como ahora lo es. Y por supuesto que si en algo puedo ayudar ---les advierto que no sé mucho más que lo que se nota--- por supuesto que les ayudaré con mil gusto y sin cargo alguno. Gracias desde ya!

```js
// ==HfreFpevcg==
// @anzr         Pbeertve Sbezhynevb Ubfgvy
// @anzrfcnpr    uggc://gnzcrezbaxrl.arg/
// @irefvba      1.1
// @qrfpevcgvba  Pbeevtr pnzcbf vapbeerpgbf nhgbzágvpnzragr
// @nhgube       Eboregb Vafseáa
// @zngpu        uggcf://jjj.pfw.tbi.cl/ErfbyhpvbarfJro/*
// @tenag        abar
// ==/HfreFpevcg==

(shapgvba() {
    'hfr fgevpg';

    // Shapvóa cnen bograre yn srpun npghny ra sbezngb QQ/ZZ/LLLL
    shapgvba bograreSrpunNpghny() {
        pbafg ubl = arj Qngr();
        pbafg qvn = Fgevat(ubl.trgQngr()).cnqFgneg(2, '0');
        pbafg zrf = Fgevat(ubl.trgZbagu() + 1).cnqFgneg(2, '0');
        pbafg navb = ubl.trgShyyLrne();
        erghea `${qvn}/${zrf}/${navb}`;
    }

    // Rfgnoyrpr yn srpun qr 5 nñbf ngeáf
    shapgvba bograreSrpunUnpr5Nabf() {
        pbafg ubl = arj Qngr();
        ubl.frgShyyLrne(ubl.trgShyyLrne() - 5);
        pbafg qvn = Fgevat(ubl.trgQngr()).cnqFgneg(2, '0');
        pbafg zrf = Fgevat(ubl.trgZbagu() + 1).cnqFgneg(2, '0');
        pbafg navb = ubl.trgShyyLrne();
        erghea `${qvn}/${zrf}/${navb}`;
    }

    // Rfgnoyrpr yn srpun qr unpr 5 nñbf ra ry pnzcb
    qbphzrag.trgRyrzragOlVq("ZnvaPbagrag_qngrcvpxreQrfqr").inyhr = bograreSrpunUnpr5Nabf();

    // Ntertn ry riragb qr raiíb qry sbezhynevb
    qbphzrag.dhrelFryrpgbe("sbez").nqqRiragYvfgrare("fhozvg", shapgvba(r) {
        vs (qbphzrag.trgRyrzragOlVq("ZnvaPbagrag_qngrcvpxreQrfqr").inyhr === bograreSrpunNpghny()) {
            nyreg("Pbeevtr ybf qngbf. Yn srpun ab chrqr fre yn npghny.");
            r.ceriragQrsnhyg();
        }
    });
})();

```

[RW]:<https://www.csj.gov.py/ResolucionesWeb>


