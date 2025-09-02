# ChatzIA.ai - Plataforma de Agentes IA

Bienvenido a ChatzIA.ai, una plataforma de código abierto construida con Next.js y Genkit para crear, gestionar y desplegar agentes de Inteligencia Artificial para atención al cliente. Esta aplicación ha sido desarrollada de forma interactiva en Firebase Studio.

## Características Principales

- **Creación de Agentes desde Archivos**: Los usuarios pueden subir documentos (.txt, .pdf) que actúan como base de conocimiento para sus agentes de IA.
- **Playground Interactivo**: Una vez creado un agente, los usuarios son redirigidos a un "Playground" donde pueden chatear con él y ajustar su comportamiento en tiempo real.
- **Configuración Avanzada del Agente**: Ajusta el modelo de IA, la "temperatura" (creatividad) y el "prompt del sistema" para refinar la personalidad y las respuestas del agente.
- **Dashboard de Agentes**: Un panel central que muestra métricas clave como el número de agentes activos, mensajes consumidos y la tasa de resolución.
- **Sugerencias de Planes con IA**: Una sección de facturación que utiliza un flow de Genkit para analizar el patrón de uso de un usuario y recomendar el plan de suscripción más adecuado.
- **Interfaz Moderna y Responsiva**: Construida con ShadCN/UI y Tailwind CSS, incluyendo un menú de navegación lateral colapsable que se expande al pasar el ratón por encima.

## 🚀 Stack Tecnológico

- **Framework**: [Next.js](https://nextjs.org/) (con App Router)
- **Lenguaje**: [TypeScript](https://www.typescriptlang.org/)
- **Inteligencia Artificial**: [Genkit](https://firebase.google.com/docs/genkit) (utilizando los modelos de Google AI)
- **Estilos**: [Tailwind CSS](https://tailwindcss.com/)
- **Componentes de UI**: [ShadCN/UI](https://ui.shadcn.com/)
- **Gráficos**: [Recharts](https://recharts.org/)
- **Validación de Formularios**: [React Hook Form](https://react-hook-form.com/) & [Zod](https://zod.dev/)

## 📂 Estructura del Proyecto

El código fuente está organizado siguiendo las mejores prácticas de un proyecto Next.js:

- **`src/app/`**: Contiene todas las rutas y páginas de la aplicación. La estructura de carpetas se mapea directamente a las URLs.
  - **`src/app/(app)`**: Agrupa las páginas internas de la aplicación que comparten el layout principal con la barra de navegación.
  - **`src/app/layout.tsx`**: Es la plantilla raíz de la aplicación.
  - **`src/app/page.tsx`**: Es la página de inicio (landing page).
- **`src/components/`**: Alberga todos los componentes reutilizables de React.
  - **`ui/`**: Componentes base de ShadCN/UI (Button, Card, Input, etc.).
  - **`landing/`**: Componentes específicos para la página de inicio.
- **`src/ai/`**: Aquí reside toda la lógica de la Inteligencia Artificial.
  - **`flows/`**: Contiene los "flujos" de Genkit, que definen tareas específicas para la IA (ej. `createInitialAgentFromFAQ.ts`).
  - **`genkit.ts`**: Archivo de configuración inicial para Genkit.
- **`src/lib/`**: Funciones de utilidad y configuración de servicios como Firebase.
- **`src/hooks/`**: Hooks personalizados de React (ej. `use-toast.ts` para notificaciones).

## ⚙️ Cómo Empezar (Instalación Local)

Sigue estos pasos para ejecutar el proyecto en tu máquina local.

### Prerrequisitos

- [Node.js](https://nodejs.org/en/) (versión 18 o superior)
- [npm](https://www.npmjs.com/) o [yarn](https://yarnpkg.com/)

### 1. Clonar el repositorio

```bash
git clone https://github.com/tu-usuario/chatzia-ai.git
cd chatzia-ai
```

### 2. Instalar dependencias

```bash
npm install
```

### 3. Configurar las variables de entorno

Crea un archivo llamado `.env.local` en la raíz del proyecto y añade tu clave de API de Google AI:

```env
# Clave de API para los modelos de Google AI (Gemini)
GEMINI_API_KEY="TU_API_KEY_DE_GOOGLE_AI"
```

### 4. Ejecutar el servidor de desarrollo

Para iniciar la aplicación Next.js y el servidor de Genkit (en modo de observación para recarga automática), puedes ejecutar los siguientes comandos en dos terminales separadas:

**Terminal 1 (Aplicación Next.js):**

```bash
npm run dev
```

La aplicación estará disponible en `http://localhost:9002`.

**Terminal 2 (Servidor Genkit):**

```bash
npm run genkit:watch
```

Esto iniciará el servidor de Genkit que gestiona los flujos de IA.

¡Y listo\! Ahora tienes el entorno completo de ChatzIA.ai corriendo localmente.