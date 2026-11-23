# Guía del Equipo Frontend — Municipio de Ibarra (SIME / SRGE)

> **Repositorio oficial del equipo:** `https://github.com/Fereris-Coder/municipio-ibarra-frontend.git`  
> **Tablero de tareas (Microsoft Planner):** [Vinculación O26M27](https://planner.cloud.microsoft/ui/web/plan/pdq06Os9RUStU6e9gvaJhmQAELED/view/grid?tid=db49f171-9aed-4477-afdc-bcab069eb75b)  
> **Stack:** Next.js 16 (App Router) · React 19 · TypeScript · Tailwind CSS v4 · shadcn/ui · Zustand · React Hook Form + Zod

---

## 1. Configuración inicial en tu computadora

1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com/Fereris-Coder/municipio-ibarra-frontend.git
   cd municipio-ibarra-frontend
   ```
2. **Instalar dependencias:**
   ```bash
   npm install
   ```
3. **Configurar variables de entorno:**
   ```bash
   cp .env.example .env.local
   ```
   *(Verifica que `.env.local` apunte a `NEXT_PUBLIC_API_BASE_URL=http://localhost:9000/api` o a la URL del Backend de pruebas asignada).*
4. **Levantar en desarrollo:**
   ```bash
   npm run dev
   ```
   Abre `http://localhost:3000`.

---

## 2. Flujo de Git obligatorio (Cero conflictos)

* **`main`**: Código estable de entrega (solo merge desde `develop` vía PR aprobado por el Líder).
* **`develop`**: Rama de integración semanal del equipo.
* **Regla de oro:** **NUNCA** hacer `git push` directo a `main` ni a `develop`. Cada integrante trabaja en su rama asignada (creada desde `develop`) y abre un **Pull Request (PR) hacia `develop`** al terminar cada subtarea.

Comandos para trabajar en tu rama:
```bash
git checkout develop
git pull origin develop
git checkout <tu-rama-asignada>
git merge develop
# ... realizas tus cambios ...
git add .
git commit -m "feat: descripcion corta en minusculas"
git push origin <tu-rama-asignada>
```
Luego entra a GitHub y crea el **Pull Request → `develop`**.

---

## 3. Distribución de Tareas, Ramas y Carpetas por Integrante

| Integrante | Rama asignada | Carpetas principales en `src/` | Actividades en Planner (`1.5`, `1.8`, `1.9`, `2.1`) |
|---|---|---|---|
| **Felipe Renato Ricaurte** *(Líder)* | `feature/core-auth` | `src/features/auth`, `src/app/(auth)`, `src/lib` | Setup repo/PRs, Login JWT, menú dinámico por `rol_ruta_acceso`, coordinación Backend/BD (`1.7`, `1.8`, `1.9`, `2.1`–`2.5`). |
| **Cristian Angulo** | `feature/api-catalogos` | `src/lib`, `src/types`, `src/features/**/services` | Cliente HTTP/API, DTOs TypeScript, catálogos dinámicos (cero IDs quemados), validación contra Backend/BD de pruebas y QA E2E (`1.5`, `1.6`, `1.8`, `1.9`, `1.10`). |
| **Allison Rodriguez** | `feature/fase1-portal-wizard` | `src/features/landing`, `src/features/registro-emprendedor`, `src/app/(public)` | Identidad visual/capturas (`1.5`), Portal público, Consulta de estado y Wizard Pasos 1–3 + Borrador (`1.8`, `1.9`, `2.1`). |
| **Fernando Castro** | `feature/fase1-admin-cruds` | `src/features/emprendedores`, `src/features/emprendimientos`, `src/features/formularios`, `src/features/usuarios` | Auditoría de brechas Fase 1 (`1.5`), Wizard Pasos 4–6 y CRUDs Admin de Emprendedores, Emprendimientos, Asistencia y Usuarios (`1.8`, `1.9`). |
| **Guido Rea** | `feature/fase2-sime-g1-g3` | `src/features/asesorias/modelo-negocio`, `src/features/modelo-negocio`, `src/app/(dashboard)/asesorias` | Shell SIME 16 pasos (`mn_progreso_modelo`), grupos G1–G3 y subida de fotos de productos `multipart/form-data` (`1.8`, `1.9`). |
| **David Cañas** | `feature/fase2-sime-finanzas` | `src/features/asesorias/modelo-negocio` *(costos, proyección, canvas, foda)* | Estructura de costos, Simulador Financiero en vivo a 20 trimestres, Canvas 9 bloques y Matriz FODA (`1.8`, `1.9`). |
| **Hair Vargas** | `feature/dashboard-reportes` | `src/features/dashboard`, `src/features/reportes`, `src/app/api/reportes` | Dashboard estadístico, los 4 reportes PDF del panel y exportador oficial SIME a PDF y Word `.docx` (`1.8`, `1.9`, `2.1`). |

---

## 4. Checklist de Calidad antes de abrir PR
- [ ] `npm run lint` sin errores.
- [ ] `npm run build` compila limpio.
- [ ] Sin IDs quemados en código (`if (id === 3)` ❌ → usar códigos/banderas semánticas como `es_terminal` ✅).
- [ ] Marcar el avance de tu ítem en el checklist de la tarjeta correspondiente en [Microsoft Planner](https://planner.cloud.microsoft/ui/web/plan/pdq06Os9RUStU6e9gvaJhmQAELED/view/grid?tid=db49f171-9aed-4477-afdc-bcab069eb75b).
