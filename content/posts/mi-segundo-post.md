---
title: "Reto de hoy: Descifrar XOR"
date: 2026-02-05T22:25:22+01:00
draft: false
categories: ["Criptografía", "Lógica"]
tags: ["XOR", "Algoritmos", "Optimización"]
ShowToc: true
TocOpen: true
---

### 🧠 El desafío de los bits

Hoy exploramos cómo manipular datos a nivel bajo. Un concepto fundamental en criptografía y optimización es el intercambio de valores entre variables.

#### Métodos de intercambio
Para intercambiar dos valores en memoria, podemos usar diferentes aproximaciones según nuestras necesidades de rendimiento o claridad:

* **Suma y resta:** Un método ingenioso pero peligroso en lenguajes de bajo nivel por posibles desbordamientos (*overflow*).
* **XOR (Exclusive OR):** El truco clásico del hacking. Permite intercambiar valores sin usar una tercera variable de apoyo mediante manipulación de bits.
* **Variable temporal:** El estándar de la industria. Es el más seguro y fácil de leer para cualquier desarrollador.



#### Comparativa Técnica

| Método | Velocidad | Legibilidad | Uso de Memoria |
| :--- | :--- | :--- | :--- |
| **XOR** | ⚡ Alta | 🔴 Baja | Mínimo (0 extra) |
| **Temporal** | 🟢 Media | 🟢 Alta | 1 variable extra |
| **Aritmética**| 🟢 Media | 🟡 Media | 0 extra |

---

### Ejemplo práctico: XOR Swap en Python

Aunque en Python el intercambio se hace de forma nativa con `a, b = b, a`, entender la lógica tras el XOR es vital para la criptografía:

```python
a = 5  # Representación binaria: 0101
b = 10 # Representación binaria: 1010

# Algoritmo de intercambio XOR
a = a ^ b
b = a ^ b
a = a ^ b

print(f"Resultado -> a: {a}, b: {b}") # Ahora a=10 y b=5