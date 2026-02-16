# 🚀 Deployment Guide - GitHub Pages

## Despliegue Público del Demo de Animaciones

Esta guía te ayudará a publicar el demo de animaciones para que todo el equipo pueda verlo.

---

## ✅ Preparación Completa

Ya está todo listo para desplegar:
- ✅ `index.html` configurado (renombrado de `demo.html`)
- ✅ `animations.css` con todas las animaciones
- ✅ Accesibilidad WCAG 2.1 AA implementada
- ✅ Figma Material Design tokens alineados

---

## 🌐 Opción 1: GitHub Pages (Recomendado)

### Paso 1: Fusionar a la rama principal

```bash
# Crear pull request
gh pr create --title "Animation System with Figma Alignment & Accessibility" \
  --body "Complete animation system with Figma Material Design alignment and WCAG 2.1 AA accessibility"

# O fusionar directamente a main
git checkout main
git merge claude/figma-animation-alignment-on7qO
git push origin main
```

### Paso 2: Habilitar GitHub Pages

**Opción A: Desde la interfaz web de GitHub**

1. Ve a tu repositorio en GitHub: `https://github.com/rafagarces/studious-octo-happiness`
2. Haz clic en **Settings** (Configuración)
3. En el menú lateral, busca **Pages**
4. En **Source** (Fuente):
   - Branch: Selecciona `main` (o la rama que prefieras)
   - Folder: Selecciona `/ (root)`
5. Haz clic en **Save** (Guardar)
6. Espera 1-2 minutos para que se despliegue

**Opción B: Desde la rama actual**

Si prefieres desplegar directamente desde esta rama:

1. Ve a **Settings** → **Pages**
2. En **Source**:
   - Branch: Selecciona `claude/figma-animation-alignment-on7qO`
   - Folder: `/ (root)`
3. Haz clic en **Save**

### Paso 3: Accede a tu demo

Después de 1-2 minutos, el demo estará disponible en:

```
https://rafagarces.github.io/studious-octo-happiness/
```

O con el nombre del repositorio:

```
https://rafagarces.github.io/studious-octo-happiness/index.html
```

### Compartir con el Equipo

Una vez desplegado, simplemente comparte el link:

```
🎬 Demo de Animaciones
https://rafagarces.github.io/studious-octo-happiness/

✨ Características:
- Animaciones alineadas con Figma Material Design
- Durations: XS, S, M, L, XL, XXL
- Easing curves de Material Design
- Accesible WCAG 2.1 AA
- Completamente interactivo
```

---

## 🚀 Opción 2: Netlify (Alternativa más rápida)

Si quieres un despliegue instantáneo sin configurar GitHub:

### Paso 1: Arrastra y suelta

1. Ve a [netlify.com/drop](https://netlify.com/drop)
2. Arrastra la carpeta del proyecto
3. ¡Listo! Obtendrás un URL público instantáneamente

### Paso 2: URL personalizado (opcional)

1. En Netlify, ve a **Site settings** → **Change site name**
2. Cambia a algo como: `animation-system-demo`
3. Tu URL será: `https://animation-system-demo.netlify.app`

---

## 📦 Opción 3: Vercel

### Despliegue con un comando:

```bash
# Instalar Vercel CLI
npm i -g vercel

# Desplegar
vercel

# Seguir las instrucciones
```

URL de ejemplo: `https://studious-octo-happiness.vercel.app`

---

## 🔒 Opción 4: Despliegue Privado (Solo para el equipo)

Si no quieres hacerlo completamente público:

### Netlify con contraseña

1. Despliega en Netlify (Opción 2)
2. Ve a **Site settings** → **Access control**
3. Activa **Password protection**
4. Establece una contraseña
5. Comparte el URL + contraseña con el equipo

### GitHub Pages desde repositorio privado

Si el repositorio es privado, GitHub Pages también será privado (solo accesible para colaboradores del repo).

---

## 📝 Actualizaciones Futuras

Una vez desplegado en GitHub Pages:

### Actualizar el demo:

```bash
# Hacer cambios en index.html o animations.css
git add .
git commit -m "Update animations"
git push origin main

# GitHub Pages se actualiza automáticamente en 1-2 minutos
```

### Ver el estado del despliegue:

```bash
# Ver el último despliegue
gh api repos/rafagarces/studious-octo-happiness/pages/builds/latest

# O ver en la interfaz web
# Settings → Pages → "Your site is live at..."
```

---

## 🎯 URL del Demo

Una vez configurado GitHub Pages, el demo estará en:

### URL Principal:
```
https://rafagarces.github.io/studious-octo-happiness/
```

### URLs de Archivos Específicos:
```
# CSS de animaciones
https://rafagarces.github.io/studious-octo-happiness/animations.css

# Documentación
https://rafagarces.github.io/studious-octo-happiness/FIGMA-ALIGNMENT.md
https://rafagarces.github.io/studious-octo-happiness/ACCESSIBILITY.md
```

---

## ✉️ Template de Email para el Equipo

```
Asunto: 🎬 Demo de Sistema de Animaciones - Listo para Revisión

Hola equipo,

Ya está disponible el demo interactivo del sistema de animaciones:

🔗 URL: https://rafagarces.github.io/studious-octo-happiness/

🎨 Características principales:
✅ Alineado con convenciones de Figma Material Design
✅ Durations: XS (50ms), S (150ms), M (200ms), L (400ms), XL (600ms), XXL (1000ms)
✅ Easing curves Material Design (emphasized-decelerate, regular-accelerate, etc.)
✅ 100% accesible (WCAG 2.1 AA) - funciona con teclado y lectores de pantalla
✅ Ejemplos interactivos de todas las animaciones

📚 Documentación:
- FIGMA-ALIGNMENT.md - Guía de mapeo Figma → CSS
- ACCESSIBILITY.md - Detalles de accesibilidad
- EASING-REFERENCE.md - Referencia de easing curves

Por favor revisen y déjenme saber sus comentarios.

Saludos,
[Tu nombre]
```

---

## 🐛 Troubleshooting

### El sitio no carga después de 5 minutos

1. Verifica que GitHub Pages esté habilitado en Settings → Pages
2. Revisa que la rama correcta esté seleccionada
3. Verifica que `index.html` esté en la raíz del repositorio

### Error 404

1. Asegúrate de que el archivo se llame `index.html` (no `demo.html`)
2. Verifica que los archivos estén en la rama configurada
3. Limpia la caché del navegador (Ctrl+Shift+R)

### Los CSS no cargan

1. Verifica que `animations.css` esté en la misma carpeta que `index.html`
2. Revisa la consola del navegador para errores
3. Asegúrate de que la ruta en `<link>` sea relativa: `href="animations.css"`

### Cambios no se reflejan

1. GitHub Pages puede tomar 1-2 minutos en actualizar
2. Limpia la caché del navegador
3. Verifica que los cambios se hayan pusheado correctamente

---

## 🎉 ¡Listo!

Una vez completado cualquiera de estas opciones, tu equipo podrá:

✅ Ver todas las animaciones interactivamente
✅ Probar diferentes easing curves en tiempo real
✅ Navegar con teclado (accesibilidad completa)
✅ Copiar código CSS directamente
✅ Entender las convenciones Figma Material Design

---

## 📞 Soporte

Si tienes problemas con el despliegue:

1. Revisa la sección de Troubleshooting
2. Consulta [GitHub Pages Documentation](https://docs.github.com/pages)
3. Verifica el status de GitHub Pages: [githubstatus.com](https://www.githubstatus.com/)

---

**Última actualización**: Sistema desplegable listo con todas las características de accesibilidad y alineación Figma.
