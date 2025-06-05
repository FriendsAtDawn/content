---
title: "Resoluciones Web - Como hacerlo fácil"
description: ""
tags: ["resoluciones", "web", "userscript", "buscador"]
draft: false
date: 2025-03-03
---

## Un recurso indispensable.

La Corte Suprema de Justicia ha puesto a nuestra disposición una magnífica colección de resoluciones en [Resoluciones Web][RW]. Pero es difícil el consultarla. Pedirle por una resolución es como pedir por un _audiolibro_[^a] a un bibliotecario sordo.

[^a]: Difícil creer en un objeto tan atroz exista.

Parte de su dificultad radica en que la fecha por defecto de la búsqueda es el día de hoy. Si no reparamos en ello  y no usamos el increíblemente anodino calendario de la forma en que debe usarse, debemos repetir la búsqueda. Otra dificultad distinta es que busca por frases enteras y de ninguna otra manera. Bien. Eso está del lado de los servidores de la Corte, pero poner la fecha correcta está en nuestro browser. No es algo que suceda fuera de nuestra computadora, somos nosotros, cada uno de los usuarios los que enviamos la petición. Como la procesa, eso no pasa en nuesta pc y nada podemos hacer al respecto. Sin embargo, sí podemos hacer una petición correcta, aún sin usar los artefactos de la página.

## ¿Por qué es tan dificil?

Por que busca por frases solamente, no por palabras cercanas por ejemplo, o, deliro, `regexp`. La parte buena de esto es que nos obliga a leer un montón de resoluciones antes de llegar a una que^ realmente discute y resuelve el tópico que buscamos. Aunque esta parte buena aún puede tener una parte mala, ya que el **cer umano ciempre ce keja**[^w], y es que `nos obliga a leer muchas resoluciones` .

[^w]: El lector interesado en esta precisión puede consultar "El malestar en la Cultura", Sigmund Freud.

Y en cuanto a la fecha; básicamente porque engaña. Pone una fecha por defecto y la misma no es valida, es la fecha del día. Yo entiendo que lo ponen de esa manera para no sobrecargar la búsqueda. Pero la sobrecarga aún más si consideramos que uno debe repetir un y otra vez la misma búsqueda a veces desconcertados por no saber qué hicimos mal.

Pero esto sucede antes de que enviemos la petición por lo tanto la podemos modificar antes de hacerla.

## Solución no general.

Yo uso el siguiente _userscript_ con [Tampermokey](https://www.tampermonkey.net/) que me arregla el problema.

Si no conoces algo de [Tampermonkey](https://www.tampermonkey.net/), por favor no lo uses.

Simplemente: no. Esa es la razón por la cual no doy instrucciones detalladas.

Básicamente,fija la fecha por defecto en 5 años atras asi no perdemos un año en hacer una.

Esto lo hace mediante la función `obtenerFechaActual()`. Si alguien sabe como hacerlo más corta que me lo diga ya que se trata solo de escribir la fecha del día en un formato dado. 

Luego se lo usa en la función `obtenerFechaHace5Anos()`. Y básicamente eso es todo. Se puede modificar la línea `hoy.setFullYear(hoy.getFullYear() - 5);` y dejarla en tres años que juzgo que es un mejor periodo.

```js
// ==UserScript==
// @name         Corregir Formulario Hostil
// @namespace    http://tampermonkey.net/
// @version      1.1
// @description  Corrige campos incorrectos automáticamente
// @author       Roberto Insfrán
// @match        https://www.csj.gov.py/ResolucionesWeb/*
// @grant        none
// ==/UserScript==

(function() {
    'use strict';

    // Función para obtener la fecha actual en formato DD/MM/YYYY
    function obtenerFechaActual() {
        const hoy = new Date();
        const dia = String(hoy.getDate()).padStart(2, '0');
        const mes = String(hoy.getMonth() + 1).padStart(2, '0');
        const anio = hoy.getFullYear();
        return `${dia}/${mes}/${anio}`;
    }

    // Establece la fecha de 5 años atrás
    function obtenerFechaHace5Anos() {
        const hoy = new Date();
        hoy.setFullYear(hoy.getFullYear() - 5);
        const dia = String(hoy.getDate()).padStart(2, '0');
        const mes = String(hoy.getMonth() + 1).padStart(2, '0');
        const anio = hoy.getFullYear();
        return `${dia}/${mes}/${anio}`;
    }

    // Establece la fecha de hace 5 años en el campo
    document.getElementById("MainContent_datepickerDesde").value = obtenerFechaHace5Anos();

    // Agrega el evento de envío del formulario
    document.querySelector("form").addEventListener("submit", function(e) {
        if (document.getElementById("MainContent_datepickerDesde").value === obtenerFechaActual()) {
            alert("Corrige los datos. La fecha no puede ser la actual.");
            e.preventDefault();
        }
    });
})();

```

[RW]:<https://www.csj.gov.py/ResolucionesWeb>


