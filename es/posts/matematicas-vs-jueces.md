---
title: "Matemáticas vs. Jueces"
description: "¿Quien gana? Tú decides."
tags: ["ejecución de sentencia", "cosa juzgada", "procesal"]
draft: false
date: 2025-03-09
---

## Al infinito y más allá.

Cualquiera de nosotros habrá oído que si se generan _honorarios sobre honorarios_ [^1] ello sería proponer una serie infinita. 

[^1]: Que esta premisa es falsa en sí misma es algo que veremos luego cuando este de humor para verificarla.

Anoche no pude dormir pensando en vos, mujer. Así que... ¿por qué no? Intuitivamente siempre supe que la serie sí era infinita (los jueces no mienten), pero que tendía a cero muy pronto, digamos en 10 pasos. Es bastante menos.

Digamos que en una causa o incidente o lo que fuera te regulan 20% ---sí sé, sueño.

$$a_1, a_2 = a_1 \times \dfrac{20}{100}, a_3 = a_2 \times \dfrac{20}{100}$$



Es infinita. Infinitamente decreciente.

## Sigamos soñando.

Si resultara que ganamos un juicio de USD 1, 000,000 y siguiendo el supuesto del 20%, la primera regulación sería de USD 200,000. Y la sexta de USD 320. Y para entonces habremos acumulado un 25% sobre el valor principal. Algunos de ustedes tiene juicios de USD 1,000,000. Yo no :cry:

En nuestros juicios normales que son del orden de los 100 millones de Gs. mi sexta regulación sería de Gs. 320.000, nadie podría hacer, ni siquiera la quinta de Gs. 1.600.000, quizás la cuarta, humilde Gs. 8.000.000 nos movería tal vez a ejecutarlo. Probable es que no.

Es decir la serie nos puede llevar hasta el sexto término si es que estamos en un juicio bueno, y hasta el tercer término, la tercera regulación si vamo en un juicio _normal_.

## Razón.

En la mañana pude generalizar la fórmula: $$a_n=a_1 \cdot \left( \dfrac{1}{5}\right)^{n-1}$$

Pero ¿si tenemos un juicio de USD 10,000,000? En realidad tenemos una fórmula que decrece exponencialmente en razón de $$r=\dfrac{1}{5}$$ , asumiendo claro que el Juez nos regula por lo alto. Asi que no importa mucho el multiplicado monto propuesto. Al momento estaríamos iguales.

{{< ipfs url="QmYEzpXVKVVgX2bWnSjye2HU9vBT7dWquuR14bZwJBDq3h" width="100%" height="100%" >}}



Ese gráfico proviene de:

```python
import matplotlib.pyplot as plt

# Valores iniciales
initial_values = [1_000_000, 10_000_000]
steps = 10
ratio = 1/5

# Generar los términos para cada serie
series = {}
for a1 in initial_values:
    terms = [a1 * (ratio ** n) for n in range(steps)]
    series[f"Inicio: USD {a1:,}"] = terms

# Graficar sin escala logarítmica
plt.figure(figsize=(10, 6))
for label, values in series.items():
    plt.plot(range(1, steps + 1), values, marker='o', label=label)

plt.title("Progresión geométrica con razón 1/5 (escala normal)")
plt.xlabel("Término (n)")
plt.ylabel("Valor de aₙ")
plt.grid(True, linestyle='--', linewidth=0.5)
plt.legend()
plt.tight_layout()
plt.show()
```

Lo pueden copiar y pegar en https://colab.research.google.com y lo verán en toda su magnificiencia.

Así que sí la serie es infinita, lo que no te dicen es que es que es infinitamente pequeña.

Que  $$\left( \dfrac{1}{5} \right)^{n-1}$$ decrece exponencialmente. Y como:

$$
\lim_{n \to \infty} \left( \frac{1}{5} \right)^{n} = 0
$$

quiere decir que **sin importar con qué valor comiences**, la serie **tiende rápidamente a cero**. Ya en el **tercer o cuarto término**, el número es muy pequeño.

Sorry.



















------
