# Gestión De Alquileres De Maquinaria En Obra: MaquiRent Pro

Sistema de gestión de maquinaria alquilada a terceros desarrollado como aplicación web autónoma (HTML + JavaScript + SQLite en navegador).

Permite controlar proveedores, maquinaria, alquileres, obras, documentación técnica y costes asociados, todo desde una única interfaz sin necesidad de instalar software adicional ni disponer de servidor.

---

## 📋 Características principales

### 🚜 Gestión de maquinaria

- Alta y edición de equipos alquilados.
- Registro de:
  - Identificador o matrícula.
  - Empresa alquiladora.
  - Modelo y marca.
  - Número de serie.
  - Coste diario.
- Estado de cada equipo:
  - En catálogo.
  - Alquilado.
  - Devuelto.
  - Dado de baja.

### 🏢 Gestión de proveedores

- Registro de empresas de alquiler.
- Almacenamiento de:
  - CIF/NIF.
  - Persona de contacto.
  - Teléfono.
  - Email.
  - Notas comerciales.
- Resumen de maquinaria asociada.
- Cálculo de gasto diario activo por proveedor.

### 🏗 Gestión de obras y proyectos

- Catálogo de obras.
- Dirección y ubicación asociada.
- Relación automática con alquileres activos.
- Actualización masiva del nombre de una obra en todos los registros asociados.

### 📦 Control de entradas y devoluciones

- Registro de entrada de maquinaria en obra.
- Control de fecha de recepción.
- Fecha prevista de devolución.
- Fecha real de devolución.
- Cálculo automático de:
  - Días de alquiler.
  - Coste acumulado.
  - Coste total final.

### 📊 Auditoría mensual

Vista tipo calendario/Gantt que permite:

- Ver qué maquinaria estuvo activa cada día del mes.
- Identificar periodos de alquiler.
- Calcular gasto mensual por equipo.
- Analizar permanencias en obra.

### 📁 Gestión documental

Cada máquina puede almacenar:

#### Fotografías

- Múltiples imágenes.
- Compresión automática.
- Galería integrada.
- Visualizador ampliado.

#### Documentación PDF

- Contratos.
- Fichas técnicas.
- Certificados.
- Manuales.

Los documentos pueden visualizarse directamente dentro de la aplicación.

### 💾 Base de datos SQLite integrada

La aplicación utiliza:

- SQLite ejecutado en el navegador mediante SQL.js.
- Persistencia local mediante IndexedDB.
- Exportación directa a archivo:

```text
.sqlite
```

- Importación de bases de datos existentes.

No requiere servidor ni backend.

---

## 🧱 Tecnologías utilizadas

### Frontend

- HTML5
- JavaScript Vanilla
- Tailwind CSS

### Componentes externos

- TailwindCSS
- Lucide Icons
- SQL.js (SQLite WebAssembly)

### Almacenamiento

- SQLite
- IndexedDB

---

## 📂 Estructura de datos

La aplicación utiliza cuatro tablas principales:

### providers

Información de empresas alquiladoras.

| Campo | Descripción |
|---------|---------|
| id | Identificador |
| name | Nombre empresa |
| cif | CIF/NIF |
| phone | Teléfono |
| contact | Persona contacto |
| email | Email |
| notes | Observaciones |

### machines

Información de maquinaria.

| Campo | Descripción |
|---------|---------|
| id | Identificador |
| provider | Empresa |
| name | Nombre |
| model | Modelo |
| serial | Nº serie |
| rate | Coste diario |
| status | Estado |
| specs | Ficha técnica |
| photos | Fotografías |
| pdfs | Documentación |

### rentals

Histórico de alquileres.

| Campo | Descripción |
|---------|---------|
| id | Identificador |
| machineId | Máquina |
| site | Obra |
| startDate | Fecha entrada |
| endDate | Fecha devolución |
| rate | Coste diario |
| status | Estado |
| totalCost | Coste total |

### sites

Catálogo de obras.

| Campo | Descripción |
|---------|---------|
| id | Identificador |
| name | Nombre obra |
| address | Dirección |

---

## 🚀 Puesta en marcha

### Ejecución directa en navegador

Simplemente abrir:

```text
gestion_de_alquiler_de_maquinaria.html
```

en cualquier navegador moderno.

---

## 📈 Indicadores disponibles

La pantalla principal muestra:

- Equipos actualmente alquilados.
- Proveedores activos.
- Equipos devueltos.
- Coste diario total en curso.

---

## 🔄 Flujo de trabajo recomendado

### 1. Crear proveedores

Registrar las empresas de alquiler.

### 2. Registrar maquinaria

Crear fichas técnicas completas de los equipos.

### 3. Crear obras

Añadir los proyectos donde trabajará la maquinaria.

### 4. Registrar entradas

Asignar maquinaria a una obra.

### 5. Registrar devoluciones

Cerrar alquileres y obtener el coste real.

### 6. Auditar

Revisar mensualmente permanencias y gastos.

---

## ✅ Ventajas

- Aplicación completamente local.
- No requiere instalación.
- Sin dependencias de servidor.
- Exportación e importación de SQLite.
- Interfaz responsive.
- Gestión documental integrada.
- Historial completo de alquileres.
- Seguimiento económico automático.

---

## 📄 Licencia

GPL 3.0

---

## 👨‍💻 Autor

Julio Sánchez Berro

Desarrollado para la gestión operativa y económica de maquinaria alquilada a terceros en obras y proyectos de construcción.
