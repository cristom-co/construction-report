# App: Registro de Avances de Obra con Evidencia Fotográfica

## Descripción General

Aplicación móvil enfocada en trabajadores de construcción, contratistas y pequeños negocios de obra para registrar avances mediante fotos, notas de voz y ubicación.

El objetivo principal es generar evidencia organizada del trabajo realizado para:

- demostrar avances al cliente,
- evitar discusiones,
- mostrar antes/después,
- respaldar cobros,
- documentar daños previos,
- crear historial del proyecto,
- generar reportes profesionales en PDF.

---

# Objetivo del Proyecto

Construir una aplicación móvil rápida, simple y de bajo consumo de batería que permita registrar evidencias de obra en segundos desde el teléfono.

La experiencia debe sentirse así:

1. abrir app,
2. tomar foto,
3. agregar nota rápida,
4. guardar automáticamente fecha y ubicación,
5. generar reportes profesionales.

---

# Público Objetivo

- albañiles,
- maestros de obra,
- contratistas,
- electricistas,
- plomeros,
- pintores,
- instaladores,
- técnicos independientes.

---

# Nombre Tentativo del Proyecto

Opciones:

- ObraTrack
- EvidenciaObra
- AvancePro
- ObraLog
- BuildProof
- RegistroObra
- FotoAvance
- Bitácora de Obra

---

# Funciones Principales

## 1. Registro Fotográfico

El usuario puede:

- tomar foto desde la cámara,
- seleccionar varias fotos,
- organizar fotos por proyecto,
- guardar fotos por fecha automáticamente.

### Datos almacenados por foto

- imagen,
- fecha,
- hora,
- ubicación GPS,
- proyecto asociado,
- notas,
- audio opcional.

---

## 2. Nota de Voz

Permitir grabar audio corto asociado al avance.

Ejemplo:

> “Se terminó instalación de tubería del baño principal.”

### Requisitos

- grabación simple,
- reproducción inmediata,
- almacenamiento local,
- compresión de audio ligera.

---

## 3. Ubicación Automática

La app NO debe usar GPS constantemente.

La ubicación se obtiene únicamente:

- al abrir la app,
- al guardar evidencia,
- al generar reporte.

Objetivo:

- minimizar consumo de batería,
- evitar procesos en segundo plano,
- mantener simplicidad.

---

## 4. Gestión de Proyectos

Cada proyecto debe contener:

- nombre,
- cliente,
- dirección,
- fecha de inicio,
- descripción,
- lista de evidencias.

---

## 5. Línea de Tiempo de Avances

Mostrar historial visual:

- fecha,
- fotos,
- notas,
- audios,
- ubicación.

Formato tipo timeline.

---

## 6. Comparador Antes / Después

Función importante.

Permitir:

- marcar una foto como “ANTES”,
- marcar otra como “DESPUÉS”,
- visualizar comparación lado a lado.

Muy útil para:

- remodelaciones,
- pintura,
- instalaciones,
- reparaciones.

---

## 7. Generación de PDF

Generar reportes profesionales automáticamente.

## Contenido del PDF

- logo del negocio,
- información del cliente,
- fechas,
- fotos,
- notas,
- ubicación,
- firma opcional,
- resumen del trabajo.

## Formatos

- reporte diario,
- reporte semanal,
- reporte completo del proyecto.

---

# Flujo Principal del Usuario

## Crear Proyecto

Usuario:

1. crea proyecto,
2. agrega cliente,
3. agrega dirección.

---

## Registrar Avance

Usuario:

1. abre proyecto,
2. toma foto,
3. agrega nota,
4. graba audio opcional,
5. guarda.

La app automáticamente:

- guarda fecha,
- guarda hora,
- obtiene ubicación,
- organiza evidencia.

---

## Generar Reporte

Usuario:

1. selecciona rango de fechas,
2. selecciona evidencias,
3. genera PDF,
4. comparte por WhatsApp o correo.

---

# Arquitectura Recomendada

## Frontend

### Recomendado

- Flutter

Ventajas:

