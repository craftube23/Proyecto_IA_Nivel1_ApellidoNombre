# 🤖 AgendaBot

**Proyecto IA Nivel 1**

## 📌 1. Objetivo del Proyecto

Implementar un bot automatizado que permita a los usuarios:

* Agendar y consultar citas
* Gestionar tareas con estados y prioridad
* Crear y recibir recordatorios
* Llevar seguimiento de hábitos
* Administrar listas tipo checklist
* Consultar reportes básicos
* Controlar permisos y usuarios (modo administrador)

Todo lo anterior usando únicamente:

* **Telegram**
* **n8n Community Edition**
* **Google Sheets**

---

## 🛠️ 2. Stack Tecnológico

### Herramientas Utilizadas

* **Telegram**
  Interfaz conversacional con el usuario.

* **n8n Community Edition**
  Motor de automatización y lógica de negocio.

* **Google Sheets**
  Almacenamiento persistente de datos y logs.

### Restricciones Cumplidas

* ❌ No se usa n8n Cloud de pago
* ❌ No se usan APIs que requieran tarjeta de crédito
* ❌ No se usan modelos entrenados, embeddings ni RAG

---

## 💬 3. Enfoque Conversacional

AgendaBot sigue los siguientes principios:

* El usuario **siempre elige escribiendo un número**
* El bot **explica qué hace y qué opciones existen**
* El bot **no asume intención**
* Siempre existe una opción para **volver o cancelar**
* El bot sugiere una opción recomendada cuando aplica

---

## 🧭 4. Menú Principal

```
0. Ayuda
1. Agenda (citas)
2. Tareas
3. Recordatorios
4. Hábitos
5. Listas
6. Reportes
7. Configuración
8. Administrador
```

Mensaje de orientación:

> Tip rápido: escribe solo el número (por ejemplo: 1) y presiona enviar.

---

## ❓ 5. Módulo Ayuda

**Objetivo:** orientar al usuario sobre el uso del bot.

### Menú Ayuda

```
1. Cómo funciona AgendaBot
2. Ejemplos rápidos
3. Reglas y limitaciones
9. Volver al menú principal
```

**Importante:**
Este módulo **no guarda datos**, solo permite navegación informativa.

---

## ✅ 6. Módulo Tareas

**Objetivo:** gestionar tareas con estados y prioridad.

### Menú Tareas

```
1. Crear nueva tarea
2. Ver mis tareas
3. Cambiar estado de una tarea
4. Editar tarea
5. Eliminar tarea
9. Volver al menú principal
```

### Flujo Crear Tarea

1. Título
2. Prioridad (Alta / Media / Baja)
3. Fecha objetivo (opcional)
4. Confirmación

### Estados de Tarea

* Pendiente
* En progreso
* Completada
* Cancelada

**Almacenamiento:**
Google Sheets → Hoja **TAREAS**

---

## ⏰ 7. Módulo Recordatorios

**Objetivo:** enviar avisos automáticos por Telegram.

### Menú Recordatorios

```
1. Crear recordatorio
2. Ver recordatorios activos
3. Editar recordatorio
4. Eliminar recordatorio
9. Volver al menú principal
```

### Flujo Crear Recordatorio

1. Mensaje
2. Fecha
3. Hora
4. Confirmación

**Automatización clave:**
n8n (Cron) → revisión de fecha/hora → envío de mensaje Telegram.

---

## 🔁 8. Módulo Hábitos

**Objetivo:** seguimiento de hábitos recurrentes.

### Menú Hábitos

```
1. Crear hábito
2. Ver mis hábitos
9. Volver al menú principal
```

### Flujo Crear Hábito

1. Nombre
2. Frecuencia (Diario / Semanal / Días específicos)
3. Hora de recordatorio
4. Confirmación

**Almacenamiento:**
Google Sheets → Hoja **HABITOS**

---

## 📝 9. Módulo Listas

**Objetivo:** manejar listas tipo checklist.

### Menú Listas

```
1. Crear nueva lista
2. Ver mis listas
3. Ver items de una lista
4. Agregar item
5. Marcar item como completado
6. Eliminar item
9. Volver al menú principal
```

**Estructura de datos:**

* LISTAS
* ITEMS_LISTA

Tipos comunes:

* Compras
* Pendientes
* Personalizada

---

## 📊 10. Módulo Reportes

**Objetivo:** mostrar información resumida (solo lectura).

### Menú Reportes

```
1. Resumen de hoy
2. Citas de la semana
3. Tareas pendientes
4. Hábitos activos
9. Volver al menú principal
```

📌 Este módulo **no modifica datos**, solo consulta Google Sheets.

---

## ⚙️ 11. Configuración

**Objetivo:** preferencias del usuario.

### Menú Configuración

```
1. Cambiar nombre
9. Volver al menú principal
```

**Almacenamiento:**
Google Sheets → Hoja **USUARIOS**

---

## 🛡️ 12. Módulo Administrador

**Objetivo:** funciones restringidas por rol.

### Menú Administrador

```
1. Ver usuarios
9. Volver al menú principal
```

**Control de acceso:**
Validado por campo **rol** en la hoja USUARIOS.

---

## 🗂️ 13. Modelo de Datos

El documento **AgendaBot_DB** contiene las siguientes hojas:

* CITAS
* TAREAS
* HABITOS
* LISTAS
* ITEMS_LISTA
* USUARIOS
* LOGS
* SESSIONS
* RECORDATORIOS

Incluye control de sesión, navegación, logs y datos parciales.

---

## 🔄 14. Automatizaciones en n8n

* Router principal por pantalla y opción
* Flujos guiados tipo wizard
* Control de sesiones
* Validaciones de datos
* Registro automático de logs
* Envío de recordatorios

---

## ✔️ 15. Estado del Proyecto

* Navegación por menús implementada
* Flujos principales funcionales
* Persistencia en Google Sheets
* Proyecto alineado con los requisitos del curso

---

## 📁 16. Estructura del Repositorio

```
Proyecto_IA_Nivel1_ApellidoNombre/
├── README.md
├── docs/
│   └── AgendaBot.md
├── workflows/
│   └── workflows_n8n.json
└── evidencias/
```

---

**AgendaBot** demuestra cómo es posible crear automatizaciones útiles, conversacionales y estructuradas utilizando únicamente herramientas gratuitas.
