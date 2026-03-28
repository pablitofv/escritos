# Tu sitio literario

Un sitio estático hecho con Hugo, alojado en GitHub Pages.

## Primer setup (una sola vez)

### 1. Creá una cuenta en GitHub

Si no tenés una: https://github.com/join

### 2. Instalá GitHub Desktop

Descargá e instalá desde: https://desktop.github.com/

Cuando lo abras por primera vez, iniciá sesión con tu cuenta de GitHub.

### 3. Instalá Hugo

1. Andá a https://github.com/gohugoio/hugo/releases/latest
2. Buscá el archivo que diga `hugo_extended_` y termine en `_windows-amd64.zip`
3. Descargá ese zip
4. Creá una carpeta en tu disco, por ejemplo `C:\hugo\`
5. Extraé el contenido del zip ahí. Vas a ver un archivo `hugo.exe`
6. Agregá esa carpeta al PATH de Windows:
   - Buscá "Variables de entorno" en el menú de inicio
   - Clic en "Variables de entorno..."
   - En "Variables del sistema", seleccioná `Path` y clic en "Editar"
   - Clic en "Nuevo" y escribí `C:\hugo\`
   - Aceptar todo

Para verificar que funcione, abrí una terminal (buscá "cmd" o "PowerShell" en el menú de inicio) y escribí:

```
hugo version
```

Si te muestra un número de versión, está instalado.

### 4. Descomprimí los archivos del sitio

Descomprimí el zip que descargaste de Claude. Vas a ver una carpeta `site/` con todo adentro. Podés moverla o renombrarla como quieras, por ejemplo `mi-sitio/` o `escritos/`.

### 5. Creá el repositorio con GitHub Desktop

1. Abrí GitHub Desktop
2. File > Add Local Repository
3. Seleccioná la carpeta del sitio
4. Te va a decir que no es un repositorio. Clic en "create a repository here"
5. Ponele un nombre (ej: `escritos`)
6. Clic en "Create Repository"
7. Arriba a la derecha, clic en "Publish repository"
8. Dejá el nombre, asegurate de que "Keep this code private" esté **destildado** (tiene que ser público para GitHub Pages)
9. Clic en "Publish Repository"

### 6. Activá GitHub Pages

1. Andá a github.com y entrá a tu repositorio
2. Andá a **Settings** (la pestaña de arriba a la derecha)
3. En el menú de la izquierda, clic en **Pages**
4. En "Source", seleccioná **GitHub Actions**
5. No hace falta hacer nada más. El workflow ya está incluido en los archivos.

Esperá unos minutos. Tu sitio va a estar en:
`https://TU_USUARIO.github.io/TU_REPO/`

### 7. (Opcional) Conectá tu dominio

Si compraste un dominio (ej. en Porkbun o Cloudflare):

1. En tu proveedor de dominio, agregá un registro CNAME que apunte a `TU_USUARIO.github.io`
2. En GitHub, andá a **Settings > Pages** y poné tu dominio en "Custom domain"
3. Activá "Enforce HTTPS"
4. En `hugo.toml`, cambiá el `baseURL` a tu dominio

---

## Día a día: publicar un texto nuevo

### Escribir el texto

1. Abrí la carpeta del sitio en tu computadora
2. Andá a `content/escritos/`
3. Creá un archivo nuevo. El nombre tiene que terminar en `.md` y usar guiones en vez de espacios. Ejemplo: `el-mitre-de-las-seis.md`
4. Abrilo con cualquier editor de texto (Notepad, VS Code, lo que uses) y escribí esto arriba:

```markdown
---
title: "El título de tu texto"
date: 2026-03-28
subtitle: ""
---

Tu texto va acá.

Segundo párrafo. Dejá una línea en blanco entre párrafos.
```

5. Guardá el archivo.

### Publicar

1. Abrí GitHub Desktop
2. Vas a ver los archivos que cambiaron en la columna izquierda
3. Abajo a la izquierda, escribí un mensaje breve (ej: "nuevo texto: el mitre")
4. Clic en "Commit to main"
5. Arriba, clic en "Push origin"

En unos minutos, el texto aparece en tu sitio.

### Ver el sitio en tu computadora antes de publicar

Abrí una terminal en la carpeta del sitio y escribí:

```
hugo server
```

Abrí `http://localhost:1313` en el navegador. Se actualiza en tiempo real mientras editás.

---

## Estructura del sitio

```
site/
├── hugo.toml              ← configuración del sitio
├── content/
│   ├── escritos/           ← tus textos van acá
│   │   ├── _index.md
│   │   └── desma-y-galgo.md
│   └── sobre.md            ← tu página "sobre mí"
├── layouts/                ← las plantillas HTML
├── static/css/style.css    ← el diseño visual
└── .github/workflows/      ← deploy automático
```

Lo que vas a tocar normalmente: la carpeta `content/` y nada más.

## Referencia rápida de markdown

```
*itálica*
**negrita**
---          (separador visual: · · ·)
> cita
```
