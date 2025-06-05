---
title: "Validar ---pero fuera del Sistema"
description: "Judisoft."
tags: ["validación", "blockchain"]
draft: false
date: 2025-04-25
slug: "validar-fuera-del-sistema"
---

¿Que pasaría si... tuviéramos que reconstituir un expediente digital? Las resoluciones están firmadas por los jueces así que en más o en menos alli existe ya cierta seguridad. Y digo en más o en menos por la actual falta de timestamp. Pero... ¿Y las peticiones?


## Validación de documentos judiciales fuera del sistema Judisoft

La preocupación sobre cómo validar y reconstruir la autenticidad de documentos judiciales -especialmente las peticiones de abogados- en caso de que el sistema Judisoft de la Corte Suprema de Paraguay quede fuera de servicio es legítima y relevante. Actualmente, las resoluciones firmadas digitalmente ofrecen garantías de autenticidad, pero las peticiones de los abogados pueden no estar igual de protegidas.

### Estado actual de la firma digital y validación

- La Corte Suprema de Justicia de Paraguay ya implementa la firma digital en varios de sus documentos, lo que otorga seguridad y confianza a los documentos electrónicos, independientemente del medio en que se compartan. Esto reduce el uso de papel y aumenta la transparencia y seguridad de los servicios judiciales[^2].
- Para verificar la autenticidad de documentos generados por el Poder Judicial, se recomienda confirmar que el dominio de descarga sea el oficial (www.csj.gov.py) y corroborar visualmente la integridad del documento (colores, logos, QR, etc.)[^3].
- El marco legal paraguayo reconoce la validez jurídica y probatoria de los expedientes electrónicos y documentos firmados digitalmente, equiparándolos al expediente tradicional, según la Ley N° 4017/10 y su modificatoria, la Ley N° 4610/12[^7].


### Limitación actual

- Si bien las resoluciones están firmadas digitalmente y pueden validarse fuera del sistema, las peticiones de los abogados no necesariamente cuentan con la misma protección, lo que podría dificultar su validación en caso de caída o desaparición del sistema Judisoft. ---Piénsese en: hambruna, guerra termonuclear, colisión con objetos celestes, backups en pendrives, alzamiento en armas contra la tiranía, muerte súbita, terremotos, "sólo quise saber que hacía `rm -rf ~`", etc.


## Mejor manera de implementar una validación robusta

La Corte Suprema puede fortalecer la validación de documentos (especialmente peticiones de abogados) fuera del sistema Judisoft mediante las siguientes acciones:

**1. Sugerir se use firma digital de todas las presentaciones electrónicas**

- Proponer ---no hace falta que se obligue, porque cuando los colegas vean la ventaja, se acoplarán de manera espontánea--- que cada escrito presentado por abogados esté firmado digitalmente con un certificado emitido por una autoridad certificadora reconocida por la Corte Suprema, o por la misma Corte Suprema --- véase al respecto {{< link "no-valida" >}}

- Esto permitiría que cualquier copia del escrito pueda ser validada de manera independiente, usando software estándar (por ejemplo, Adobe Reader, que permite verificar firmas digitales y certificados de confianza)[^4].

Esta, que parece la solución más directa,  es en realidad la más aparatosa. Pues no considera que el Judisoft, por motivos de seguridad totalmente entendibles, despoja a cada pdf de toda información no visible. Lo que se dice, lo aplana. Sé que la acordada dice que cada pdf debe cumplir con cierto estándard, pero esto ya es exigir mucho por el momento.

**2. Incorporar sellos de tiempo y códigos de verificación**

- Además de la firma digital, agregar un sello de tiempo ---{{< link "firma-rota">}}--- y un código QR o alfanumérico único que vincule el documento a un registro verificable, incluso fuera del sistema principal. Ahora existe uno, pero no valida nada ni siquiera dentro del Sistema.

- El QR podría llevar a una página de verificación independiente, o permitir la validación offline mediante herramientas proporcionadas por la Corte, o proporcionadas por este enorme reloj que se llama internet.

**3. Publicar e instruir sobre la verificación de firmas digitales**

- Proveer guías y software para que cualquier usuario pueda validar la autenticidad e integridad de los documentos descargados, aun si el sistema central no está disponible[^4].
- Esto incluye la publicación de los certificados raíz ---quiero decir la parte pública, naturalmente--- y de autoridad de certificación de la Corte Suprema, para que puedan ser instalados y reconocidos en sistemas de validación estándar.

Es una lástima que HUGO (el motor de la página) haga tan difícil hacer links dentro de la página porque de hecho está destacada en ella una mención a una situación similar.

> Postdata: {{< link "no-valida" >}}

**4. Respaldos periódicos y exportación de expedientes**

- Permitir y fomentar la descarga periódica de expedientes completos[^a], en formato PDF firmado digitalmente, para que abogados y partes tengan copias de confianza almacenadas localmente. No sé por qué he escrito lo anterior. Eso no pasará. De hecho, la forma más fácil sería la de implementar un API REST como lo hace Tributación. Pero olvídalo, muchachito.

