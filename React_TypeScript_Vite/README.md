---

src
├── assets # Recursos estáticos como imágenes, fuentes, estilos globales
│
├── core # Código reutilizable (hooks, contextos, utilidades, servicios)
│ ├── api # Configuración de llamadas a la API
│ ├── components # Componentes compartidos (botones, inputs, modales)
│ ├── hooks # Hooks personalizados
│ ├── utils               # Utilidades y funciones helper
│ └── styles              # Estilos globales (resets, variables, mixins)
│       ├── _variables.scss
│       ├── _mixins.scss
│       └── global.scss
│
├── pods # Un pod por cada funcionalidad o feature
│ ├── members # Pod para manejar miembros de la organización
│ │ ├── components # Componentes específicos del pod (MemberList, MemberItem)
│ │ │      ├── MemberList.tsx
│ │ │      ├── MemberList.module.scss  # Estilos específicos para el componente
│ │ │      └── MemberItem.module.scss
│ │ │   
│ │ ├── models # Tipos y modelos de datos para miembros
│ │ │      └── member.model.ts
│ │ │   
│ │ ├── services # Llamadas a la API y lógica de negocio para miembros
│ │ │      └── members.service.ts
│ │ │   
│ │ └── pages # Páginas relacionadas con los miembros (listado, detalle)
│ │ │      ├── MembersPage.tsx
│ │ │      └── MembersPage.module.scss
│ │ │
│ │ └── index.ts
│ │    
│ └── home # Pod para la pantalla principal
│   ├── components
│   ├── pages
│   └── pages.module.scss
│
├── App.tsx # Punto de entrada principal de la aplicación
├── main.tsx # Renderizado de React y configuración principal
├── vite-env.d.ts # Configuración de tipos para Vite
│
├── .gitignore  
├── eslint.config.js  
├── index.html  
├── package.json  
├── tsconfig.json  
├── vite.config.ts

---

# Explicación

- **assets:** Archivos estáticos como imágenes y estilos globales.
- **core:** Contiene lógica compartida y reusable, como componentes globales (inputs, botones), hooks personalizados, y servicios generales como autenticación o gestión de errores.
- **pods:** Cada funcionalidad (como gestionar miembros) tiene su propio pod que contiene:

  - **components:** Componentes específicos del pod.
  - **models:** Tipos y definiciones de datos (TypeScript).
  - **services:** Llamadas a la API y lógica de negocio.
  - **pages:** Vistas específicas de este pod.

- **Raíz del proyecto:** Archivos de configuración y el punto de entrada principal.

## Explicación sobre la colocación de los archivos CSS:

### 1. Estilos globales (core/styles)

- Archivo `global.scss`: Contiene estilos globales como el reset de CSS, fuentes, y layout general.
- Archivo `_variables.scss`: Definición de variables como colores, fuentes y tamaños.
- Archivo `_mixins.scss`: Mixins y funciones reutilizables para el proyecto.

### 2. Estilos específicos de un pod (pods)

- Cada pod tiene sus propios archivos de estilos.
- Se recomienda usar CSS Modules (`.module.scss`) para el scoping de estilos y evitar colisiones entre pods.
- Los archivos CSS se ubican junto a sus respectivos componentes, siguiendo el principio de colocalización.
- **Uso de CSS Modules en un componente:**

```tsx
import styles from "./MemberList.module.scss";
```

# Ventajas de esta estructura:

- **Modularidad:** Cada pod está aislado, facilitando el mantenimiento y pruebas.
- **Escalabilidad:** Se pueden añadir más pods fácilmente sin modificar el resto del proyecto.
- **Separación de responsabilidades:** Cada pod es dueño de su lógica y presentación.

# Ventajas de esta organización CSS:

- **Modularidad:** Cada pod gestiona sus propios estilos.
- **Evita colisiones:** El uso de CSS Modules asegura que los estilos estén aislados.
- **Escalabilidad:** Fácil de mantener y extender con nuevos pods y estilos.
- **Consistencia:** Variables y mixins centralizados en `core/styles`.

---
