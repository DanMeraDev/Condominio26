# Documentación de Casos de Uso
## Módulo GRC – Gestión de Inmuebles

---

## 1. Descripción General

El módulo **GRC – Gestión de Inmuebles** permite administrar el ciclo de vida de los inmuebles dentro de un condominio, incluyendo el mantenimiento del catálogo, la gestión de propiedades por propietario y la realización de reservas o agendas por parte de los usuarios.

---

## 2. Actores

| Actor | Descripción |
|---|---|
| **Administrador** | Responsable de gestionar el catálogo del condominio, actualizar estados de inmuebles y administrar los inmuebles registrados. |
| **Propietario** | Gestiona las propiedades asociadas a su nombre dentro del sistema. |
| **Usuario** | Realiza reservas o agendas relacionadas a los inmuebles. |

---

## 3. Casos de Uso

### CU-01 – Mantener catálogo del condominio

| Campo | Detalle |
|---|---|
| **Actor principal** | Administrador |
| **Descripción** | Permite al administrador crear, modificar y eliminar entradas del catálogo general del condominio. |
| **Incluye** | Gestionar características del condominio |
| **Precondiciones** | El administrador debe estar autenticado en el sistema. |
| **Postcondiciones** | El catálogo del condominio queda actualizado con la información correspondiente. |

---

### CU-02 – Gestionar características del condominio *(incluido)*

| Campo | Detalle |
|---|---|
| **Actor principal** | Administrador |
| **Descripción** | Subproceso incluido en CU-01. Permite definir y actualizar atributos específicos del condominio (nombre, ubicación, número de unidades, etc.). |
| **Incluido por** | Mantener catálogo del condominio |
| **Precondiciones** | Se debe estar ejecutando el flujo de CU-01. |

---

### CU-03 – Actualizar estado del inmueble

| Campo | Detalle |
|---|---|
| **Actor principal** | Administrador |
| **Descripción** | Permite al administrador modificar el estado de un inmueble (disponible, ocupado, en mantenimiento, etc.). |
| **Incluye** | Generar reportes de cambios |
| **Precondiciones** | El inmueble debe estar previamente registrado en el sistema. |
| **Postcondiciones** | El estado del inmueble es actualizado y se genera un reporte de los cambios realizados. |

---

### CU-04 – Generar reportes de cambios *(incluido)*

| Campo | Detalle |
|---|---|
| **Actor principal** | Administrador |
| **Descripción** | Subproceso incluido en CU-03. Genera un registro o reporte con el historial de cambios de estado del inmueble. |
| **Incluido por** | Actualizar estado del inmueble |
| **Precondiciones** | Se debe estar ejecutando el flujo de CU-03. |

---

### CU-05 – Administrar inmuebles

| Campo | Detalle |
|---|---|
| **Actor principal** | Administrador |
| **Descripción** | Permite al administrador gestionar el inventario de inmuebles del condominio, incluyendo el registro de nuevos edificios y unidades. |
| **Incluye** | Registrar edificios, Registrar departamentos, suites, estudios y locales |
| **Precondiciones** | El administrador debe estar autenticado. |
| **Postcondiciones** | Los inmuebles quedan registrados y disponibles en el sistema. |

---

### CU-06 – Registrar edificios *(incluido)*

| Campo | Detalle |
|---|---|
| **Actor principal** | Administrador |
| **Descripción** | Subproceso incluido en CU-05. Permite registrar la información de un edificio dentro del condominio. |
| **Incluido por** | Administrar inmuebles |

---

### CU-07 – Registrar departamentos, suites, estudios y locales *(incluido)*

| Campo | Detalle |
|---|---|
| **Actor principal** | Administrador |
| **Descripción** | Subproceso incluido en CU-05. Permite registrar las distintas tipologías de unidades habitacionales o comerciales dentro de un edificio. |
| **Incluido por** | Administrar inmuebles |
| **Precondiciones** | El edificio correspondiente debe estar previamente registrado (CU-06). |

---

### CU-08 – Gestionar propiedades de cada propietario

| Campo | Detalle |
|---|---|
| **Actor principal** | Propietario |
| **Descripción** | Permite al propietario visualizar y gestionar las unidades inmobiliarias asociadas a su cuenta (departamentos, suites, estudios o locales). |
| **Precondiciones** | El propietario debe estar autenticado y tener inmuebles asignados. |
| **Postcondiciones** | La información de las propiedades del propietario queda actualizada. |

---

### CU-09 – Realizar reserva o agenda

| Campo | Detalle |
|---|---|
| **Actor principal** | Usuario |
| **Descripción** | Permite al usuario realizar una reserva o agendar el uso de un espacio o inmueble disponible dentro del condominio. |
| **Incluye** | Gestionar notificaciones y recordatorios |
| **Precondiciones** | El usuario debe estar autenticado y el inmueble/espacio debe estar disponible. |
| **Postcondiciones** | La reserva queda registrada y se envían las notificaciones y recordatorios correspondientes. |

---

### CU-10 – Gestionar notificaciones y recordatorios *(incluido)*

| Campo | Detalle |
|---|---|
| **Actor principal** | Usuario |
| **Descripción** | Subproceso incluido en CU-09. Administra el envío de notificaciones de confirmación y recordatorios previos a la fecha de reserva. |
| **Incluido por** | Realizar reserva o agenda |

---

## 4. Relaciones entre Casos de Uso

```
CU-01 Mantener catálogo del condominio
  └── «include» CU-02 Gestionar características del condominio

CU-03 Actualizar estado del inmueble
  └── «include» CU-04 Generar reportes de cambios

CU-05 Administrar inmuebles
  ├── «include» CU-06 Registrar edificios
  └── «include» CU-07 Registrar departamentos, suites, estudios y locales

CU-09 Realizar reserva o agenda
  └── «include» CU-10 Gestionar notificaciones y recordatorios
```

---

## 5. Resumen de Actores por Caso de Uso

| Caso de Uso | Actor |
|---|---|
| Mantener catálogo del condominio | Administrador |
| Actualizar estado del inmueble | Administrador |
| Administrar inmuebles | Administrador |
| Gestionar propiedades de cada propietario | Propietario |
| Realizar reserva o agenda | Usuario |