[^a]: Hojas del árbol caídas / juguetes del viento son / las ilusiones perdidas / son hojas, ay, desprendidas / del árbol del corazón.

## Resumen de la solución propuesta

| Medida | Beneficio principal |
| :-- | :-- |
| Firma digital optativa | Autenticidad y validez independiente de la plataforma |
| Sello de tiempo y código de verificación | Prueba de integridad y existencia en fecha cierta |
| Publicación de certificados y guías | Validación accesible y transparente para cualquier usuario |
| Descarga/exportación de expedientes | Copias de respaldo confiables fuera del sistema central |

## Coda.

La mejor manera en que la Corte Suprema de Paraguay puede asegurar la validación de las peticiones de abogados fuera del sistema Judisoft es expedir certificados de firma digital a los usuarios del sistema ---esto no implica costo alguno--- de todos los escritos, acompañada de mecanismos de verificación independientes (sellos de tiempo, códigos QR/códigos únicos), y facilitar la validación pública mediante la publicación de certificados y guías de uso. Así, aun si el sistema central desapareciera, los documentos conservarían su valor probatorio y podrían ser reconstruidos y validados por cualquier persona o autoridad competente[^2][^4][^7].

---

## Final.

Pero antes de que aplaudan mi sapiencia, hay una forma mucho mejor, más efectiva, y en consonancia con la consabida tendencia al _secretismo_ que tienen los estados: publicar los hashes.


1. **Protocolo de "huella digital inmutable"**:
    - Que cada documento judicial lleve un hash criptográfico único registrado en una blockchain pública (ej: LACChain). O en cualquiera otro, incluso la Corte podría tener la suya propia.
    - Esto permitiría probar la existencia e integridad del documento incluso décadas después, sin depender de Judisoft.
1. **Auditorías ciudadanas**:
    - Publicar hashes de lotes de expedientes en el portal web periódicamente (ej: cada 24 horas).
    - Cualquier ciudadano podría verificar que su copia local coincide con el registro oficial.

**¿Por qué funcionaría esto?** Porque convierte a cada abogado/juzgado/ciudadano en un **nodo de validación independiente**, creando una red antifrágil que no depende de un solo sistema centralizado.

Sólo los hashes habría que publicar, no pesarían nada, no revelarían nada del contenido del documento, y sin embargo estaría en una blockchain como la indicada. Claro que mi elección sería BTC. Pero LACChain me parece un medio paso seguro.

<div style="text-align: center">⁂</div>

[^1]: https://www.csj.gov.py

[^2]: https://www.pj.gov.py/notas/20659-la-direccion-general-de-registros-publicos-ya-cuenta-con-emision-de-certificado-de-firma-digital

[^3]: https://www.pj.gov.py/notas/24992-verificacion-de-documentos-generados-por-dependencias-del-poder-judicial

[^4]: https://old.pjn.gov.ar/publico/FE/INSTRUCTIVOINSTALACIONCERTIFICADOS.pdf

[^5]: https://www.pj.gov.py/notas/26838-sistema-judisoft-y-oficio-judicial-electronicos-vigentes-en-la-circunscripcion-de-alto-paraguay

[^6]: https://www.pj.gov.py/contenido/1436-tramite-judicial-electronico/1436

[^7]: https://www.acraiz.gov.py/adjunt/Instituciones/CSJ/Guia_de_uso_tramitacion_judicial_electronica_rol_abogado.pdf

[^8]: https://www.instagram.com/poderjudicialpy/reel/DAYY4D-MQIt/?locale=de

[^9]: https://www.pj.gov.py/images/contenido/acordadas/acordada1268.pdf

[^10]: https://www.pj.gov.py/notas/24965-recomendaciones-para-verificar-la-legitimidad-de-documentos-generados-por-dependencias-del-poder-judicial

[^11]: https://www.csj.gov.py/gestion/ayuda/ayuda_de_uso_del_sistema_mesa_entrada_en_linea.pdf

[^12]: https://www.mef.gov.py/sites/default/files/2025-01/13 01 Corte Suprema de Justicia_0.pdf

[^13]: https://www.pj.gov.py/images/contenido/acordadas/acordada1108.pdf

[^14]: https://www.pj.gov.py/notas/18718-disponen-la-verificacion-de-documentos-que-cuentan-con-codigo-qr

[^15]: https://www.pj.gov.py/images/contenido/dtic/tje-marco-normativo/acordada_1107.pdf

[^16]: https://www.pj.gov.py/notas/16281-firma-digital-para-resoluciones-de-juzgados-de-capital

[^17]: https://www.csj.gov.py/informesjudiciales/

[^18]: https://www.csj.gov.py/web/portal/preguntasfrecuentes

[^19]: https://www.pj.gov.py/contenido/1436-tramite-judicial-electronico/1438

[^20]: https://www.youtube.com/