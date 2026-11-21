# Search & Rescue: Kodiak

Juego de rescate marítimo en helicóptero (U.S. Coast Guard · Air Station Kodiak, Alaska) desarrollado con HTML5 Canvas, Web Audio API y JavaScript modular sin dependencias externas.

## Estructura del proyecto

```text
├── index.html                   # Documento principal e interfaz del juego
├── manifest.webmanifest         # Manifiesto PWA e iconos
├── assets/
│   ├── i18n/
│   │   └── en.json              # Diccionario de traducción al inglés (carga bajo demanda)
│   ├── icons/
│   │   ├── favicon.png          # Icono principal (180×180)
│   │   └── apple-touch-icon.png # Icono iOS / PWA (640×640)
│   └── images/splash/
│       ├── epsilon-sym.webp     # Símbolo de Épsilon Games Studio
│       ├── epsilon-word.webp    # Logotipo tipográfico
│       └── epsilon-sub.webp     # Subtítulo "Games Studio"
├── css/
│   ├── main.css                 # Estilos del juego, menús y controles táctiles
│   └── splash.css               # Estilos y animaciones de la intro y aviso iOS
└── js/
    ├── main.js                  # Núcleo de simulación, física, renderizado, HUD y flujo de menús
    ├── audio.js                 # Música y efectos sintetizados con Web Audio API
    ├── gamepad.js               # Soporte de mandos USB/BT (Xbox, PlayStation, Nintendo y PC)
    ├── sprites.js               # Generador procedural de sprites pixel-art en canvas
    ├── i18n.js                  # Gestor de idioma y carga diferida de traducciones
    ├── splash.js                # Secuencia de introducción y pantalla completa móvil
    ├── utils.js                 # Utilidades matemáticas y de color
    └── data/
        ├── vehicles.js          # Especificaciones de helicópteros y embarcaciones
        ├── missions.js          # Parámetros del planificador de misiones y presets
        └── campaign.js          # Guion, diálogos y misiones del modo campaña
```

## Desarrollo local

El proyecto usa ES Modules nativos (`<script type="module">`) y carga las traducciones vía `fetch()`, por lo que requiere servirse mediante HTTP local (no abrir directamente con `file://`):

```bash
python3 -m http.server 8000
```

Después abre <http://localhost:8000> en el navegador.

## Despliegue

Pensado para servir archivos estáticos directamente en **GitHub Pages** desde la rama `main` sin paso de compilación.