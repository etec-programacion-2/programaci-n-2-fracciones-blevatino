# Prompts utilizados durante el desarrollo del trabajo práctico

---

### Prompt 1

* **Fecha**: 2025-07-14
* **Herramienta**: ChatGPT
* **Prompt**: "¿Cómo implemento `operator fun equals(other: Any?): Boolean` para verificar igualdad entre fracciones?"
* **Respuesta**: Se recomendó comparar las fracciones con producto cruzado:

  ```kotlin
  override fun equals(other: Any?): Boolean {
      if (this === other) return true
      if (other !is Fraccion) return false
      return this.numerador * other.denominador == other.numerador * this.denominador
  }
  ```

---

### Prompt 2

* **Fecha**: 2025-07-14
* **Herramienta**: ChatGPT
* **Prompt**: "¿Cómo convierto un número decimal a fracción en Kotlin?"
* **Respuesta**: Se propuso una función en el `companion object`:

  ```kotlin
  companion object {
      fun desdeDecimal(decimal: Double, precision: Int = 1000): Fraccion {
          val numerador = (decimal * precision).toInt()
          val denominador = precision
          return Fraccion(numerador, denominador)
      }
  }
  ```

---

### Prompt 3

* **Fecha**: 2025-07-14
* **Herramienta**: ChatGPT
* **Prompt**: "¿Cómo implemento un CLI simple para probar una clase Fraccion en Kotlin?"
* **Respuesta**: Se generó un archivo `CalculadoraFracciones.kt` con menú, lectura de fracciones, validaciones y manejo de errores usando `Scanner` y `when`.
  Fragmento del `main()`:

  ```kotlin
  fun main() {
      val scanner = Scanner(System.`in`)
      var opcion: Int
      do {
          mostrarMenu()
          opcion = scanner.nextInt()
          when (opcion) {
              1 -> realizarSuma(scanner)
              2 -> realizarResta(scanner)
              ...
          }
      } while (opcion != 0)
      scanner.close()
  }
  ```

---

### Prompt 4

* **Fecha**: 2025-07-14
* **Herramienta**: ChatGPT
* **Prompt**: "¿Cómo redondeo un número a 3 decimales en Kotlin?"
* **Respuesta**: Se recomendaron tres métodos. Uno de ellos:

  ```kotlin
  val redondeado = String.format("%.3f", numero)
  ```

---

### Prompt 5

* **Fecha**: 2025-07-14
* **Herramienta**: ChatGPT
* **Prompt**: "¿Qué es un companion object en Kotlin?"
* **Respuesta**: Explicación conceptual de `companion object` para acceder a métodos sin instanciar una clase. Ejemplo usado:

  ```kotlin
  companion object {
      fun desdeDecimal(...) { ... }
  }
  ```

---
