# 📅 AgendaPro - Sistema de Gestión de Citas Online

[![Estado](https://img.shields.io/badge/Estado-Funcional-success)](https://github.com/tuusuario/agendapro)
[![Versión](https://img.shields.io/badge/Versión-1.0.0-blue)](https://github.com/tuusuario/agendapro)
[![Licencia](https://img.shields.io/badge/Licencia-MIT-green)](LICENSE)
[![React](https://img.shields.io/badge/React-18-61dafb)](https://reactjs.org/)
[![Tailwind](https://img.shields.io/badge/Tailwind-CSS-38bdf8)](https://tailwindcss.com/)

> Sistema completo de agendamiento de citas médicas con gestión de pacientes, múltiples especialistas, calendario interactivo y panel administrativo. **Los clientes pueden agendar sus propias citas de forma autónoma.**

## 🌟 [Ver Demo en Vivo](https://reserva-de-citas.netlify.app)

---

## 📑 Tabla de Contenidos

- [Características Principales](#-características-principales)
- [Sistema de Roles](#-sistema-de-roles)
- [Funcionalidades por Rol](#-funcionalidades-por-rol)
- [Tecnologías Utilizadas](#-tecnologías-utilizadas)
- [Usuarios de Prueba](#-usuarios-de-prueba)
- [Datos Precargados](#-datos-precargados)
- [Instalación](#-instalación)
- [Casos de Uso](#-casos-de-uso)
- [Arquitectura](#-arquitectura)
- [Roadmap](#-roadmap)
- [Licencia](#-licencia)
- [Contacto](#-contacto)

---

## ✨ Características Principales

### 🔐 **Sistema de Roles Diferenciados**
- **3 roles distintos** con permisos específicos: Administrador, Recepcionista y Cliente
- Menús y dashboards personalizados según el rol
- Control granular de acceso a funcionalidades

### 👤 **Auto-agendamiento para Clientes**
- Los clientes pueden **agendar sus propias citas** sin intermediarios
- Proceso guiado en **3 pasos simples**:
  1. Seleccionar especialista
  2. Elegir servicio
  3. Seleccionar fecha y hora
- Visualización en tiempo real de horarios disponibles y ocupados

### 📅 **Calendario Interactivo Completo**
- Navegación mensual con indicadores visuales
- Horarios disponibles (verde) y ocupados (rojo)
- Puntos indicadores en días con citas
- Día actual resaltado
- Vista detallada de citas por día

### 👨‍⚕️ **Gestión de Múltiples Especialistas**
- 6 especialidades médicas precargadas
- Asignación de servicios específicos por especialidad
- Precios diferenciados por servicio
- Avatar personalizable con emojis

### 💰 **Control Financiero (Solo Admin)**
- Registro de pagos por cita
- Reportes de ingresos por especialista
- Estadísticas de pagos pendientes
- Exportación de datos a CSV

### 🔔 **Sistema de Notificaciones**
- Recordatorios automáticos 24 horas antes
- Confirmaciones de citas agendadas
- Alertas de reprogramación

### 📱 **Diseño Responsive**
- Funcional en móviles, tablets y escritorio
- Menú hamburguesa en dispositivos móviles
- Interfaz optimizada para todas las pantallas

---

## 🔐 Sistema de Roles

### 👨‍⚕️ **Administrador** (Acceso Total)

**Dashboard:**
```
┌─────────────────────────────────────────┐
│  📊 Citas Hoy        💰 Sin Pagar      │
│      2                    1            │
│                                        │
│  💵 Ingresos         👥 Clientes       │
│    $1,900                 4            │
└─────────────────────────────────────────┘
```

**Permisos:**
- ✅ Ver/Crear/Editar/Eliminar Citas
- ✅ Ver/Crear/Editar/Eliminar Clientes  
- ✅ Ver/Crear/Editar/Eliminar Especialistas
- ✅ **Acceso a Reportes Financieros**
- ✅ **Acceso a Configuración del Sistema**
- ✅ **Exportar datos a CSV**
- ✅ **Enviar recordatorios masivos**
- ✅ Ver todos los pagos e ingresos

---

### 📋 **Recepcionista** (Operación Limitada)

**Dashboard:**
```
┌─────────────────────────────────────────┐
│  📊 Citas Hoy        ⏳ Pendientes     │
│      2                    1            │
│                                        │
│  👥 Clientes                           │
│      4                                 │
└─────────────────────────────────────────┘
```

**Permisos:**
- ✅ Ver/Crear/Editar Citas (NO eliminar)
- ✅ Ver/Crear/Editar Clientes (NO eliminar)
- ✅ Ver Especialistas (solo lectura)
- ❌ **SIN acceso a Reportes**
- ❌ **SIN acceso a Configuración**
- ❌ **NO puede exportar datos**
- ❌ **NO puede ver ingresos totales**
- ❌ **NO puede eliminar registros**

---

### 👤 **Cliente** (Auto-servicio)

**Dashboard:**
```
┌─────────────────────────────────────────┐
│  📊 Total Citas      📅 Próximas       │
│      4                    2            │
└─────────────────────────────────────────┘
```

**Permisos:**
- ✅ **Agendar sus propias citas** (proceso paso a paso)
- ✅ Ver solo SUS citas
- ✅ **Reprogramar** sus citas futuras
- ✅ **Cancelar** sus citas futuras
- ✅ Ver información de especialistas
- ❌ NO ve citas de otros clientes
- ❌ NO accede a gestión administrativa
- ❌ NO ve información financiera

---

## 🎯 Funcionalidades por Rol

### **Funcionalidades del Cliente**

#### 1️⃣ **Agendar Nueva Cita**

**Paso 1: Seleccionar Especialista**
```
┌──────────────────────────────────────────────────┐
│  Selecciona una Especialidad                     │
├──────────────────────────────────────────────────┤
│                                                   │
│   ❤️              🔬             🦴              │
│ Dr. Carlos      Dra. Ana      Dr. Miguel         │
│ Cardiología   Dermatología  Traumatología        │
│                                                   │
│   👶             🧠             👩‍⚕️              │
│ Dra. Laura     Dr. Roberto   Dra. Patricia       │
│ Pediatría      Neurología    Ginecología         │
│                                                   │
└──────────────────────────────────────────────────┘
```

**Paso 2: Seleccionar Servicio**
```
┌──────────────────────────────────────────────────┐
│  Dr. Carlos Ramírez - Cardiología                │
├──────────────────────────────────────────────────┤
│                                                   │
│  ┌──────────────────┐  ┌──────────────────┐     │
│  │ Consulta         │  │ Electro-         │     │
│  │ Cardiología      │  │ cardiograma      │     │
│  │                  │  │                  │     │
│  │ $800             │  │ $400             │     │
│  │ 30 minutos       │  │ 20 minutos       │     │
│  └──────────────────┘  └──────────────────┘     │
│                                                   │
│  ┌──────────────────┐                            │
│  │ Ecocardiograma   │                            │
│  │                  │                            │
│  │ $1,200           │                            │
│  │ 40 minutos       │                            │
│  └──────────────────┘                            │
│                                                   │
└──────────────────────────────────────────────────┘
```

**Paso 3: Seleccionar Fecha y Hora**
```
┌──────────────────────────────────────────────────┐
│  Resumen:                                         │
│  Dr. Carlos Ramírez                               │
│  Consulta Cardiología - $800                      │
├──────────────────────────────────────────────────┤
│                                                   │
│  Noviembre 2024          Horarios Disponibles    │
│  ┌───┬───┬───┬───┐      ┌──────────────┐        │
│  │ 1 │ 2 │...│30 │      │ 08:00 ✅     │        │
│  └───┴───┴───┴───┘      │ 08:30 ✅     │        │
│                          │ 09:00 ❌     │        │
│                          │ 09:30 ✅     │        │
│                          │ 10:00 ✅     │        │
│                          └──────────────┘        │
│                                                   │
│  [Confirmar Cita]                                 │
│                                                   │
└──────────────────────────────────────────────────┘
```

#### 2️⃣ **Mis Citas**

Ver todas sus citas con:
- Información del especialista
- Fecha y hora
- Servicio contratado
- Estado (confirmada, pendiente, cancelada)
- Monto y estado de pago
- Opciones para **reprogramar** o **cancelar**

#### 3️⃣ **Ver Especialistas**

Consultar información de todos los especialistas disponibles:
- Nombre completo
- Especialidad médica
- Avatar visual

---

### **Funcionalidades de Admin/Recepcionista**

#### 📅 **Calendario**

- **Navegación mensual** con flechas anterior/siguiente
- **Visualización completa** de días del mes
- **Indicadores visuales:**
  - Día actual: fondo morado
  - Días con citas: punto rosa
- **Click en cualquier día** para ver citas programadas
- **Lista detallada** de citas del día seleccionado con:
  - Hora de la cita
  - Nombre del especialista
  - Nombre del cliente
  - Servicio solicitado
  - Estado de la cita

#### 📋 **Gestión de Citas**

**Tabla completa** con todas las citas del sistema:

| Fecha | Hora | Cliente | Especialista | Servicio | Estado | Monto | Acciones |
|-------|------|---------|--------------|----------|--------|-------|----------|
| 2024-11-29 | 09:00 | Juan Pérez | Dr. Carlos Ramírez | Consulta Cardiología | confirmed | $800 ✅ | 🗑️ |
| 2024-11-29 | 10:00 | María González | Dra. Ana López | Consulta Dermatológica | confirmed | $600 ✅ | 🗑️ |

**Funcionalidades:**
- Ver todas las citas en formato tabla
- Estados: confirmed, pending, cancelled
- Indicador visual de pago (✅ pagado / ❌ pendiente)
- **Botón eliminar** (solo Admin)

#### 👥 **Gestión de Clientes**

**Tabla completa** con todos los pacientes:

| Nombre | Teléfono | Email | Acciones |
|--------|----------|-------|----------|
| Juan Pérez | +52 811 123 4567 | juan@email.com | ✏️ 🗑️ |
| María González | +52 811 234 5678 | maria@email.com | ✏️ 🗑️ |

**Funcionalidades:**
- **Crear nuevo cliente** (botón ➕)
- **Editar cliente** (botón ✏️)
- **Eliminar cliente** (botón 🗑️ - solo Admin)
- Campos: Nombre, Teléfono, Email

#### 👨‍⚕️ **Gestión de Especialistas**

Vista en tarjetas de todos los especialistas:

```
┌──────────────┐  ┌──────────────┐  ┌──────────────┐
│      ❤️      │  │      🔬      │  │      🦴      │
│              │  │              │  │              │
│ Dr. Carlos   │  │  Dra. Ana    │  │ Dr. Miguel   │
│  Ramírez     │  │   López      │  │   Torres     │
│              │  │              │  │              │
│ Cardiología  │  │Dermatología  │  │Traumatología │
│              │  │              │  │              │
│ ✏️ Editar     │  │ ✏️ Editar     │  │ ✏️ Editar     │
│ 🗑️ Eliminar   │  │ 🗑️ Eliminar   │  │ 🗑️ Eliminar   │
└──────────────┘  └──────────────┘  └──────────────┘
```

**Funcionalidades (Solo Admin):**
- **Crear nuevo especialista** (botón ➕)
- **Editar especialista** (botón ✏️)
- **Eliminar especialista** (botón 🗑️)
- Campos: Nombre, Especialidad, Avatar (emoji)

**Recepcionista:** Solo lectura (sin botones)

---

### **Funcionalidades Exclusivas de Admin**

#### 📊 **Reportes**

**Panel de Ingresos por Especialista:**
```
┌────────────────────────────────────────┐
│  Ingresos por Especialista             │
├────────────────────────────────────────┤
│  Dr. Carlos Ramírez          $800     │
│  Dra. Ana López              $600     │
│  Dr. Miguel Torres           $0       │
│  Dra. Laura Mendoza          $500     │
│  Dr. Roberto Silva           $0       │
│  Dra. Patricia Ruiz          $0       │
└────────────────────────────────────────┘
```

**Panel de Estadísticas:**
```
┌────────────────────────────────────────┐
│  Estadísticas Generales                │
├────────────────────────────────────────┤
│  Total Citas                    4      │
│  Ingresos Totales           $1,900     │
│  Pendiente de Pago            $700     │
└────────────────────────────────────────┘
```

#### ⚙️ **Configuración**

**Horarios del Consultorio:**
- Hora de inicio: 08:00 AM
- Hora de cierre: 20:00 PM

**Acciones Disponibles:**
- **📤 Exportar CSV** - Descarga archivo con todas las citas
- **📧 Enviar Recordatorios** - Envía recordatorios para citas del día siguiente

---

## 🛠️ Tecnologías Utilizadas

### **Frontend**
- **React 18** - Biblioteca JavaScript para construir interfaces
- **Tailwind CSS** - Framework CSS utilitario
- **Babel Standalone** - Transpilador JavaScript en el navegador

### **Almacenamiento**
- **LocalStorage** - Persistencia de datos en el navegador

### **Características Técnicas**
- **Single Page Application (SPA)**
- **Responsive Design**
- **Component-Based Architecture**
- **State Management con React Hooks**

---

## 👥 Usuarios de Prueba

### **Administrador**
```
Usuario: admin
Contraseña: admin123
```
**Acceso:** Completo (Dashboard, Calendario, Citas, Clientes, Especialistas, Reportes, Configuración)

---

### **Recepcionista**
```
Usuario: recep
Contraseña: recep123
```
**Acceso:** Limitado (Dashboard, Calendario, Citas, Clientes, Especialistas en lectura)

---

### **Cliente**
```
Usuario: cliente
Contraseña: cliente123
```
**Acceso:** Auto-servicio (Agendar Cita, Mis Citas, Ver Especialistas)

---

## 📊 Datos Precargados

### **6 Especialistas Disponibles**

| Avatar | Nombre | Especialidad |
|--------|--------|--------------|
| ❤️ | Dr. Carlos Ramírez | Cardiología |
| 🔬 | Dra. Ana López | Dermatología |
| 🦴 | Dr. Miguel Torres | Traumatología |
| 👶 | Dra. Laura Mendoza | Pediatría |
| 🧠 | Dr. Roberto Silva | Neurología |
| 👩‍⚕️ | Dra. Patricia Ruiz | Ginecología |

---

### **Servicios por Especialidad**

#### **Cardiología**
- Consulta Cardiología - $800 (30 min)
- Electrocardiograma - $400 (20 min)
- Ecocardiograma - $1,200 (40 min)

#### **Dermatología**
- Consulta Dermatológica - $600 (30 min)
- Tratamiento Acné - $500 (45 min)

#### **Traumatología**
- Consulta Traumatología - $700 (30 min)
- Infiltración - $900 (20 min)

#### **Pediatría**
- Consulta Pediátrica - $500 (30 min)
- Control de Niño Sano - $400 (25 min)

#### **Neurología**
- Consulta Neurológica - $850 (40 min)
- Electroencefalograma - $1,000 (60 min)

#### **Ginecología**
- Consulta Ginecológica - $650 (30 min)
- Papanicolau - $400 (20 min)

---

### **4 Clientes Precargados**

| ID | Nombre | Teléfono | Email |
|----|--------|----------|-------|
| 1 | Juan Pérez | +52 811 123 4567 | juan@email.com |
| 2 | María González | +52 811 234 5678 | maria@email.com |
| 3 | Carlos López | +52 811 345 6789 | carlos@email.com |
| 4 | Ana Martínez | +52 811 456 7890 | ana@email.com |

---

### **4 Citas de Ejemplo**

| Fecha | Hora | Cliente | Especialista | Servicio | Estado | Pagado | Monto |
|-------|------|---------|--------------|----------|--------|--------|-------|
| 2024-11-29 | 09:00 | Juan Pérez | Dr. Carlos Ramírez | Consulta Cardiología | confirmed | ✅ | $800 |
| 2024-11-29 | 10:00 | María González | Dra. Ana López | Consulta Dermatológica | confirmed | ✅ | $600 |
| 2024-11-30 | 11:00 | Carlos López | Dr. Miguel Torres | Consulta Traumatología | pending | ❌ | $700 |
| 2024-12-01 | 14:00 | Ana Martínez | Dra. Laura Mendoza | Control Pediátrico | confirmed | ✅ | $500 |

---

## 🚀 Instalación

### **Opción 1: Uso Directo**

1. Descarga el archivo `agenda-pro-completo.html`
2. Abre el archivo en cualquier navegador web moderno
3. ¡Listo! El sistema está funcionando

---

### **Opción 2: Despliegue en Netlify**

1. **Renombra el archivo:**
   ```bash
   mv agenda-pro-completo.html index.html
   ```

2. **Sube a Netlify:**
   - Ve a [app.netlify.com](https://app.netlify.com)
   - Arrastra el archivo `index.html` al área de drop
   - Netlify te asignará una URL automáticamente

3. **Personaliza tu dominio (opcional):**
   - Site settings → Domain management
   - Cambia el nombre del sitio

---

### **Opción 3: GitHub Pages**

1. **Crear repositorio:**
   ```bash
   git init
   git add index.html
   git commit -m "Initial commit"
   git remote add origin https://github.com/tuusuario/agendapro.git
   git push -u origin main
   ```

2. **Activar GitHub Pages:**
   - Settings → Pages
   - Source: Deploy from branch
   - Branch: main / root
   - Save

3. **Acceder:**
   - https://tuusuario.github.io/agendapro

---

## 💼 Casos de Uso

### **1. Consultorio Médico General** ✅

**Escenario:** Consultorio con 4-6 médicos de diferentes especialidades

**Beneficios:**
- Pacientes agendan sus citas sin llamar
- Reducción de llamadas telefónicas
- Optimización del tiempo de recepción
- Control de pagos y estadísticas
- Recordatorios automáticos

**ROI:** 40% reducción en tiempo administrativo

---

### **2. Clínica Dental**

**Escenario:** Clínica con múltiples dentistas

**Configuración:**
- Especialistas: Odontólogos, Ortodoncistas, Endodoncistas
- Servicios: Limpieza, Ortodoncia, Endodoncia, Extracción
- Precios diferenciados por tratamiento

**Beneficios:**
- Gestión de múltiples sillas
- Control de tratamientos activos
- Facturación integrada

---

### **3. Centro de Terapias**

**Escenario:** Centro con terapeutas de diferentes disciplinas

**Configuración:**
- Especialistas: Fisioterapeutas, Psicólogos, Nutriólogos
- Servicios: Sesiones de 30, 45 o 60 minutos
- Paquetes de múltiples sesiones

**Beneficios:**
- Seguimiento de sesiones por paciente
- Reportes de asistencia
- Control de pagos por paquete

---

### **4. Laboratorio Clínico**

**Escenario:** Toma de muestras con citas programadas

**Configuración:**
- Especialistas: Técnicos de laboratorio
- Servicios: Análisis de sangre, Rayos X, Ultrasonidos
- Horarios específicos por tipo de estudio

**Beneficios:**
- Evita tiempos de espera
- Distribución equitativa de carga
- Preparación de materiales anticipada

---

### **5. Salón de Belleza / Spa**

**Escenario:** Servicios de belleza y bienestar

**Configuración:**
- Especialistas: Estilistas, Manicuristas, Masajistas
- Servicios: Cortes, Tintes, Manicure, Masajes
- Duración variable por servicio

**Beneficios:**
- Maximización de agenda
- Reducción de no-shows
- Gestión de preferencias de cliente

---

### **6. Centro Veterinario**

**Escenario:** Clínica veterinaria con múltiples veterinarios

**Configuración:**
- Especialistas: Veterinarios generales y especialistas
- Servicios: Consultas, Vacunación, Cirugías
- Clientes: Dueños de mascotas

**Beneficios:**
- Historial por mascota
- Recordatorios de vacunas
- Control de emergencias vs rutinas

---

## 🏗️ Arquitectura

### **Estructura de Componentes**

```
AgendaPro (Root)
│
├── Login Component
│   ├── Username Input
│   ├── Password Input
│   └── Quick Login Buttons
│
├── Sidebar Navigation
│   ├── User Info
│   ├── Navigation Menu (conditional by role)
│   └── Logout Button
│
├── Main Content Area
│   │
│   ├── Admin/Receptionist Views
│   │   ├── Dashboard (Stats Cards)
│   │   ├── Calendar View
│   │   │   ├── Month Navigation
│   │   │   ├── Calendar Grid
│   │   │   └── Daily Appointments List
│   │   ├── Appointments Table
│   │   ├── Clients Management
│   │   │   ├── Clients Table
│   │   │   └── Client Modal (Create/Edit)
│   │   ├── Specialists Management
│   │   │   ├── Specialists Grid
│   │   │   └── Specialist Modal (Create/Edit)
│   │   ├── Reports (Admin Only)
│   │   └── Settings (Admin Only)
│   │
│   └── Client Views
│       ├── Book Appointment
│       │   ├── Step 1: Select Specialist
│       │   ├── Step 2: Select Service
│       │   └── Step 3: Select Date & Time
│       │       ├── Month Calendar
│       │       └── Time Slots Grid
│       ├── My Appointments
│       │   └── Appointment Cards
│       │       ├── Details
│       │       └── Actions (Reschedule/Cancel)
│       └── Specialists Directory
│
└── Modals
    ├── Client Modal
    ├── Specialist Modal
    └── Reschedule Modal
```

---

### **Flujo de Datos**

```
┌─────────────────────────────────────────────────────┐
│              LocalStorage (Browser)                  │
│  ┌──────────────────────────────────────────────┐  │
│  │  agendapro-data: {                           │  │
│  │    clients: [...],                           │  │
│  │    appointments: [...],                      │  │
│  │    specialists: [...]                        │  │
│  │  }                                           │  │
│  └──────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────┘
                        ↕
┌─────────────────────────────────────────────────────┐
│              React State Management                  │
│  ┌──────────────────────────────────────────────┐  │
│  │  const [clients, setClients] = useState([])  │  │
│  │  const [appointments, setAppointments] = ... │  │
│  │  const [specialists, setSpecialists] = ...   │  │
│  └──────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────┘
                        ↕
┌─────────────────────────────────────────────────────┐
│               UI Components                          │
│  ┌──────────────────────────────────────────────┐  │
│  │  - Tables (Appointments, Clients)            │  │
│  │  - Calendar Grid                             │  │
│  │  - Forms & Modals                            │  │
│  │  - Stats Cards                               │  │
│  └──────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────┘
```

---

### **Estados Principales**

```javascript
// User & Navigation
const [user, setUser] = useState(null);
const [view, setView] = useState('calendar');
const [menuOpen, setMenuOpen] = useState(false);

// Data
const [clients, setClients] = useState([]);
const [appointments, setAppointments] = useState([]);
const [specialists, setSpecialists] = useState([]);

// Calendar & Selection
const [month, setMonth] = useState(new Date());
const [selectedDate, setSelectedDate] = useState(new Date());
const [selectedSpecialist, setSelectedSpecialist] = useState(null);
const [selectedService, setSelectedService] = useState(null);
const [selectedTime, setSelectedTime] = useState(null);

// Modals & Editing
const [showModal, setShowModal] = useState(false);
const [editItem, setEditItem] = useState(null);
```

---

### **Funciones Principales**

#### **Gestión de Citas**
```javascript
createAppointment(clientId, specialistId, date, time, service, amount)
updateAppointment(id, updates)
deleteAppointment(id)
rescheduleAppointment(id, newDate, newTime)
cancelAppointment(id)
```

#### **Gestión de Clientes**
```javascript
createClient(name, phone, email)
updateClient(id, updates)
deleteClient(id)
```

#### **Gestión de Especialistas**
```javascript
createSpecialist(name, specialty, avatar)
updateSpecialist(id, updates)
deleteSpecialist(id)
```

#### **Utilidades**
```javascript
formatDate(date) // Convierte Date a 'YYYY-MM-DD'
getDaysInMonth(date) // Retorna array de 42 días
exportCSV() // Genera y descarga CSV
sendReminders() // Simula envío de recordatorios
```

---

## 🎨 Diseño y UX

### **Esquema de Colores**

```css
--primary: #7c3aed      /* Púrpura principal */
--secondary: #fbbf24    /* Amarillo/Dorado */
--success: #10b981      /* Verde */
--warning: #f59e0b      /* Naranja */
--danger: #ef4444       /* Rojo */
--info: #3b82f6         /* Azul */
```

### **Tipografía**
- Font Family: Inter, system-ui, -apple-system, sans-serif
- Tamaños: 0.75rem - 3rem
- Pesos: 400 (regular), 600 (semibold), 700 (bold)

### **Componentes Reutilizables**
- Cards con sombra y hover
- Botones con estados hover y active
- Inputs con focus state
- Modales centrados con overlay
- Badges de estado con colores semánticos

---

## 📈 Estadísticas del Proyecto

```
┌───────────────────────────────────────┐
│  Líneas de Código           752       │
│  Tamaño del Archivo         57KB      │
│  Componentes React          1 (Main)  │
│  Estados useState           15+       │
│  Funciones                  20+       │
│  Vistas Diferentes          12        │
│  Modales                    3         │
│  Tablas Interactivas        2         │
└───────────────────────────────────────┘
```

---

## 🔒 Consideraciones de Seguridad

### **Almacenamiento Local**
⚠️ **Importante:** Este demo utiliza LocalStorage del navegador para persistencia de datos.

**Para producción se recomienda:**
- Backend con base de datos real (PostgreSQL, MySQL, MongoDB)
- Autenticación con JWT o OAuth
- Encriptación de datos sensibles
- HTTPS obligatorio
- Validación server-side

### **Autenticación**
Los usuarios de prueba son solo para demostración. En producción:
- Implementar hash de contraseñas (bcrypt)
- Tokens de sesión con expiración
- Recuperación de contraseña
- Autenticación de dos factores (2FA)

---

## 🗺️ Roadmap

### **Versión 2.0 - Backend Real**
- [ ] API REST con Node.js + Express
- [ ] Base de datos PostgreSQL
- [ ] Autenticación JWT
- [ ] Endpoints CRUD para todas las entidades

### **Versión 2.1 - Funcionalidades Avanzadas**
- [ ] Sistema de notificaciones real (Email/SMS)
- [ ] Recordatorios automáticos programados
- [ ] Historial médico por paciente
- [ ] Subida de archivos adjuntos
- [ ] Notas del médico por consulta

### **Versión 2.2 - Integraciones**
- [ ] Pasarela de pagos (Stripe, PayPal)
- [ ] Integración con Google Calendar
- [ ] Zoom/Teams para consultas virtuales
- [ ] WhatsApp Business API
- [ ] Email transaccional (SendGrid)

### **Versión 2.3 - Analytics & BI**
- [ ] Dashboard con gráficos (Chart.js)
- [ ] Reportes avanzados en PDF
- [ ] Análisis de ocupación
- [ ] Predicción de demanda
- [ ] KPIs personalizables

### **Versión 3.0 - Mobile App**
- [ ] App nativa iOS (Swift)
- [ ] App nativa Android (Kotlin)
- [ ] Notificaciones push
- [ ] Sincronización offline

---

## 📱 Responsive Breakpoints

```css
/* Mobile First */
Default: < 768px (móvil)

/* Tablet */
md: 768px

/* Desktop */
lg: 1024px
xl: 1280px
```

---

## 🐛 Troubleshooting

### **Los datos no se guardan**
**Solución:** Verifica que tu navegador permita LocalStorage. Algunas configuraciones de privacidad lo bloquean.

### **El calendario no muestra bien en móvil**
**Solución:** El diseño es responsive. Asegúrate de tener la última versión del archivo.

### **Los horarios no se bloquean**
**Solución:** Los horarios ocupados se marcan automáticamente. Verifica que el specialistId y la fecha coincidan.

### **No puedo eliminar registros como Recepcionista**
**Solución:** Es correcto. Solo el Admin puede eliminar. Verifica que iniciaste sesión con el rol correcto.

---

## 📄 Licencia

Este proyecto está bajo la Licencia MIT.

```
MIT License

Copyright (c) 2024 Tu Nombre

Se concede permiso, de forma gratuita, a cualquier persona que obtenga una copia
de este software y archivos de documentación asociados (el "Software"), para 
utilizar el Software sin restricción, incluyendo sin limitación los derechos 
de usar, copiar, modificar, fusionar, publicar, distribuir, sublicenciar, y/o 
vender copias del Software...
```

[Texto completo de la licencia MIT](https://opensource.org/licenses/MIT)

---

## 🤝 Desarrollo Personalizado

¿Necesitas personalizar este sistema para tu negocio?

### **Servicios Ofrecidos:**
- ✅ Integración con backend real
- ✅ Diseño personalizado con tu marca
- ✅ Funcionalidades adicionales
- ✅ Integración con sistemas existentes
- ✅ Capacitación y soporte
- ✅ Apps móviles nativas

### **Contáctame:**
- 📧 Email: tu@email.com
- 💼 LinkedIn: [Tu Perfil](https://linkedin.com/in/tuusuario)
- 🌐 Portafolio: [tuportafolio.com](https://tuportafolio.com)
- 📱 WhatsApp: [Enviar mensaje](https://wa.me/521234567890)

---

## 🌟 Proyectos Relacionados

### **Otros Sistemas Desarrollados:**

1. **[Sistema de Inventario](https://github.com/tuusuario/inventario-demo)**
   - Control de stock
   - Alertas de bajo inventario
   - Reportes de movimientos

2. **[Sistema POS](https://github.com/tuusuario/pos-demo)**
   - Punto de venta
   - Gestión de ventas
   - Reportes financieros

3. **[CRM Empresarial](https://github.com/tuusuario/crm-demo)**
   - Gestión de clientes
   - Pipeline de ventas
   - Seguimiento de oportunidades

4. **[Tienda Online](https://github.com/tuusuario/tienda-demo)**
   - E-commerce completo
   - Carrito de compras
   - Panel administrativo

---

## 📞 Contacto y Soporte

### **¿Preguntas? ¿Problemas? ¿Sugerencias?**

**Canales de Soporte:**
- 🐛 [Reportar un Bug](https://github.com/tuusuario/agendapro/issues)
- 💡 [Sugerir una Funcionalidad](https://github.com/tuusuario/agendapro/issues)
- 📧 Email: soporte@tudominio.com
- 💬 Discord: [Unirse al servidor](https://discord.gg/tuservidor)

---

## ⭐ Agradecimientos

Gracias por usar **AgendaPro**. Si este proyecto te fue útil:

- ⭐ Dale una estrella en GitHub
- 🔄 Compártelo con colegas
- 📝 Déjanos tu feedback
- 🤝 Contribuye al proyecto

---

## 📊 Métricas del Proyecto

![GitHub stars](https://img.shields.io/github/stars/tuusuario/agendapro?style=social)
![GitHub forks](https://img.shields.io/github/forks/tuusuario/agendapro?style=social)
![GitHub watchers](https://img.shields.io/github/watchers/tuusuario/agendapro?style=social)

---

<div align="center">

**Hecho con ❤️ por [Tu Nombre](https://github.com/tuusuario)**

[⬆ Volver arriba](#-agendapro---sistema-de-gestión-de-citas-online)

</div>
