---
theme: seriph
background: https://enula.org/wp-content/uploads/2020/07/foto-inin.jpg
title: Welcome to Slidev
class: text-center
drawings:
  persist: false
transition: slide-left
mdc: true
overviewSnapshots: true
---

# Slidev para Presentaciones

introducción sencilla

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/guillermoibarra/mfc-seminars" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

---
transition: fade-out
---

# ¿Qué es Slidev?

Slidev es un creador y presentador de diapositivas diseñado para desarrolladores, y consta de las siguientes características.

- 📝 **Basado en texto** - enfócate en el contenido con Markdown y estilízalo después.
- 🎨 **Personalizable** - los temas se pueden compartir y reutilizar como paquetes npm.
- 🧑‍💻 **Amigable para desarrolladores** - resaltado de código, codificación en vivo con autocompletado.
- 🤹 **Interactivo** - inserta componentes de Vue para mejorar tus expresiones.
- 🎥 **Grabación** - incluye grabación integrada y vista de cámara.
- 📤 **Portable** - exporta a PDF, PPTX, PNG o incluso a una SPA alojable.
- 🛠 **Modificable** - prácticamente todo lo que es posible en una página web es posible en Slidev.
<br>
<br>

Ver más información: [Slidev](https://sli.dev/guide/why)

---

# Uso de Markdown
## caso sencillo

Esta Lámina se define de la siguente manera:
```markdown
---

# título
## Subtitulo
```

---

# Código

```ts {all|1|3-4|6|all}
import { computed, ref } from 'vue'

const count = ref(0)
const doubled = computed(() => count.value * 2)

doubled.value = 2
```

<!-- Inline style -->
<style>
.footnotes-sep {
  @apply mt-5 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
</style>

---
level: 2
---
# Shiki Magic Move

Impulsado por [shiki-magic-move](https://shiki-magic-move.netlify.app/), Slidev soporta animaciones entre múltiples fragmentos de código.

Agrega varios bloques de código y envuélvelos con <code>````md magic-move</code> (cuatro comillas invertidas) para habilitar el magic move. Por ejemplo:

````md magic-move {lines: true}
```python {*|2|3-4|5-7|*}
# primer intento
def fibonacci(n):
    sequence = []
    a, b = 0, 1
    while len(sequence) < n:
        sequence.append(a)
        a, b = b, a + b
    return sequence
```

```python {*|2|4|*}
# paso 2
from typing import List

def fibonacci(n: int) -> List[int]:
    sequence: List[int] = []
    a, b = 0, 1
    while len(sequence) < n:
        sequence.append(a)
        a, b = b, a + b
    return sequence
```

```python {*|3-15|*}
# paso 3
def fibonacci(n: int) -> List[int]:
    """
    Generate a Fibonacci sequence of 'n' terms.

    Args:
        n (int): The number of terms to generate in the Fibonacci sequence.

    Returns:
        List[int]: A list containing the first 'n' terms of the Fibonacci sequence.

    Example:
        >>> fibonacci(5)
        [0, 1, 1, 2, 3]
    """
    sequence: List[int] = []
    a, b = 0, 1
    while len(sequence) < n:
        sequence.append(a)
        a, b = b, a + b
    return sequence
```
````

---

# Obtener Slidev


Instalar localmente con:
```bash
npm init slidev@latest
```

Correr el servidor con:
```bash
slidev
```

Se edita el archivo `slides.md`
