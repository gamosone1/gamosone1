# Registro de Cambios: Perfil Responsivo y Modo Oscuro

A continuación te detallo todos los cambios que se aplicaron en tus archivos para solucionar el problema del fondo blanco y del scroll horizontal en celulares. 

*(Nota: Estos cambios **ya han sido aplicados y guardados en tus archivos originales**. Este documento es para que tengas el registro de qué cambió).*

---

### 1. Cambio en `README.md` (Hacerlo responsivo)
Se cambiaron los anchos fijos de la tabla por porcentajes (`width="100%"`, `60%`, `40%`) para que se adapten a la pantalla de cualquier celular sin generar scroll hacia la derecha.

**Código nuevo de la estructura de la tabla:**
```html
<table align="center" border="0" cellpadding="0" cellspacing="0" width="100%">
  <tr>
    <!-- COLUMNA IZQUIERDA -->
    <td width="60%" valign="top">
...
    <!-- COLUMNA DERECHA -->
    <td width="40%" valign="top">
...
```
*(Además, todas las etiquetas `<img ...>` dentro de las columnas pasaron a tener `width="100%"`, y **se eliminó una tabla interna** que estaba alrededor del saludo para evitar que GitHub dibujara un recuadro molesto en la versión de PC).*

---

### 2. Cambios en los archivos `.svg` (Fondo oscuro forzado)
Como GitHub en móviles elimina el fondo de las tablas si el celular está en modo claro, tus textos blancos desaparecían. 

Para solucionarlo, insertamos un fondo sólido oscuro (`#0D1117`) al principio de todos tus archivos SVG. 

**Archivos modificados:**
- `banner.svg`
- `bottom_stats.svg`
- `camino.svg`
- `proyectos.svg`
- `quote.svg`
- `right_panel.svg`
- `stack.svg`
- `tecnologias.svg`

**Ejemplo de cómo quedó el código dentro de cada `.svg`:**
```xml
<svg viewBox="0 0 350 200" width="100%" height="100%" xmlns="http://www.w3.org/2000/svg">
  <!-- ESTA ES LA LÍNEA NUEVA AÑADIDA: -->
  <rect width="100%" height="100%" fill="#0D1117" />
  
  <defs>
    <style>...
```

Al añadir esa etiqueta `<rect>`, forzamos a que la imagen siempre tenga fondo oscuro y las letras blancas resalten, sin importar el color de la página web de GitHub.
