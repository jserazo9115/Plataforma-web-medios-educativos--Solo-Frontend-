# Medios Educativos – Universidad CESMAG

Frontend del módulo administrativo de **Medios Educativos**.

## Stack (según Guía Técnica)

- React 19 + TypeScript
- Vite
- Material UI (MUI) v5
- React Router v6
- Axios (preparado)
- SweetAlert2
- Day.js / Zustand (disponibles)

## Estructura del módulo Solicitudes

```
src/
├── components/
│   └── AdminLayout.tsx          # Layout + menú lateral (listo para enlazar)
├── pages/MediosEducativos/Admin/Solicitudes/
│   ├── Solicitudes.tsx          # Listado + filtros + tabla
│   ├── SolicitudDetalle.tsx     # Detalle 1:1 del prototipo
│   ├── components/
│   │   ├── SolicitudesFilters.tsx
│   │   └── SolicitudesTable.tsx
│   ├── interfaces/
│   │   └── solicitudes.interface.ts
│   └── services/
│       └── solicitudes.service.ts   # Mock data → listo para API
├── routes/
│   └── AppRoutes.tsx
└── App.tsx
```

## Cómo ejecutar

```bash
cd medios-educativos
npm install --legacy-peer-deps
# o
yarn install

npm run dev
```

Abrir `http://localhost:5173` → redirige a `/admin/solicitudes`.

## Funcionalidad actual

- **Listado de Solicitudes**: filtros (código/solicitante, estado, campus, fecha, espacio), tabla 1:1, botón “Nueva solicitud” (placeholder).
- **Ver detalle →**: navega a `/admin/solicitudes/:id` y muestra el detalle completo 1:1.
- **Aprobar / Rechazar**: funcional con confirmación (SweetAlert2) y actualización de estado (mock).
- Menú lateral completo y listo para ir enlazando el resto de pantallas.

## Datos ficticios

Los datos viven en `solicitudes.service.ts`.  
Para conectar a la API real solo hay que reemplazar las funciones `getSolicitudes`, `getSolicitudById` y `updateEstadoSolicitud` por llamadas Axios.

## Próximos pasos (según guía)

1. Login administrativo (reutilizar Auth Context existente).
2. Gestión de campus / Tipos de espacio / Gestión de espacios.
3. Agenda por campus.
4. Dashboard.
5. Integración real con backend.
