---
title: "Accesible al público."
description: "Lo que es Accesible"
tags: ["validación", "blockchain", "pki", "firma digital", "tecnologia"]
draft: false
date: 2025-09-25
slug: "servicios-de-confianza"
---

En este texto es un acercamiento al papel de los CRL (Certificate Revocation Lists) y por qué su publicación, aunque obligatoria, no siempre equivale a un servicio accesible y práctico para cualquier usuario.

## Lo que dice la ley.

Dice la ley correspondiente:

> 2. Los prestadores de servicios de confianza que expidan certificados electrónicos, deben cumplir también las siguientes obligaciones:
> a) No almacenar ni copiar, ...
> (...)
> b) Disponer de un servicio de consulta sobre el estado de validez y revocación de los certificados emitidos accesible al público.

En las bases de datos de los prestadores de servicios de confianza (PSC), normalmente solo se publican las llaves criptográficas que están activas en ese momento. Las llaves que han sido revocadas o dadas de baja —por razones contempladas en los estándares PKI, como expiración, compromiso de seguridad o reemplazo— no suelen aparecer.

Esto tiene implicancias prácticas: por ejemplo, si recibes un documento firmado digitalmente hace tres años y quieres verificar su firma hoy, la llave que se utilizó podría ya no estar publicada si fue revocada. Como consecuencia, tu software de verificación podría no encontrar la llave y dar un resultado negativo, aunque en el momento de la firma la operación fuera totalmente válida. Por eso, la ausencia de llaves históricas limita la capacidad de realizar auditorías completas o de comprobar la validez de firmas antiguas usando solo la base de datos actual del PSC.

Pero entonces, ¿cómo puedo saber si un certificado utilizado para firmar una resolución de hace dos años era realmente válido, si no existe información sobre los certificados que fueron revocados? La cuestión es que, aunque todavía podría comprobar si el certificado estaba vigente en la fecha de emisión —por ejemplo, verificando su período de validez—, no hay manera de confirmar si había sido revocado por otras razones, como un compromiso de seguridad.

Por ejemplo, imagina que un funcionario firmó digitalmente una resolución en 2023 usando un certificado que parecía válido. Hoy, al intentar verificar la firma, la base de datos del prestador de servicios de confianza solo muestra certificados activos. Si aquel certificado fue revocado en 2024 por haber sido comprometido, no habría forma de detectarlo usando solo la base actual. Esto ilustra por qué la ausencia de información histórica sobre revocaciones limita la trazabilidad y la certeza sobre la validez de firmas antiguas.

Uno puede entrar en la página que da el servicio a la CSJ y… buscar por el CI… ¿Por qué no por CN (Common Name), nombre? Misterio. Y solo estan listados los certificados vigentes. No los que expirarn no los que fueron revocados.

> [!NOTE]
> Si un certificado ha expirado y no aparece en el CRL, ¿la firma es válida?
No necesariamente. El hecho de que no esté en el CRL no lo hace válido si ya expiró.
Validación de una firma digital requiere dos cosas clave: 1. El certificado debe estar dentro de su período de validez: Es decir, la fecha actual (o la fecha de la firma, si se usa timestamping) debe estar entre: NotBefore (inicio de validez) NotAfter (fecha de expiración). 2. El certificado no debe estar revocado: Verificado mediante CRL o OCSP. Dicho sea esto, se considera aca que las firmas cuentan con timestamp --v. {{< link your-e-signature-is-broken >}}.

## Se ve la mentira.

Ah, estoy siendo un poco injusto: sí se publica el CRL. Cualquiera puede descargarlo desde aquí: [https://efirma.com.py/repositorio/efirma2.crl](https://efirma.com.py/repositorio/efirma2.crl).

El detalle es que, si lo bajan, no van a poder leerlo directamente, porque es un archivo binario, no un archivo de texto. Para interpretarlo, se necesita usar alguna herramienta técnica, como OpenSSL o PowerShell, por ejemplo:

```bash
$ openssl crl -inform DER -text -noout -in efirma2.crl -out efirma2.txt
```

Esto funciona, pero plantea un problema práctico: la ley exige “disponer de un servicio de consulta sobre el estado de validez y revocación de los certificados emitidos accesible al público”. La intención no es solo publicar un archivo técnico que pocos pueden leer, sino ofrecer un servicio donde cualquier persona pueda consultar fácilmente si un certificado está vigente o ha sido revocado, sin necesidad de manipular archivos binarios o comandos especializados.

Por ejemplo, en un escenario ideal, uno podría ingresar el número de un certificado en un portal web y obtener al instante su estado: “válido”, “revocado” o “expirado”. Esto sería un servicio de consulta realmente accesible y conforme a la ley, mucho más práctico que descargar un CRL y convertirlo manualmente.

Para que se entienda mejor, si convertimos el CRL a texto plano, más o menos se ve así:

```
Certificate Revocation List (CRL):
        Version 2 (0x1)
        Signature Algorithm: sha256WithRSAEncryption
        Issuer: serialNumber=RUC80080099-0, CN=VIT S.A., OU=Prestador Cualificado de Servicios de Confianza, O=ICPP, C=PY
        Last Update: Sep 27 18:53:02 2025 GMT
        Next Update: Sep 28 06:53:02 2025 GMT
        CRL extensions:
            X509v3 CRL Number: 
                4100
            X509v3 Authority Key Identifier: 
                BB:65:11:2B:67:ED:86:38:20:1C:28:67:19:14:04:65:EA:91:A1:B3
            X509v3 Issuing Distribution Point: critical
                Full Name:
                  URI:https://www.efirma.com.py/repositorio/efirma2.crl

Revoked Certificates:
    Serial Number: 3CD7DB14CF35364E64726D4AA5C64282
        Revocation Date: Jun 19 19:25:45 2023 GMT
        CRL entry extensions:
            X509v3 CRL Reason Code: 
                Unspecified
```

Esto nos dice varias cosas:

1. Quién emitió el CRL: En este caso, la autoridad certificadora (VIT S.A.), identificada con su RUC y detalles de la organización.
2. Actualización: La lista se actualizó por última vez el 27 de septiembre de 2025 y se espera la siguiente actualización el 28 de septiembre. Esto indica cada cuánto se publica la información.
3. Número de CRL y clave de la autoridad: Sirven para identificar esta lista concreta y para verificar que no ha sido modificada.
4. Certificados revocados: Aquí aparece el número de serie de cada certificado que fue revocado, la fecha de revocación y, en algunos casos, la razón. En el ejemplo, la razón se dejó como “Unspecified” (no especificada).

En pocas palabras, un CRL nos da un listado oficial de certificados que ya no son confiables, pero todavía necesita interpretarse con herramientas técnicas o un servicio de consulta accesible para que cualquier persona pueda usarlo fácilmente.

