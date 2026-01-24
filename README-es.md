# PyMenuPup

Un menú de inicio moderno y personalizable para JWM (Joe's Window Manager) y Puppy Linux, escrito en Python con GTK3.

![Versión de Python](https://img.shields.io/badge/python-3.6%2B-blue)
![Licencia](https://img.shields.io/badge/license-GPL-green)
![Plataforma](https://img.shields.io/badge/platform-Linux-lightgrey)

**[English](README.md) | Español**

---

## Descripción

PyMenuPup es un menú de inicio moderno y altamente personalizable diseñado específicamente para distribuciones ligeras como Puppy Linux que usan JWM como gestor de ventanas. También es compatible con Openbox y Tint2.

### Características Principales

- Totalmente personalizable: colores, fuentes, tamaños y posicionamiento
- Multilingüe: soporte para inglés y español
- Búsqueda rápida: encuentra aplicaciones al instante
- Acceso rápido: carpetas del sistema con un clic
- Integración web: búsqueda directa en el navegador
- Foto de perfil: personalizable (cuadrada o circular)
- Detección automática: soporte para JWM, Openbox y Tint2
- Rendimiento optimizado: carga perezosa de aplicaciones
- Categorías personalizables: oculta las que no necesites
- Navegación con teclado: soporte para teclas de flecha y Enter
- Integración con tema del sistema: usa los colores del tema GTK

---

## Componentes

### 1. pymenu-globicons.py
Menú principal que muestra todas las aplicaciones del sistema organizadas por categorías.

**Funcionalidades:**
- Lectura automática del archivo `.jwmrc` de JWM
- Categorización inteligente de aplicaciones
- Búsqueda en tiempo real
- Acceso rápido a carpetas comunes
- Integración con redes sociales
- Creación de accesos directos en el escritorio *(no compatible con ROX-Filer; funciona solo con SpaceFM y gestores derivados)*
- Soporte de teclado (navegación con teclas de flecha)
- Menú contextual (clic derecho en aplicaciones)

### 2. pymenu-config.py
Herramienta gráfica de configuración para personalizar el menú.

**Opciones configurables:**
- Dimensiones y posición de la ventana
- Colores y transparencia
- Fuentes y tamaños de texto
- Rutas de archivos y comandos
- Categorías visibles/ocultas
- Integración con tema GTK del sistema

---

# 🌍 Sistema de Traducción

PyMenuPup utiliza un **sistema de traducción simple y fácil de usar** basado en archivos `.lang`.  
No se necesitan herramientas complejas como `poedit` o `gettext`.

El proyecto ya incluye un **`template.lang` listo para usar**, solo necesitas copiarlo y traducirlo.

---

## Cómo Funciona

Las traducciones utilizan un formato de texto simple `clave = valor`.  
Solo traduces el texto **después del signo `=`**.

```text
# Ejemplo
Search applications... = Buscar aplicaciones...
Shutdown = Apagar
Desktop = Escritorio
```

Si una línea se deja vacía, PyMenuPup usará automáticamente el inglés.

---

## Ubicación de los Archivos de Traducción

Los archivos de traducción se buscan en este orden (mayor prioridad primero):

1. `~/.config/pymenupup/locale/` — **Traducciones de usuario** (recomendado)
2. `/usr/local/share/locale/pymenupup/`
3. `/usr/share/locale/pymenupup/` — A nivel de sistema

> **Consejo:** Usar la carpeta de usuario evita modificar archivos del sistema.

---

## Idiomas Soportados

- **Inglés (en)** — Incluido por defecto (no requiere archivo)
- **Español (es)** — `es.lang` incluido
- **Francés (fr)** — `fr.lang` incluido

Se pueden agregar más idiomas fácilmente.

---

## Crear una Nueva Traducción (Recomendado)

### 1. Copia el archivo template y renómbralo usando el código de tu idioma:

```bash
template.lang → es.lang
```

**Ejemplos:**
- `fr.lang` — Francés
- `de.lang` — Alemán
- `pt.lang` — Portugués

### 2. Abre el archivo con cualquier editor de texto.

### 3. Traduce solo el texto en el lado derecho de `=`:

```text
PyMenuPup Configurator = Configurador de PyMenuPup
Window = Ventana
Colors = Colores
Font = Fuente
```

### 4. Guarda el archivo y reinicia PyMenuPup.

**¡Eso es todo! 🎉** No se requieren cambios en el código Python.

---

## Variantes Regionales

Se admiten archivos de idioma regionales, por ejemplo:

- `es-MX.lang` — Español (México)
- `es-AR.lang` — Español (Argentina)
- `fr-CA.lang` — Francés (Canadá)
- `pt-BR.lang` — Portugués (Brasil)

Si no se encuentra un archivo regional, PyMenuPup automáticamente usará el idioma base (por ejemplo `es.lang`).

---

## Ejemplo de Flujo de Trabajo de Traducción

1. **Crea tu directorio de idioma:**
   ```bash
   mkdir -p ~/.config/pymenupup/locale
   ```

2. **Copia el template:**
   ```bash
   cp template.lang ~/.config/pymenupup/locale/es.lang
   ```

3. **Edita y traduce:**
   ```bash
   nano ~/.config/pymenupup/locale/es.lang
   ```

4. **Reinicia PyMenuPup** ¡y tu idioma será detectado automáticamente!

---

## Contribuir Traducciones

Si creas una traducción para un nuevo idioma, considera contribuirla al proyecto:

1. Haz un fork del repositorio
2. Agrega tu archivo `.lang` al directorio `locale/`
3. Envía un pull request
---


### Mapeo de Nombres de Categorías

El sistema de traducción maneja automáticamente los nombres de categorías en los menús JWM. Si tu JWM tiene categorías en tu idioma (ej. "Bureau" en francés), PyMenuPup las mapeará automáticamente a los nombres estándar en inglés internamente mientras las muestra en tu idioma.

---

## Variantes de Distribución

PyMenuPup tiene diferentes versiones optimizadas para distintos entornos Linux:

### Versión Original (Puppy Linux)
La versión principal (`pymenu-globicons.py` y `pymenu-config.py`) está diseñada específicamente para Puppy Linux, que:
- Ejecuta el sistema como usuario root por defecto
- No requiere el uso de `sudo` para operaciones del sistema
- Tiene rutas y configuraciones específicas de Puppy Linux

### Compatibilidad con EasyOS
Esta versión principal también es compatible con **EasyOS de Barry Kauler**, debido a que:
- EasyOS también se ejecuta como **root** por defecto  
- Utiliza un sistema de archivos frugal con capas, similar al de Puppy Linux  
- Las rutas del sistema y el entorno funcionan de forma muy parecida a los sistemas basados en Puppy  
No se requieren modificaciones para ejecutar la versión de Puppy Linux dentro de EasyOS.

### Versiones para Distribuciones Linux Estándar

En la carpeta `distro-linux/` encontrarás versiones adaptadas para otras distribuciones Linux que usan usuarios no root:

#### **Essora** (`distro-linux/Essora/`)
Versión modificada para distribuciones Linux estándar (Debian, Ubuntu, Arch, Fedora, etc.) con los siguientes cambios:

- **Gestión de permisos**: Uso apropiado de `sudo` para operaciones que requieren privilegios elevados
- **Rutas adaptadas**: Configuraciones ajustadas para estructuras de directorios de usuario estándar
- **Comandos del sistema**: Adaptación de comandos de apagado, reinicio y bloqueo para sistemas multiusuario
- **Variables de entorno**: Manejo correcto de `$HOME` y `$USER` para usuarios no root

#### **Trixiepup64** (`distro-linux/Trixiepup64/`)
Versión especializada para Trixiepup64 (Wayland + compositor labwc) con las siguientes características:

- **Compatibilidad con Wayland**: Optimizado para el servidor de display Wayland en lugar de X11
- **Integración con labwc**: Soporte nativo para el compositor labwc (similar a Openbox para Wayland)
- **Parser de menú Openbox**: Lee y analiza `menu.xml` del formato Openbox/labwc
- **Comandos específicos de Wayland**: Comandos del sistema adaptados para el entorno Wayland
- **Estructura Menu.xml**: Compatible con la estructura de menú estándar de Openbox usada por el generador de menús de labwc

**¿Cuándo usar cada versión?**
- **Usa la versión principal** si estás en Puppy Linux o derivados
- **Usa la versión Essora** si estás en Debian, Ubuntu, Arch, Fedora, Mint u otras distribuciones estándar
- **Usa la versión Trixiepup64** si estás en Trixiepup64 o cualquier sistema basado en Wayland que use el compositor labwc

---

## Dependencias

### Requisitos del Sistema

```
Python 3 (>= 3.6)
python3-gi
gir1.2-gtk-3.0
gir1.2-gdk-3.0
gir1.2-gdkpixbuf-2.0
gir1.2-pango-1.0
gir1.2-gio-2.0
gir1.2-glib-2.0
xdg-utils
Nerd Fonts
```

### Instalación de Dependencias

#### En Puppy Linux:
```bash
# El Gestor de Paquetes de Puppy (PPM) usualmente incluye python3-gi
# Verifica que lo tengas instalado:
python3 --version
python3 -c "import gi; print('GTK3 OK')"
```

#### En Debian/Ubuntu:
```bash
sudo apt update
sudo apt install python3 python3-gi python3-gi-cairo gir1.2-gtk-3.0 xdg-utils
```

#### En Arch Linux:
```bash
sudo pacman -S python python-gobject gtk3 xdg-utils
```

#### En Fedora/RHEL:
```bash
sudo dnf install python3 python3-gobject gtk3 xdg-utils
```

#### En Fossapup64 9.5

Gracias al usuario **Burunduk** por probar en Fossapup64. Para ejecutar PyMenu en una instalación fresca de Fossapup-9.5:

1. Abre el PPM (Gestor de Paquetes de Puppy)
2. Actualiza la base de datos (~16 MB de descarga)
3. Busca e instala `meld_3.20.2` y sus dependencias (~3 MB, usa modo auto-instalación)
4. Ejecuta PyMenu - ahora debería funcionar

**Nota:** Meld es una pequeña herramienta GUI diff que proporciona las dependencias GTK necesarias y puede ser útil por sí misma.

---

## Instalación

### Instalación Manual

1. Clona el repositorio:
```bash
git clone https://github.com/tu-usuario/PyMenuPup.git
cd PyMenuPup
```

2. Copia los scripts al sistema:
```bash
sudo cp pymenu-globicons.py /usr/local/bin/
sudo cp pymenu-config.py /usr/local/bin/

# Da permisos de ejecución
sudo chmod +x /usr/local/bin/pymenu-globicons.py
sudo chmod +x /usr/local/bin/pymenu-config.py
```

3. Copia los archivos de traducción:
```bash
sudo mkdir -p /usr/share/locale/pymenupup
sudo cp locale/*.lang /usr/share/locale/pymenupup/
sudo chmod 644 /usr/share/locale/pymenupup/*.lang
```

4. Crea enlaces simbólicos (opcional):
```bash
sudo ln -s /usr/local/bin/pymenu-globicons.py /usr/local/bin/pymenu
sudo ln -s /usr/local/bin/pymenu-config.py /usr/local/bin/pymenu-config
```

---

## 🛠️ Compilación desde el Código Fuente (Usando Nuitka en Puppy Linux / EasyOS)

Este proyecto permite compilar los scripts de Python en binarios `.bin` altamente optimizados utilizando **Nuitka**, un compilador de Python a C.  
A continuación se explica qué es, dónde obtenerlo y cómo usarlo en Puppy/EasyOS.

---

### 🧩 ¿Qué es Nuitka?

**Nuitka** es un compilador real de Python escrito en C++.  
Toma tus scripts `.py` y los convierte en:
- **Ejecutables nativos** (binarios)
- Mayor rendimiento
- Menor uso de CPU
- Sin necesidad de tener Python instalado para ejecutarlos

Es ideal para distribuir aplicaciones en Puppy Linux porque:
- Reduce el tamaño del programa
- Elimina dependencias externas
- Mejora la velocidad de arranque
- Protege mejor el código fuente

---

### 🌐 ¿Dónde Obtener Nuitka?

Puedes descargarlo directamente desde el sitio oficial:
- Sitio web: https://nuitka.net  
- Descargas: https://nuitka.net/pages/download.html  
- GitHub: https://github.com/Nuitka/Nuitka

En Puppy/EasyOS lo más común es descargarlo en la carpeta `/root/`:

Ejemplo:
```
/root/Nuitka-2.9rc5/
```

Dentro encontrarás el binario para compilar:
```
/root/Nuitka-2.9rc5/bin/nuitka
```

---

### 🔧 1. Instalar Dependencias Necesarias (Puppy Linux / EasyOS)

Para poder compilar debes activar el entorno de desarrollo.

**Cargar devx.sfs:**

Menú → Setup → SFS-Load-on-the-fly → devx.sfs

El `devx` incluye:
- gcc
- make
- libc-dev
- Python.h y otros headers necesarios

Además, instala estos paquetes:
- patchelf
- python3-zstandard
- python3-dev

Si tu Puppy/EasyOS soporta `apt`:
```bash
apt install patchelf python3-zstandard python3-dev
```

---

### ⚙️ 2. Compilar los Scripts Usando Nuitka

Ejemplo de compilación para `pymenu-globicons.py`:
```bash
python3 /root/Nuitka-2.9rc5/bin/nuitka \
    --mode=onefile \
    --follow-imports \
    --lto=yes \
    --static-libpython=no \
    --plugin-enable=gi \
    --nofollow-import-to=tkinter \
    --nofollow-import-to=unittest \
    --nofollow-import-to=pydoc \
    --nofollow-import-to=*.tests \
    --experimental=use_upx \
    /usr/local/bin/pymenu-globicons.py
```

El ejecutable generado aparecerá como:
```
pymenu-globicons.bin
```

Puedes renombrarlo (eliminar la extensión `.bin`) y moverlo a `/usr/local/bin`:
```bash
mv pymenu-globicons.bin /usr/local/bin/pymenu-globicons
chmod +x /usr/local/bin/pymenu-globicons
```

---

### 📝 3. Opciones Recomendadas de Nuitka

| Opción | Descripción |
|--------|-------------|
| `--mode=onefile` | Crea un archivo ejecutable único |
| `--lto=yes` | Optimización de tamaño y rendimiento |
| `--static-libpython=no` | Produce binarios más pequeños |
| `--follow-imports` | Incluye dependencias necesarias |
| `--experimental=use_upx` | Compresión adicional (si UPX está disponible) |

---

### 💡 Consejos

- La primera compilación puede tardar varios minutos
- Los binarios compilados son significativamente más rápidos que los scripts de Python
- Asegúrate de tener todas las dependencias de Python instaladas antes de compilar
- Prueba el binario después de compilar para verificar su funcionalidad

## Configuración

### Primera Ejecución

Al ejecutar PyMenuPup por primera vez, se creará automáticamente un archivo de configuración en:

```
~/.config/pymenu.json
```

### Configurando JWM

Edita tu archivo `~/.jwmrc` y agrega:

```xml
<Program label="Menu" icon="applications-system">
    /usr/local/bin/pymenu-globicons.py
</Program>
```

O para usar con coordenadas específicas:

```xml
<Program label="Menu" icon="applications-system">
    /usr/local/bin/pymenu-globicons.py 100 100
</Program>
```

En PuppyLinux /root/.jwmrc:

```xml
<RootMenu label="Menu" labeled="false" height="24" onroot="3">
```
luego /root/.jwmrc-tray

```xml
 <TrayButton label="[MENU]" popup="Open menú">exec:pymenu-globicons.py</TrayButton>
```

### Configurando con Tint2

Si usas Tint2, edita `~/.config/tint2/tint2rc`:

```ini
# Lanzador
launcher_item_app = /usr/local/bin/pymenu-globicons.py
```

---

## Herramientas Externas (Opcional)

PyMenu puede integrarse con herramientas externas para funcionalidad extendida. Estas herramientas **no están incluidas** en este proyecto y son completamente opcionales:

### Gestor de Perfil
- Una herramienta personalizada para configurar tu foto de perfil
- Configura la ruta en: **Ajustes > Rutas > Gestor de perfil**
- PyMenu funcionará sin esta herramienta

### Diálogo de Apagado
- Una interfaz personalizada de apagado/cierre de sesión
- Configura la ruta en: **Ajustes > Rutas > Comando de apagado**
- PyMenu funcionará sin esta herramienta

**Nota:** Los usuarios pueden especificar sus propias herramientas o scripts personalizados para estas funciones. Las rutas en la configuración son ejemplos y deben ajustarse a tu sistema.

---

## Uso

### Ejecutando el Menú

```bash
# Ejecución básica
pymenu-globicons.py

# Con posición personalizada (x, y)
pymenu-globicons.py 100 100

# Con archivo JWM personalizado
pymenu-globicons.py /ruta/a/jwmrc
```

### Abriendo el Configurador

```bash
pymenu-config.py
```

O desde el menú principal, haz clic en el icono de configuración.

### Atajos de Teclado

- **Esc**: Cerrar el menú
- **Alt + Clic Izquierdo**: Mover la ventana
- **Clic Central (rueda)**: Cerrar el menú
- **Teclas de Flecha**: Navegar por las aplicaciones
- **Enter**: Lanzar aplicación seleccionada
- **Clic Derecho en app**: Menú contextual

---

## Estructura de Archivos
```
PyMenuPup/
├── README.md                  # Archivo principal (inglés)
├── README-es.md               # Archivo principal (español)
├── TECHNICAL.md               # Documentación técnica (inglés)
├── TECHNICAL-es.md            # Documentación técnica (español)
├── pymenu-globicons.py        # Menú principal
├── pymenu-config.py           # Configurador GTK
├── pymenupuplang.py           # Sistema de traducción
├── distro-linux/             # Configuraciones específicas de cada distro
│   ├── Essora/
│   │   ├── Pymenu-essora.py
│   │   ├── pymenu-config-essora.py
│   │   └── pymenupuplang.py
│   └── Trixiepup-Wayland/
│       └── Pymenu-trixiewayland.py
├── locale/                   # Traducciones
│   ├── ar.lang                # Árabe
│   ├── de.lang                # Alemán
│   ├── es.lang                # Español
│   ├── fr.lang                # Francés
│   ├── it.lang                # Italiano
│   ├── ja.lang                # Japonés
│   ├── pt-BR.lang             # Portugués (Brasil)
│   ├── pt-PT.lang             # Portugués (Portugal)
│   ├── ru.lang                # Ruso
│   └── template.lang          # Plantilla base
└── screenshots/              # Capturas de pantalla
├── config-tool.png
└── main-menu.png
```

### Rutas de Instalación
```
/usr/local/bin/
├── pymenu-globicons.py       # Ejecutable del menú principal
├── pymenu-config.py          # Ejecutable del configurador
└── pymenupuplang.py          # Módulo de traducción

/usr/share/locale/pymenupup/
├── es.lang                   # Traducción español
└── fr.lang                   # Traducción francés

~/.config/pymenupup/
├── pymenu.json              # Configuración principal
└── locale/                  # Traducciones personalizadas del usuario (opcional)
    └── es-custom.lang

```

### Archivos de Configuración del Usuario

```
~/.config/
├── pymenu.json              # Configuración principal
└── tint2/
    └── tint2rc              # Config de Tint2 (si aplica)

~/
├── .jwmrc                   # Config de JWM
├── .jwmrc-tray             # Config de bandeja JWM
└── .face                    # Foto de perfil
```

---

## Personalización Avanzada

### Editando la Configuración Manualmente

El archivo `~/.config/pymenu.json` tiene esta estructura:

```json
{
    "window": {
        "width": 700,
        "height": 850,
        "decorated_window": false,
        "hide_header": false,
        "hide_quick_access": false,
        "hide_social_networks": false,
        "hide_category_text": false,
        "halign": "center",
        "icon_size": 32,
        "category_icon_size": 16,
        "profile_pic_size": 128,
        "profile_pic_shape": "square",
        "header_layout": "left"
    },
    "font": {
        "family": "Sans 12",
        "size_categories": 12000,
        "size_names": 10000,
        "size_header": 8000
    },
    "colors": {
        "use_gtk_theme": false,
        "background": "rgba(0, 0, 0, 0.7)",
        "border": "rgba(255, 255, 255, 0.1)",
        "text_normal": "#D8DEE9",
        "text_header_os": "#D8DEE9",
        "text_header_kernel": "#D0883A",
        "text_header_hostname": "#88C0D0",
        "hover_background": "rgba(255, 255, 255, 0.1)",
        "button_normal_background": "rgba(0,0,0,0.6)",
        "button_text": "#ECEFF4",
        "categories_background": "rgba(0,0,0,0.6)",
        "use_gtk_theme": true
    },
    "paths": {
        "profile_pic": "/root/.face",
        "profile_manager": "/usr/local/bin/ProfileManager.py",
        "shutdown_cmd": "/usr/local/bin/apagado-avatar.py",
        "jwmrc_tray": "/root/.jwmrc-tray",
        "tint2rc": "/root/.config/tint2/tint2rc"
    },
    "tray": {
        "use_tint2": false
    },
    "categories": {
        "excluded": []
    }
}
```

### Agregando Iconos Personalizados

PyMenuPup busca iconos en estas rutas:
- `/usr/local/lib/X11/pixmaps`
- `/usr/share/pixmaps`
- `/usr/share/icons/hicolor/*/apps`
- `/usr/share/pixmaps/puppy`

Coloca tus iconos en cualquiera de estas carpetas.

### Excluyendo Categorías

Edita el archivo de configuración para ocultar categorías específicas:

```json
"categories": {
    "excluded": ["Ayuda", "Salir", "Rectificar"]
}
```

---

## Solución de Problemas

### El menú no aparece

```bash
# Verifica que Python3 esté instalado
python3 --version

# Verifica las dependencias de GTK
python3 -c "import gi; gi.require_version('Gtk', '3.0'); from gi.repository import Gtk; print('GTK OK')"
```

### Los iconos no se muestran

```bash
# Verifica las rutas de iconos en tu .jwmrc
grep IconPath ~/.jwmrc

# Reinstala el paquete de iconos
# (en Puppy Linux usualmente viene incluido)
```

### Menú incompleto o faltan entradas
Si tu archivo `.jwmrc` contiene XML mal formado, el menú puede no cargarse completamente.
Incluso las secciones comentadas pueden causar errores si las etiquetas no están correctamente cerradas.

Ejemplo de un comentario incorrecto:

```xml
\<!-- comentario sin cerrar
```

### Errores de permisos

```bash
# Asegúrate de que los scripts sean ejecutables
chmod +x /usr/local/bin/pymenu-globicons.py
chmod +x /usr/local/bin/pymenu-config.py
```

### El menú se cierra inmediatamente

```bash
# Ejecuta desde la terminal para ver los errores
python3 /usr/local/bin/pymenu-globicons.py
```

### La foto de perfil no carga

```bash
# Verifica que la foto de perfil exista
ls -la ~/.face

# O verifica la ruta configurada
grep profile_pic ~/.config/pymenu.json
```

---

## Contribuir

¡Las contribuciones son bienvenidas! Si quieres mejorar PyMenuPup:

1. Haz un fork del repositorio
2. Crea una rama para tu característica (`git checkout -b feature/CaracteristicaAsombrosa`)
3. Haz commit de tus cambios (`git commit -m 'Agrega alguna CaracteristicaAsombrosa'`)
4. Haz push a la rama (`git push origin feature/CaracteristicaAsombrosa`)
5. Abre un Pull Request

---

## Licencia

Este proyecto está licenciado bajo la Licencia GPL v3. Consulta el archivo `LICENSE` para más detalles.

---

## Autor

Nilson Morales
- GitHub: [@woofshahenzup](https://github.com/Woofshahenzup)
- Foro: [Foro de Puppy Linux](https://forum.puppylinux.com)

---

## Agradecimientos

- Al equipo de Puppy Linux por crear una distribución tan ligera y eficiente
- A Joe Wingbermuehle por JWM (Joe's Window Manager)
- A las comunidades de GTK y Python
- A todos los contribuidores del proyecto

---

## Capturas de Pantalla y Demo

### Capturas de Pantalla
![Menú Principal](screenshots/main-menu.png)
![Herramienta de Configuración](screenshots/config-tool.png)

### Video Demo
[![Demo de PyMenuPup - Recorrido Completo](https://img.youtube.com/vi/CV71anlLqe8/maxresdefault.jpg)](https://www.youtube.com/watch?v=CV71anlLqe8)
*Haz clic para ver el demo completo en YouTube*

---

## Enlaces Útiles

- [Puppy Linux Oficial](https://puppylinux.com)
- [Documentación de JWM](http://joewing.net/projects/jwm/)
- [Documentación de GTK3](https://docs.gtk.org/gtk3/)
- [Documentación de Python GObject](https://pygobject.readthedocs.io/)

---

**¿Te gusta PyMenuPup? ¡Dale una estrella al repositorio!**
