<div align="center">

# 🌦️ ClimaTrip

### Clima inmersivo y planificador de viajes inteligente

*Un dashboard meteorológico premium con escenas animadas, pronósticos detallados y un planificador de viajes que te recomienda qué llevar, qué hacer y a qué prestar atención en cada destino.*

[![React](https://img.shields.io/badge/React-18.3-61DAFB?logo=react&logoColor=white)](https://react.dev)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.8-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Vite](https://img.shields.io/badge/Vite-5.4-646CFF?logo=vite&logoColor=white)](https://vitejs.dev/)
[![TailwindCSS](https://img.shields.io/badge/Tailwind-3.4-38B2AC?logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![shadcn/ui](https://img.shields.io/badge/shadcn%2Fui-black?logo=shadcnui&logoColor=white)](https://ui.shadcn.com/)

</div>

---

## ✨ Características

### 🌤️ Dashboard del tiempo
- **Escena animada de fondo** que cambia según la condición meteorológica y la hora del día (sol, lluvia, nubes, nieve, noche estrellada…).
- **Pronóstico horario interactivo** — selecciona cualquier hora para previsualizar las condiciones.
- **Pronóstico semanal** con máximas, mínimas, probabilidad de lluvia y viento.
- **Métricas en tiempo real:** sensación térmica, humedad, viento, presión, nubosidad, índice UV y calidad del aire (AQI).
- **Búsqueda híbrida** de ciudades, regiones, comunidades autónomas y países (Open-Meteo + Nominatim/OSM).
- **Favoritos** persistentes para acceder rápido a tus ubicaciones habituales.

<img width="1560" height="847" alt="{AB26ECD0-4F0C-4471-BDC5-8F31454275A6}" src="https://github.com/user-attachments/assets/70150f42-4b12-4a6c-878f-b83e56d17866" />

<img width="1589" height="768" alt="{366CA3BA-BB0E-4CBA-BE6F-FB6CA3C13084}" src="https://github.com/user-attachments/assets/a25f263e-767b-425a-93d3-cea87c13a211" />

### 🧳 Planificador de viajes
- **Multi-destino:** añade varias ciudades y construye tu itinerario completo.
- **Pronóstico por día y destino** con tira deslizable horizontal.
- **Recomendaciones inteligentes** generadas a partir del clima previsto:
  - 🎒 **Packing pool** — qué meter en la maleta.
  - 🎯 **Activities pool** — qué hacer en cada destino según el tiempo.
  - ⚠️ **Warnings pool** — alertas de calor, lluvia, viento, UV, etc.
- **Modo de transporte** (vuelo, coche, tren) que ajusta los consejos.
- **Guardado de viajes** con persistencia local y carga posterior.
- **Prevención de duplicados** y validación de coordenadas para evitar destinos repetidos.
<img width="1109" height="478" alt="{298E9E39-5A76-4068-B5A7-071D81DC166A}" src="https://github.com/user-attachments/assets/7a1108da-0423-40a6-acac-b4eae770e5a0" />

<img width="1168" height="839" alt="{2E38BE7E-ABAD-46F3-AC5A-8B383C7C2CB6}" src="https://github.com/user-attachments/assets/4e52eefb-fe8f-499a-a16d-ff68f5b06c5f" />



### 🎨 Experiencia de usuario
- Tema oscuro elegante con tokens semánticos HSL.
- Tipografía **Inter** y jerarquía visual cuidada.
- Animaciones suaves, microinteracciones y feedback visual con *toasts*.
- Totalmente responsive (móvil, tablet, escritorio).
- Scroll horizontal "wheel-hijack" inteligente que libera la página al final del recorrido.

---

## 🚀 Inicio rápido

### Requisitos

- **Node.js** ≥ 18 (recomendado 20+)
- **bun**, **npm** o **pnpm**

### Instalación

```bash
# 1. Clona el repositorio
git clone <https://github.com/aisurf3r/Clima-Trip>
cd climatrip

# 2. Instala las dependencias
bun install        # o: npm install

# 3. Arranca el servidor de desarrollo
bun run dev        # o: npm run dev
```

La app estará disponible en [http://localhost:8080](http://localhost:8080).

### Scripts disponibles

| Comando             | Descripción                                       |
| ------------------- | ------------------------------------------------- |
| `bun run dev`       | Servidor de desarrollo con HMR                    |
| `bun run build`     | Build de producción optimizado                    |
| `bun run build:dev` | Build en modo desarrollo (sin minificar)          |
| `bun run preview`   | Sirve el build de producción localmente           |
| `bun run lint`      | Ejecuta ESLint sobre todo el proyecto             |
| `bun run test`      | Ejecuta la suite de tests con Vitest              |
| `bun run test:watch`| Tests en modo *watch*                             |

---

## 🧱 Stack técnico

| Capa            | Tecnología                                                |
| --------------- | --------------------------------------------------------- |
| **Framework**   | React 18 + Vite 5 + TypeScript 5                          |
| **Estilos**     | Tailwind CSS 3 + tokens semánticos HSL                    |
| **Componentes** | shadcn/ui + Radix UI                                      |
| **Iconografía** | lucide-react                                              |
| **Routing**     | React Router 6                                            |
| **Estado**      | TanStack Query + hooks locales (`useState`, `useReducer`) |
| **Fechas**      | date-fns (locale `es`)                                    |
| **Notificaciones** | sonner + shadcn toast                                  |
| **Formularios** | react-hook-form + zod                                     |
| **APIs**        | Open-Meteo (tiempo) + Nominatim/OSM (geocoding regional)  |
| **Tests**       | Vitest + Testing Library + jsdom                          |

---

## 📁 Estructura del proyecto

```
src/
├── components/
│   ├── ui/                    # shadcn/ui components
│   ├── WeatherDashboard.tsx   # Vista principal del clima
│   ├── WeatherScene.tsx       # Fondo animado por condición
│   ├── HourlyForecast.tsx     # Pronóstico horario
│   ├── DailyForecast.tsx      # Pronóstico semanal
│   ├── TripPlanner.tsx        # Planificador multi-destino
│   ├── CitySearch.tsx         # Buscador con autocompletado
│   ├── FavoritesBar.tsx       # Acceso rápido a favoritos
│   ├── MetricTile.tsx         # Tarjeta de métrica
│   └── WeatherIcon.tsx        # Icono dinámico día/noche
├── hooks/
│   ├── use-drag-scroll.ts     # Scroll horizontal con wheel-hijack
│   ├── use-local-storage.ts   # Persistencia tipada
│   └── use-theme.ts           # Gestión de tema
├── lib/
│   ├── weather-api.ts         # Cliente Open-Meteo + Nominatim
│   ├── trip-insights.ts       # Motor de recomendaciones
│   └── utils.ts               # Utilidades (cn, etc.)
├── pages/
│   ├── Index.tsx              # Página principal
│   └── NotFound.tsx           # 404
├── App.tsx
├── main.tsx
└── index.css                  # Design tokens (HSL)
```

---

## 🎨 Sistema de diseño

Todos los colores se definen como **tokens HSL semánticos** en `src/index.css` y se exponen vía `tailwind.config.ts`. Nunca se usan colores literales (`text-white`, `bg-black`) en componentes — siempre `text-foreground`, `bg-background`, `text-primary`, etc.

```css
:root {
  --background: 222 47% 7%;
  --foreground: 210 40% 98%;
  --primary: 199 89% 60%;
  --primary-glow: 199 100% 75%;
  /* … */
}
```

Esto garantiza consistencia, soporte limpio para temas y un único punto de cambio para rediseños globales.

---

## 🌐 APIs utilizadas

| Servicio                                                  | Uso                                          |
| --------------------------------------------------------- | -------------------------------------------- |
| [Open-Meteo Forecast](https://open-meteo.com/)            | Pronóstico actual, horario y diario          |
| [Open-Meteo Geocoding](https://open-meteo.com/en/docs/geocoding-api) | Búsqueda de ciudades                |
| [Open-Meteo Air Quality](https://open-meteo.com/en/docs/air-quality-api) | AQI europeo y contaminantes      |
| [Nominatim (OSM)](https://nominatim.org/)                 | Búsqueda de regiones, estados y países       |

> Todas las APIs son **gratuitas y sin clave**, ideales para prototipado y producción ligera.

---

## 🧪 Testing

```bash
bun run test          # Ejecuta todos los tests una vez
bun run test:watch    # Modo watch para desarrollo
```

Los tests viven en `src/test/` y usan `Vitest` + `@testing-library/react`.

---

## 📦 Build y despliegue

```bash
bun run build
```

El build se genera en `dist/` y se puede desplegar en cualquier hosting estático: **Vercel**, **Netlify**, **Cloudflare Pages**, **GitHub Pages**, etc.

Si usas Lovable, basta con pulsar **Publish** en la esquina superior derecha del editor.

---


<div align="center">

Hecho con ❤️ por Aisurf3r · React · Tailwind · Open-Meteo

</div>
