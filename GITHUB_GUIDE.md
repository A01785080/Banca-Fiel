# Guía: Cómo Subir BancaFiel a GitHub

## Requisitos Previos
- Tener una cuenta en [GitHub](https://github.com)
- Tener Git instalado en tu computadora ([Descargar Git](https://git-scm.com/))

---

## Opción 1: Crear un Repositorio Nuevo (Recomendado)

### Paso 1: Crear el Repositorio en GitHub
1. Ve a [github.com](https://github.com) y inicia sesión
2. Haz clic en el **+** en la esquina superior derecha
3. Selecciona **New repository**
4. Configura:
   - **Repository name**: `bancafiel-platform` (o tu nombre preferido)
   - **Description**: `Plataforma digital de solicitud de créditos para BancaFiel`
   - **Public**: Selecciona si quieres que sea público o privado
   - **Initialize with README**: NO (ya lo tenemos)
   - **Add .gitignore**: NO (ya lo tenemos)
5. Haz clic en **Create repository**

### Paso 2: Configurar Git en tu Computadora

Abre la Terminal (Mac/Linux) o Command Prompt (Windows) y ejecuta:

```bash
# Configura tu nombre de usuario (solo la primera vez)
git config --global user.name "Tu Nombre"

# Configura tu email (solo la primera vez)
git config --global user.email "tuemail@example.com"
```

### Paso 3: Subir los Archivos

En la Terminal, navega a la carpeta donde están los archivos:

```bash
# Navega a la carpeta de tu proyecto
cd /ruta/a/tu/carpeta/bancafiel-platform

# Inicializa el repositorio local
git init

# Añade todos los archivos
git add .

# Crea el primer commit
git commit -m "Commit inicial: Plataforma digital BancaFiel"

# Añade el repositorio remoto (reemplaza USERNAME y REPO)
git remote add origin https://github.com/USERNAME/bancafiel-platform.git

# Cambia la rama a main (GitHub usa main por defecto ahora)
git branch -M main

# Sube los archivos
git push -u origin main
```

**Nota**: Si GitHub te pide autenticación, usarás un Personal Access Token (en lugar de contraseña).

### Paso 4: Generar Personal Access Token (si es necesario)

1. Ve a GitHub → Settings (perfil) → Developer settings → Personal access tokens
2. Haz clic en **Generate new token**
3. Selecciona los scopes: `repo`, `workflow`
4. Genera el token y cópialo
5. Cuando Git pida contraseña, pega el token

---

## Opción 2: Usar GitHub Desktop (Más Fácil)

Si prefieres una interfaz gráfica:

1. Descarga [GitHub Desktop](https://desktop.github.com/)
2. Inicia sesión con tu cuenta de GitHub
3. Ve a File → Add Local Repository
4. Selecciona la carpeta con los archivos de BancaFiel
5. Haz clic en "Publish repository"
6. Configura el nombre y descripción
7. ¡Listo!

---

## Opción 3: Usar Visual Studio Code

Visual Studio Code tiene integración directa con Git:

1. Abre la carpeta del proyecto en VS Code
2. Ve a la Vista de Control de Código Fuente (Ctrl+Shift+G)
3. Haz clic en "Inicializar repositorio"
4. Escribe el mensaje del commit en el campo de texto
5. Haz clic en el checkmark para hacer commit
6. En el menú, selecciona "Publicar rama"
7. Selecciona tu cuenta de GitHub
8. ¡Listo!

---

## Activar GitHub Pages

### Para que tu sitio sea accesible en línea:

1. Ve a tu repositorio en GitHub
2. Haz clic en **Settings**
3. Baja hasta **Pages** (en el menú izquierdo)
4. En **Source**, selecciona:
   - Branch: `main`
   - Folder: `/ (root)`
5. Haz clic en **Save**

GitHub creará automáticamente tu sitio en:
```
https://username.github.io/bancafiel-platform
```

Espera 2-3 minutos a que GitHub construya el sitio. Verás un mensaje azul confirmando que está listo.

---

## Actualizar los Cambios Después

Cada vez que hagas cambios:

### Con Terminal:
```bash
git add .
git commit -m "Descripción de los cambios"
git push
```

### Con GitHub Desktop:
1. Los cambios aparecen automáticamente
2. Escribe el resumen en "Summary"
3. Haz clic en **Commit to main**
4. Haz clic en **Push origin**

### Con VS Code:
1. Ctrl+Shift+G (Control de Código Fuente)
2. Escribe el mensaje
3. Ctrl+Enter para hacer commit
4. Haz clic en "Sincronizar cambios"

---

## Estructura del Repositorio

Después de subir, tu repositorio lucirá así:

```
bancafiel-platform/
├── index.html                 # Aplicación web
├── README.md                  # Documentación
├── LICENSE                    # Licencia MIT
├── .gitignore                # Archivos ignorados
└── .github/
    └── workflows/
        └── deploy.yml         # Automatización
```

---

## Troubleshooting

### Error: "fatal: not a git repository"
Solución: Asegúrate de estar en la carpeta correcta
```bash
cd /ruta/correcta
git status
```

### Error: "Permission denied (publickey)"
Solución: Configura SSH key o usa HTTPS con Personal Access Token

### El sitio no actualiza después de push
Solución: GitHub Pages tarda 2-3 minutos. Recarga la página o limpia la caché.

### Los archivos no aparecen en el repositorio
Solución: Asegúrate de haber ejecutado:
```bash
git add .
git commit -m "mensaje"
git push
```

---

## Comando Rápido (Todo en Uno)

Si ya hiciste `git init`:

```bash
git add . && git commit -m "Actualización" && git push
```

---

## Verificar que Todo Está Correcto

```bash
# Ver el estado actual
git status

# Ver el historial de commits
git log

# Ver los repositorios remotos configurados
git remote -v
```

---

## Próximos Pasos

Una vez en GitHub:

1. **Compartir el enlace**: `https://github.com/username/bancafiel-platform`
2. **Dirigir al sitio en vivo**: `https://username.github.io/bancafiel-platform`
3. **Colaborar**: Invita a otros usuarios como colaboradores
4. **Integrar backend**: Conecta un servidor real (Node.js, Python, etc.)

---

¡Tu plataforma BancaFiel está lista para ser compartida! 🚀
