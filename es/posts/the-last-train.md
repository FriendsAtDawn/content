---
title: "Accesible al público."
description: "pki, efirma"
tags: ["validación", "blockchain"]
draft: false
date: 2025-09-25
slug: "servicios-de-confianza"
---

## Lo que dice la ley.

Dice la ley correspondiente:

```yaml
2. Los prestadores de servicios de confianza que expidan certificados electrónicos, deben cumplir también las siguientes obligaciones:

a) No almacenar ni copiar, ...

(...)

b) Disponer de un servicio de consulta sobre el estado de validez y revocación de los certificados emitidos accesible al público.
```

Uno puede consultar las bases de datos de los prestadores de servicio de confianza y hallar que no publican sino las llaves actuales, no las que ya han dado de baja por alguna de las razones por las que el standard pki admite.

Pero entonces como sabré si el certificado con el cuál fue firmado cierta resolución de hace dos añs es válido si no hay información acerca los certificados revocados? —Sobreentiendo que aun puedo corroborar que el vencido valida.

Uno puede entrar en la página que da el servicio a la CSJ y… buscar por el CI… ¿Por qué no por CN (Common Name), nombre? Misterio. Y solo estan listados los certificados vigentes. No los que expirarn no los que fueron revocados.

> [!NOTE]
> Si un certificado ha expirado y no aparece en el CRL, ¿la firma es válida?
No necesariamente. El hecho de que no esté en el CRL no lo hace válido si ya expiró.
Validación de una firma digital requiere dos cosas clave: 1. El certificado debe estar dentro de su período de validez: Es decir, la fecha actual (o la fecha de la firma, si se usa timestamping) debe estar entre: NotBefore (inicio de validez) NotAfter (fecha de expiración). 2. El certificado no debe estar revocado: Verificado mediante CRL o OCSP. Dicho sea esto, se considera aca que las firmas cuentan con timestamp.

## Se ve la mentira.

Ah, estoy faltando a la verdad, sí se publica el crl. Cualquiera puede bajarlo desde acá: https://efirma.com.py/repositorio/efirma2.crl. 

Pero si lo bajan no les aseguro que puedan leer nada porque es un archivo binario, es decir, no es texto.

Seguramente se me objetará que el interesado puede usar el PowerShell de su máquina  y escribir algo asi:

```bash
$ openssl crl -inform DER -text -noout -in efirma2.crl -out efirma2.txt
```

Y tener como resultado el el [texto plano](./efirma2.crl)

Más o menos se ve así:

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

Pero sinceramente no creo que sea a eso lo que la ley se sefiere. 

Sino que las personas puedan saber si un certificado expirado ha sido emitido por el proveedor y si el mismo fue revocado.