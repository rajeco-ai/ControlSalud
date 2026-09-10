# 🩺 Control Salud

**Panel personal de monitoreo de signos vitales**

Aplicación web ligera y autocontenida para el registro y seguimiento de **presión arterial** y **glicemia (azúcar en sangre)**. Diseñada para uso personal, familiar o educativo, con datos almacenados de forma local en el navegador (sin servidores, sin cuentas, sin publicidad).

---

## 📖 Tabla de contenidos

- [Descripción](#-descripción)
- [Características](#-características)
- [Estructura del proyecto](#-estructura-del-proyecto)
- [Tecnologías utilizadas](#-tecnologías-utilizadas)
- [Uso](#-uso)
- [Instalación y despliegue](#-instalación-y-despliegue)
- [Personalización](#-personalización)
- [Privacidad](#-privacidad)
- [Aviso médico](#-aviso-médico)
- [Autor](#-autor)
- [Licencia](#-licencia)

---

## 📝 Descripción

**Control Salud** es un hub central que conecta dos aplicaciones independientes:

1. **Presión Arterial** — Registra presión sistólica, diastólica y pulso, con categorización AHA (Asociación Americana del Corazón), alertas de hipotensión y conteo de lecturas altas, bajas y normales.
2. **Glicemia** — Registra niveles de glucosa en sangre con categorización ADA (Asociación Americana de Diabetes), contexto de la toma (ayunas, postprandial, etc.) y alertas de hipo/hiperglucemia.

Todo funciona **100 % en el navegador**, sin backend ni base de datos externa. Los datos se guardan automáticamente en el `localStorage` del dispositivo.

---

## ✨ Características

### 🏠 Página principal (`index.html`)
- Panel visual con tarjetas de acceso a cada herramienta.
- **Resumen dinámico** de la última lectura de presión, última glicemia y total de registros combinados.
- Modo claro/oscuro persistente.
- Diseño responsive (móvil, tablet, escritorio).

### 🫀 Módulo de Presión Arterial (`presion_arterial.html`)
- Registro de fecha, hora, sistólica, diastólica, pulso y notas.
- Categorización automática según **AHA**:
  - 🟢 Normal · 🟡 Normal-Alta · 🟠 Etapa 1 · 🔴 Etapa 2 · ⚫ Crisis · ⚠️ Hipotensión.
- Alerta en tiempo real al escribir valores bajos (< 90/60).
- Estadísticas: promedio, rango, total, conteo de lecturas bajas, altas y normales.
- Gráfico de tendencia con líneas de meta configurables.
- Edición y eliminación de registros.
- Exportación a CSV.
- Modo oscuro.

### 🩸 Módulo de Glicemia (`glicemia.html`)
- Registro de fecha, hora, valor (mg/dL), contexto (ayunas, postprandial 2h, preprandial, aleatorio), medicación y notas.
- Categorización automática según **ADA**:
  - ✅ Normal · 🟡 Prediabetes · 🔴 Diabetes · ⚠️ Hipoglucemia.
- Alertas en tiempo real al ingresar valores de riesgo.
- Estadísticas: promedio, rango, total, conteo de hipoglucemias e hiperglucemias.
- Gráfico de tendencia con línea de meta configurable.
- Edición y eliminación de registros.
- Exportación a CSV.
- Modo oscuro.

### 🌐 Características transversales
- **Botón flotante "Volver al inicio"** en cada módulo (ideal para móviles).
- **Sin caducidad**: los datos permanecen hasta que el usuario los borre.
- **Sin conexión a internet** (excepto la carga inicial de las librerías CDN).
- **Sin publicidad ni rastreo**.

---

## 📂 Estructura del proyecto
