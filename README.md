# 🤖 **Proyecto_IA_Nivel1_EstebanEstebanSahiamValentina**
**Proyecto_IA_Nivel1_NavasAlvearAndresFelipe**

AgendaBot es un bot conversacional automatizado diseñado para la gestión de **citas, tareas, recordatorios, hábitos y listas**, utilizando únicamente herramientas gratuitas y accesibles.
Este documento describe su funcionamiento, estructura, flujos y reglas internas.

---

## 1. Descripción General

AgendaBot funciona a través de Telegram y permite al usuario interactuar mediante **menús numéricos**, sin necesidad de comandos complejos.
El bot guía al usuario paso a paso, explicando cada acción y solicitando confirmación antes de realizar cambios importantes.

El sistema fue diseñado para ser:
- Fácil de usar
- Predecible
- Controlado por el usuario
- Libre de dependencias de pago

---

## 2. Arquitectura del Sistema

### 2.1 Telegram
- Interfaz conversacional
- Envío y recepción de mensajes

### 2.2 n8n & NGROK
- Automatización de flujos
- Validaciones
- Control de sesiones

### 2.3 Google Sheets
- Almacenamiento de datos
- Logs y auditoría

---

## 3. Principios Conversacionales

- El usuario siempre elige escribiendo un número
- El bot nunca asume intención
- Siempre hay opción de cancelar o volver

---

## 4. Menú Principal

0. Ayuda  
1. Agenda  
2. Tareas  
3. Recordatorios  
4. Hábitos  
5. Listas  
6. Reportes  
7. Configuración  
8. Administrador  


---

## 6. Modelo de Datos

Incluye hojas para citas, tareas, hábitos, listas, usuarios, logs y sesiones.

---

## 7. Automatizaciones

- Router principal
- Flujos guiados
- Resumen diario
- Logs automáticos

---

## 8. Validaciones

- Fechas válidas
- Opciones correctas
- Control de permisos

---

## 9. Estado del Proyecto

Proyecto funcional y en crecimiento.
