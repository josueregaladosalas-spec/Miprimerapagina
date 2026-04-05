# Top-5-Estrategias-en-Educaci-n-Inclusiva-para-Computaci-n
Infografia
# 📄 Explicación de la Implementación

## 🧱 Estructura Semántica
Se utiliza HTML semántico para mejorar la accesibilidad y organización del contenido:

- `<section>` como contenedor principal  
- `<header>` para el encabezado  
- `<ol>` para la lista ordenada (ranking)  
- `<li>` para cada elemento  
- `<h3>` para los títulos  
- `<p>` para las descripciones  

Todo el contenido decorativo usa `aria-hidden="true"` para que los lectores de pantalla se enfoquen únicamente en el contenido relevante.

---

## 🎨 Efecto Semicírculo Animado
- Se utiliza `.icon-circle` con `overflow: hidden` y un gradiente de fondo.
- `::after` funciona como máscara que cubre la mitad inferior.
- Al hacer hover:
  - Se aplica `transform: rotateX(-90deg)`
  - Se usa `transform-origin: center top`
  - Se revela el fondo completo simulando una apertura 3D.
- `::before` añade un anillo decorativo que cambia de color al pasar el cursor.

---

## 🌊 Línea Ondulada SVG
- Se utiliza un SVG codificado en URL (`data:image/svg+xml`) como `background-image`.
- Estado inicial:
  - `opacity: 0`
  - `scaleX(0)`
- En hover:
  - `scaleX(1)`
  - Se activa animación `@keyframes waveSlide`
  - Se mueve con `background-position-x` para crear efecto continuo.

---

## ✨ Animaciones de Entrada
- Cada `<li>` tiene animación escalonada:
  - `animation-delay: 0.12s, 0.24s, ...`
- Se usa `animation-fill-mode: backwards` para evitar conflictos con efectos hover.
- Animación principal: `@keyframes fadeInUp`

---

## 📱 Diseño Responsive
Para pantallas menores a **620px**:

- `flex-direction` cambia de `row` a `column`
- El ícono se posiciona arriba del texto
- La línea de acento lateral pasa a ser superior
- Se eliminan desplazamientos horizontales para evitar desalineación

---

## ♿ Accesibilidad
- Alto contraste:
  - Texto: `#1A2332`
  - Fondo: `#FFFFFF`
- Tamaño mínimo de fuente: **16px**
- Uso de `aria-label` en secciones e íconos
- Soporte para usuarios con reducción de movimiento:

```css
@media (prefers-reduced-motion: reduce) {
  /* Desactiva animaciones */
}
