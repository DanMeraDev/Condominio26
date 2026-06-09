# Módulo GRC - Gestión de Inmuebles

## Índice

1. [Gestionar Propiedades](#1-gestionar-propiedades)
2. [Mantener Catálogo del Condominio](#2-mantener-catálogo-del-condominio)
3. [Gestionar Características del Condominio](#3-gestionar-características-del-condominio)
4. [Actualizar Estado del Inmueble](#4-actualizar-estado-del-inmueble)
5. [Generar Reportes de Cambios](#5-generar-reportes-de-cambios)
6. [Gestionar Casos Fortuitos](#6-gestionar-casos-fortuitos)

---

# 1. Gestionar Propiedades

## Descripción

El sistema permitirá consultar las propiedades que pertenecen a un propietario, verificar si se encuentran en alquiler o no y conocer los residentes asociados a cada inmueble.

## Datos del Caso de Uso

| Elemento | Descripción |
|-----------|------------|
| **Actor** | Administrador, Propietario |
| **Entradas** | Número de cédula del propietario |
| **Salidas** | Listado de propiedades y mensaje |

## Escenario Básico

1. El caso de uso inicia cuando el Administrador o Propietario selecciona la opción **Gestionar Propiedades**.
2. El Sistema solicita el número de cédula del propietario.
3. El actor ingresa el número de cédula.
4. El Sistema valida el formato de la cédula.
5. Si la cédula es válida, el Sistema busca la información del propietario.
6. El Sistema recupera todas las propiedades asociadas al propietario.
7. El Sistema consulta el estado de cada propiedad.
8. El Sistema determina si la propiedad se encuentra en alquiler o no.
9. El Sistema consulta los residentes asociados a cada propiedad.
10. El Sistema muestra:
    - Tipo de inmueble.
    - Estado del inmueble.
    - Situación de alquiler.
    - Residentes registrados.
11. El caso de uso termina mostrando la información y el mensaje:

> Consulta realizada correctamente.

## Escenarios Alternos

### Escenario Alterno 1: Cédula inválida

1. El Sistema valida la cédula.
2. Si la cédula tiene formato incorrecto, el Sistema emite el mensaje:

> Número de cédula inválido.

3. El caso de uso termina.

### Escenario Alterno 2: Propietario no registrado

1. El Sistema busca el propietario.
2. Si el propietario no existe, el Sistema emite el mensaje:

> Propietario no registrado.

3. El caso de uso termina.

---

# 2. Mantener Catálogo del Condominio

## Descripción

El sistema permitirá mantener actualizado el catálogo de inmuebles y parqueaderos disponibles para alquiler o venta dentro del condominio.

## Datos del Caso de Uso

| Elemento | Descripción |
|-----------|------------|
| **Actor** | Administrador, Presidente |
| **Entradas** | Tipo de inmueble, Estado del inmueble, Información del parqueadero |
| **Salidas** | Catálogo actualizado, Mensaje |

## Escenario Básico

1. El actor selecciona la opción **Mantener Catálogo**.
2. El Sistema muestra el catálogo actual.
3. El actor registra, modifica o elimina información del catálogo.
4. El Sistema valida la información ingresada.
5. El Sistema actualiza el catálogo.
6. El Sistema registra:
   - Departamentos.
   - Suites.
   - Estudios.
   - Locales comerciales.
   - Parqueaderos.
7. El Sistema actualiza la disponibilidad para alquiler o venta.
8. El caso de uso termina con el mensaje:

> Catálogo actualizado correctamente.

## Escenarios Alternos

### Escenario Alterno 1: Información inválida

1. El Sistema detecta información inválida.
2. El Sistema emite el mensaje:

> Información inválida para actualizar el catálogo.

3. El caso de uso termina.

---

# 3. Gestionar Características del Condominio

## Descripción

El sistema permitirá administrar las características físicas de los inmuebles del condominio.

## Datos del Caso de Uso

| Elemento | Descripción |
|-----------|------------|
| **Actor** | Administrador, Presidente |
| **Entradas** | Metros cuadrados, Número de habitaciones, Número de baños, Número de parqueaderos, Descripción adicional |
| **Salidas** | Mensaje |

## Escenario Básico

1. El actor selecciona la opción **Gestionar Características**.
2. El Sistema solicita la información del inmueble.
3. El actor ingresa los datos.
4. El Sistema valida los datos ingresados.
5. El Sistema registra las características.
6. El caso de uso termina con el mensaje:

> Características registradas correctamente.

## Escenarios Alternos

### Escenario Alterno 1: Datos inválidos

1. Si los datos son inválidos, el Sistema emite el mensaje:

> Información de características inválida.

2. El caso de uso termina.

---

# 4. Actualizar Estado del Inmueble

## Descripción

El sistema permitirá actualizar el estado de un inmueble y registrar los cambios relevantes producidos sobre este.

## Datos del Caso de Uso

| Elemento | Descripción |
|-----------|------------|
| **Actor** | Administrador, Presidente |
| **Entradas** | Código del inmueble, Nuevo estado, Información de residente, Información de remodelación |
| **Salidas** | Mensaje, Registro histórico de cambios |

## Escenario Básico

1. El actor selecciona **Actualizar Estado del Inmueble**.
2. El Sistema solicita el código del inmueble.
3. El actor selecciona el inmueble.
4. El Sistema muestra la información actual.
5. El actor actualiza la información correspondiente.

Los cambios pueden incluir:

- Cambio de residente.
- Remodelaciones realizadas.
- Cambio de estado de ocupación.
- Cambio de disponibilidad.

6. El Sistema valida la información ingresada.
7. El Sistema actualiza la información del inmueble.
8. El Sistema registra automáticamente el cambio en el historial.
9. El Sistema genera el registro correspondiente para futuros reportes.
10. El caso de uso termina con el mensaje:

> Estado actualizado correctamente.

## Escenarios Alternos

### Escenario Alterno 1: Inmueble no encontrado

1. El inmueble no existe.
2. El Sistema emite el mensaje:

> Inmueble no encontrado.

3. El caso de uso termina.

### Escenario Alterno 2: Información inválida

1. La información ingresada es inválida.
2. El Sistema emite el mensaje:

> Información inválida para actualizar el inmueble.

3. El caso de uso termina.

---

# 5. Generar Reportes de Cambios

## Descripción

El sistema permitirá generar reportes históricos de modificaciones realizadas en los inmuebles.

## Datos del Caso de Uso

| Elemento | Descripción |
|-----------|------------|
| **Actor** | Administrador, Presidente |
| **Entradas** | Fecha inicial, Fecha final |
| **Salidas** | Reporte, Mensaje |

## Escenario Básico

1. El actor ingresa la fecha inicial.
2. El actor ingresa la fecha final.
3. El Sistema valida el formato de las fechas.
4. El Sistema consulta el historial de cambios.
5. El Sistema obtiene:
   - Cambios de residentes.
   - Remodelaciones realizadas.
   - Cambios de estado.
   - Modificaciones de disponibilidad.
6. El Sistema genera el reporte.
7. El Sistema muestra el reporte.
8. El caso de uso termina con el mensaje:

> Reporte generado correctamente.

---

# 6. Gestionar Casos Fortuitos

## Descripción

El sistema permitirá registrar eventos inesperados que afecten a los inmuebles o al condominio.

## Datos del Caso de Uso

| Elemento | Descripción |
|-----------|------------|
| **Actor** | Presidente |
| **Entradas** | Tipo de incidente, Descripción, Fecha, Inmueble afectado |
| **Salidas** | Mensaje, Notificaciones |

## Escenario Básico

1. El Presidente selecciona **Gestionar Casos Fortuitos**.
2. El Sistema solicita la información del incidente.
3. El Presidente registra el incidente.
4. El Sistema valida la información.
5. El Sistema registra el caso fortuito.

### Ejemplos de incidentes

- Incendio.
- Inundación.
- Cortes eléctricos.
- Daños estructurales.
- Fugas de agua.
- Desastres naturales.

6. El Sistema genera las notificaciones correspondientes.
7. El caso de uso termina con el mensaje:

> Caso fortuito registrado correctamente.

---