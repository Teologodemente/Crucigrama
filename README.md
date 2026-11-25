# ✝️ Crucigrama Bíblico

Un juego de crucigrama bíblico en **un solo archivo HTML** (HTML + CSS + JavaScript puro, sin dependencias ni build). Genera un tablero **diferente en cada partida** a partir de un banco de más de 150 palabras bíblicas (personas, lugares, libros y conceptos), con pistas que **nunca contienen la palabra** a adivinar.

![badge](https://img.shields.io/badge/JavaScript-vanilla-f7df1e?logo=javascript)
![badge](https://img.shields.io/badge/Dependencias-ninguna-brightgreen)
![badge](https://img.shields.io/badge/Plataforma-Web%20y%20móvil-orange)

## 🎮 Cómo jugar

1. Pulsa **🎲 Nueva partida** para generar un tablero aleatorio (8 a 12 palabras).
2. Toca una casilla y escribe la letra.
3. Usa **↔️ Cambiar ↔/↕** (o la tecla **Espacio**) para alternar entre horizontal y vertical.
4. Pulsa **✔️ Comprobar** para validar lo escrito (las casillas incorrectas se marcan en rojo y sacuden).
5. ¿Atascado? Usa **💡 Pista** para revelar una letra de la palabra activa, o **👁️ Revelar** para completar esa palabra.
6. **🧹 Borrador**: actívalo y toca las casillas para borrarlas; en el teclado, **Backspace** borra la casilla actual y **Shift+Backspace** borra toda la línea activa.
7. Haz **clic en cualquier pista** para saltar directamente a su palabra.
8. ¡Completa todas las palabras para ganar! 🏆 Aparecen confeti y tus estadísticas.

## ✨ Características

- **Tablero único cada partida**: generador con reintentos que busca la máxima cantidad de palabras bien entrelazadas.
- **Banco de 150+ palabras bíblicas** organizadas en:
  - 👤 Personas (Moisés, David, Ester, Pablo…)
  - 📍 Lugares (Belén, Galilea, Jericó, Gólgota…)
  - 📖 Libros (Génesis, Salmos, Apocalipsis…)
  - 🕊️ Cosas, eventos y valores (Fe, Cruz, Pentecostés, Perdón…)
- Cada pista incluye su **referencia bíblica** (ej. `Ex 14`, `Jn 19:17`).
- **Modo de tiempo** con cronómetro, contador de palabras completadas y de pistas usadas.
- **Diseño responsive** optimizado para móvil: evita el zoom automático de iOS al escribir (fuentes ≥ 16px), scroll suave de casillas y botones táctiles grandes.
- Animaciones: sacudida en errores, resaltado de palabra activa, modal de victoria y lluvia de confeti en canvas.
- **100 % offline**: no requiere servidor, conexión a internet ni instalación.

## 🚀 Cómo usarlo

### Opción 1 — Abrir el archivo

Simplemente abre [`index.html`](index.html) en cualquier navegador moderno.

```bash
# o sirve la carpeta localmente (opcional)
python3 -m http.server 8000
# → http://localhost:8000
```

### Opción 2 — GitHub Pages (recomendado)

Este repositorio incluye un [workflow de GitHub Actions](.github/workflows/deploy.yml) que publica el juego automáticamente en cada push a `main`.

1. Crea un repositorio nuevo en GitHub y sube este código:
   ```bash
   git init
   git add .
   git commit -m "Crucigrama Bíblico"
   git branch -M main
   git remote add origin https://github.com/TU_USUARIO/crucigrama-biblico.git
   git push -u origin main
   ```
2. En tu repositorio ve a **Settings → Pages** y verifica que la fuente sea **"Deploy from a branch"** → *GitHub Actions* (el workflow se encarga del despliegue; si no aparece, selecciona la rama `main` / carpeta raíz).
3. Espera ~1 minuto y tu juego estará disponible en:
   ```
   https://TU_USUARIO.github.io/crucigrama-biblico/
   ```
   Ese enlace es el que puedes pegar en la **pantalla principal de tus dispositivos**: funciona directamente al tocarlo, sin instalar nada.

## ⌨️ Atajos de teclado

| Tecla | Acción |
|---|---|
| Escribe una letra | Se coloca en la casilla seleccionada y avanza |
| `Espacio` | Alterna dirección ↔ / ↕ |
| `Backspace` | Borra la casilla (o retrocede y borra) |
| `Shift` + `Backspace` | Borra toda la palabra activa |
| `Enter` | Salta a la siguiente casilla de la palabra |

## 📁 Estructura

```
crucigrama-biblico/
├── index.html          # El juego completo (HTML + CSS + JS)
├── README.md           # Esta descripción
├── LICENSE             # Licencia MIT
└── .github/workflows/
    └── deploy.yml      # Despliegue automático a GitHub Pages
```

## 🔧 Personalización rápida

Todo está en [`index.html`](index.html):

- **Palabras**: edita el objeto `WORDS` (formato `PALABRA: { c: 'pista', r: 'referencia' }`). Las respuestas deben usar solo `A–Z` (sin tildes ni Ñ).
- **Tamaño del tablero**: cambia el rango en `generate()` (`8 + Math.floor(Math.random()*5)` = 8 a 12 palabras).
- **Colores**: modifica las variables CSS en `:root` (`--gold`, `--bg1`, `--bg2`…).

## 📄 Licencia

[MIT](LICENSE) — úsalo, modifícalo y compártelo libremente.