- Android e iPhone,
- rápido de desarrollar,
- excelente cámara,
- buen soporte offline,
- PDFs fáciles,
- ideal para apps de campo.

---

## Backend

### Opción 1 — Firebase (Recomendado)

Servicios:

- Authentication,
- Firestore,
- Storage,
- Crashlytics.

Ventajas:

- rápido para MVP,
- escalable,
- simple,
- integración móvil excelente.

---

## Base de Datos

### Firestore

Colecciones:

```text
users/
projects/
evidences/
reports/
```

---

# Modelo de Datos

## Proyecto

```json
{
  "id": "project_001",
  "name": "Remodelación Casa Pérez",
  "clientName": "Juan Pérez",
  "address": "Cali, Colombia",
  "createdAt": "2026-05-18"
}
```

---

## Evidencia

```json
{
  "id": "evidence_001",
  "projectId": "project_001",
  "imageUrl": "...",
  "audioUrl": "...",
  "note": "Instalación terminada",
  "latitude": 3.4516,
  "longitude": -76.5320,
  "createdAt": "2026-05-18T10:30:00"
}
```

---

# Funciones Offline

Muy importante.

La app debe funcionar sin internet.

## Requisitos

- guardar evidencias localmente,
- sincronizar cuando vuelva internet,
- cachear proyectos,
- evitar pérdida de datos.

---

# Seguridad

## Requisitos

- autenticación básica,
- respaldo automático,
- cifrado de archivos sensibles,
- reglas de acceso por usuario.

---

# Optimización de Rendimiento

## Reglas Importantes

### NO usar GPS constantemente

Solo solicitar ubicación:

- al abrir app,
- al guardar evidencia.

---

### Compresión Inteligente de Fotos

Antes de subir:

- reducir tamaño,
- mantener calidad aceptable.

Objetivo:

- ahorrar almacenamiento,
- ahorrar datos móviles,
- acelerar subida.

---

# Funciones Futuras

## Posibles mejoras

### Firma Digital

Cliente firma conformidad.

---

### IA para Clasificación

Detectar automáticamente:

- paredes,
- pisos,
- tuberías,
- pintura,
- electricidad.

---

### Etiquetas Inteligentes

Ejemplo:

- “baño”,
- “cocina”,
- “fachada”.

---

### Recordatorios

Ejemplo:

> “Hace 5 días no registras avances en este proyecto.”

---

### Multiusuario

Equipo de trabajo colaborando en el mismo proyecto.

---

# Monetización

## Opciones

### Freemium

Gratis:

- 2 proyectos,
- PDFs básicos.

Premium:

- proyectos ilimitados,
- almacenamiento cloud,
- branding personalizado,
- exportaciones avanzadas.

---

# Stack Técnico Recomendado

## Mobile

- Flutter

## Backend

- Firebase

## Almacenamiento

- Firebase Storage

## Base de datos

- Firestore

## PDFs

- pdf package (Flutter)

## Mapas

- Google Maps SDK

## Estado

- Riverpod o Bloc

---

# Estructura Recomendada del Proyecto

```text
/lib
  /core
  /features
    /auth
    /projects
    /evidences
    /reports
  /shared
  /services
```

---

# MVP Inicial

## Versión 1.0

Debe incluir únicamente:

- login,
- crear proyecto,
- tomar foto,
- agregar nota,
- guardar ubicación,
- generar PDF,
- compartir reporte.

NO agregar:

- chat,
- IA avanzada,
- multiusuario,
- mapas complejos.

---

# Prioridades de Desarrollo

## Fase 1

- arquitectura base,
- autenticación,
- proyectos,
- cámara.

## Fase 2

- notas de voz,
- PDFs,
- almacenamiento cloud.

## Fase 3

- offline,
- sincronización,
- optimización.

---

# Objetivo Final

Crear una herramienta extremadamente rápida y práctica para trabajadores de campo, enfocada en:

- simplicidad,
- evidencia,
- organización,
- confianza con clientes,
- respaldo profesional del trabajo realizado.
