# Tienda Ticket MVP — Guía de Prueba y Validación

## 1. CÓMO EJECUTAR EL PROTOTIPO

### Opción A: En tu computadora
1. Descarga el archivo `tienda_ticket_mvp.html`
2. Abre el archivo en cualquier navegador (Chrome, Firefox, Safari, Edge)
3. No requiere conexión a internet ni instalación

### Opción B: En teléfono (para probar con tenderos)
1. Carga el archivo a un servidor temporal (ej: https://github.com, Google Drive, o un hosting gratuito)
2. Abre el link en el navegador del teléfono
3. Alternativa local: Usa AirDrop, email o compartir por WhatsApp el archivo HTML

## 2. ESTRUCTURA DEL PROTOTIPO

El MVP tiene 6 módulos accesibles por la barra lateral:

### Módulo A: 📦 Caja Rápida
- **Funcionalidad:** Simula el flujo de ventas en mostrador
- **Características:**
  - 20 productos guatemaltecos precargados con precios en Q
  - Búsqueda de productos en tiempo real
  - Opción de registrar productos sin código (venta manual)
  - Botones de cobro rápido: Q5, Q10, Q20, Q50, Q100, Q200
  - Cálculo automático de cambio
  - Carrito visible con opción de quitar items
- **Prueba:** Registra 2-3 ventas típicas (ej: arroz + frijoles + café)

### Módulo B: 💰 Ganancia Visible
- **Funcionalidad:** Muestra rentabilidad percibida después de cada venta
- **Datos:**
  - Ganancia bruta acumulada del día
  - Margen porcentual
  - Total vendido y número de transacciones
  - Costo estimado (editable)
- **Propósito:** Validar si ver ganancia en tiempo real es motivante

### Módulo C: ⏱️ Valle vs Pico
- **Funcionalidad:** Compara comportamiento bajo dos escenarios
- **Cómo funciona:**
  - Selecciona código de participante
  - Elige "Hora Valle" (sin presión) o "Hora Pico" (con presión simulada)
  - Sistema captura automáticamente:
    - Tiempo total de operación
    - Número de clics
    - Errores cometidos
    - Número de transacciones completadas
- **Exporta:** Resultados en CSV para análisis posterior

### Módulo D: 🔒 Confianza y Privacidad
- **Contenido:**
  - Qué información se registra
  - Para qué se usa
  - Dónde permanecen los datos (navegador local)
  - Cómo borrar todo
  - Aclaración legal: no es sistema tributario oficial
- **Propósito:** Tranquilizar al tendero sobre privacidad

### Módulo E: 📋 Encuesta
- **5 preguntas Likert (1-5):**
  1. Facilidad de registrar una venta
  2. Velocidad del proceso
  3. Utilidad de ver ganancia
  4. Disposición a usar la herramienta diariamente
  5. Dificultades encontradas (respuesta abierta)
- **Exporta:** Respuestas en CSV

### Módulo F: 🔬 Modo Investigador
- **Acceso:** Solo para facilitador
- **Funcionalidad:**
  - Gestionar sesiones de prueba
  - Registrar código anónimo de participante
  - Ingresar observaciones durante la prueba
  - Ver resultados automáticos
  - Exportar todas las sesiones en CSV
- **Tabla de criterios de éxito**
- **Protocolo de prueba paso a paso**

---

## 3. PROTOCOLO DE PRUEBA CON TENDEROS (10-15 minutos)

### Estructura: 5 fases

#### Fase 1: Introducción (1 minuto)
**Lo que dices:**
> "Buenos días/tardes. Estoy validando un prototipo de herramienta para registrar ventas de forma rápida. Tu aporte es muy valioso. No es un sistema oficial; es experimental. ¿Tienes 10-15 minutos?"

**Objetivo:** Contexto claro, sin compromiso.

#### Fase 2: Familiarización (2 minutos)
**Qué muestras:**
- Cómo buscar un producto (barra de búsqueda)
- Cómo agregar al carrito (clic en producto)
- Botones de cobro rápido
- Dónde aparece la ganancia estimada

**Lo que dices:**
> "Esto es como una caja registradora simplificada. Aquí está el menú de productos, aquí agregamos al carrito, y aquí cobramos. ¿Preguntas antes de empezar?"

**Objetivo:** Familiaridad sin instrucciones exhaustivas.

#### Fase 3: Hora Valle (3-4 minutos)
**Lo que dices:**
> "Ahora te pido que registres 3-5 ventas típicas como si fuera una mañana tranquila. Sin prisa. Cualquier producto que normalmente vendes."

**Sistema captura:**
- Tiempo total
- Clics
- Errores
- Transacciones completadas

**Observa:**
- ¿Tarda en encontrar productos?
- ¿Duda con los botones?
- ¿Usa la búsqueda o los iconos?

#### Fase 4: Hora Pico (3-4 minutos)
**Lo que dices:**
> "Ahora simulo que es mediodía y hay fila. Voy a darte clientes rápido. Quiero que completes las operaciones lo más rápido posible. Aquí vienen:"
> 
> "Cliente 1: arroz, aceite, sal"
> "Cliente 2: leche, huevos"
> "Cliente 3: café, pan"

**Sistema captura** lo mismo que en Valle.

**Observa:**
- ¿Abandona alguna operación?
- ¿Los botones de cobro rápido ayudan?
- ¿La búsqueda ralentiza o acelera?
- ¿Hay frustración?

#### Fase 5: Encuesta (3-5 minutos)
**Lo que dices:**
> "Perfecto. Ahora te pido que respondas 5 preguntas rápidas sobre tu experiencia."

**Recolecta:**
- Evaluaciones 1-5 en facilidad, velocidad, utilidad
- Disposición a usar
- Comentarios abiertos

---

## 4. HIPÓTESIS Y MÉTRICAS

### Hipótesis Principal
**Si reduzco el número de clics y el tiempo para registrar una venta, el tendero tendrá más disposición a usarla durante horas pico.**

### Indicadores a Medir

| Aspecto | Métrica | Cómo Medir | Umbral Inicial |
|---------|---------|-----------|----------------|
| **Deseabilidad** | Utilidad percibida | Pregunta 3 (ganancia útil?) | ≥4/5 (mediana) |
| **Deseabilidad** | Intención de uso | Pregunta 4 (usar diariamente?) | ≥4/5 (mediana) |
| **Usabilidad** | Facilidad | Pregunta 1 (facilidad?) | ≥4/5 (mediana) |
| **Usabilidad** | Independencia | % que completa sin ayuda | ≥80% |
| **Usabilidad** | Velocidad percibida | Pregunta 2 (rapidez?) | ≥4/5 (mediana) |
| **Viabilidad Operativa** | Completar bajo presión | % que completa hora pico | ≥80% (4 de 5) |
| **Viabilidad Operativa** | Diferencia pico/valle | Clics pico vs clics valle | Pico ≤ Valle +20% |
| **Viabilidad Técnica** | Funcionamiento | Cero errores críticos | 100% |
| **Viabilidad Técnica** | Persistencia local | Datos se guardan/exportan | 100% |

### Cómo Interpretar Resultados (5 participantes)

**Éxito débil:**
- Mediana de facilidad/utilidad = 3/5
- 3 de 5 completan hora pico
- Comentarios: "Rápido pero le falta X"

**Éxito fuerte:**
- Mediana de facilidad/utilidad = 4-5/5
- 4-5 de 5 completan hora pico sin presión
- Comentarios positivos sin bloqueadores claros

**Fracaso:**
- Mediana < 3/5
- <3 de 5 completan hora pico
- Comentarios: "Demasiado complicado", "No lo usaría"

---

## 5. CÓMO EXPORTAR Y ANALIZAR DATOS

### Exportar desde Comparación (Valle vs Pico)
1. Ve a módulo "⏱️ Valle vs Pico"
2. Haz clic en "📥 Exportar Resultados (CSV)"
3. Se descargará `comparacion_valle_pico.csv`

**Columnas:**
- Participant
- Scenario (valle/pico)
- Timestamp
- Duration(s)
- Clicks
- Errors
- Transactions

### Exportar desde Encuesta
1. Ve a módulo "📋 Encuesta"
2. Haz clic en "📥 Exportar Encuesta"
3. Se descargará `encuesta_respuestas.csv`

**Columnas:**
- Pregunta (facilidad, velocidad, utilidad, disposición, dificultades)
- Respuesta (1-5 o texto abierto)

### Exportar desde Modo Investigador
1. Ve a módulo "🔬 Investigador"
2. Haz clic en "📥 Exportar Todos (CSV)"
3. Se descargará `investigacion_sesiones.csv`

**Columnas:**
- SessionID
- Participant
- Scenario
- Duration, Clicks, Errors
- Notes (observaciones del facilitador)

### Análisis Rápido en Spreadsheet
1. Copia los datos CSV en Google Sheets o Excel
2. Calcula medianas por pregunta:
   - =MEDIAN(rango) para respuestas Likert
3. Cuenta porcentajes:
   - =COUNTIF(rango,">3")/COUNTA(rango) para % que responde ≥4/5
4. Compara pico vs valle:
   - Diferencia de clicks: Pico_Clicks - Valle_Clicks
   - Diferencia de tiempo: Pico_Duration - Valle_Duration

---

## 6. COMPARTIR EL PROTOTIPO CON TENDEROS

### Opción 1: Link en navegador (móvil/desktop)
```
Sube el archivo HTML a:
- Google Drive (compartir link)
- GitHub (páginas públicas)
- Netlify/Vercel (free hosting)
- Dropbox (compartir)
```

### Opción 2: Archivo local (sin internet)
```
1. Copia tienda_ticket_mvp.html al teléfono
2. Abre con navegador (Chrome, Firefox)
3. Funciona sin conexión
```

### Opción 3: Demo en vivo
```
1. Abre en tu laptop
2. Conéctate a la misma WiFi
3. Comparte pantalla vía:
   - Zoom/Google Meet
   - AirPlay (Mac)
   - Chromecast
```

---

## 7. DATOS GENERADOS Y PRIVACIDAD

### Qué se registra
- Productos agregados
- Montos de venta
- Tiempos y clics (en modo pico/valle)
- Respuestas a encuesta

### Dónde se guardan
- **Local Storage** del navegador
- No se envía a ningún servidor
- Se borra si limpias caché del navegador

### Cómo borrarlo todo
1. Ve a módulo "🔒 Confianza"
2. Haz clic en "🗑️ Borrar Todos los Datos"
3. Se eliminan: ventas, pruebas, encuestas

---

## 8. TROUBLESHOOTING

| Problema | Solución |
|----------|----------|
| El archivo no abre | Verifica que sea .html y abre con navegador (no doble clic directo) |
| Los datos no se guardan | Comprueba que localStorage no esté deshabilitado (Incógnito puede afectar) |
| No se ve bien en móvil | Abre en Chrome/Firefox; algunos navegadores pueden tener CSS limitado |
| No funciona sin internet | Debe funcionar offline. Recarga la página después de descargar. |
| Botones lentos | Normal si hay muchas ventas registradas; los datos se guardan localmente |

---

## 9. CRITERIOS DE DECISIÓN

**Después de 5 participantes, pregúntate:**

### ¿Continuar desarrollando?
- [x] Si mediana de utilidad ≥ 4/5
- [x] Si 4+ de 5 completan hora pico
- [x] Si no hay errores críticos recurrentes
- [x] Si comentarios señalan mejoría, no rechazo fundamental

### ¿Iterar y reprueba?
- [ ] Si mediana = 3/5 (neutral)
- [ ] Si hay bloqueador claro (ej: búsqueda lenta, botones confusos)
- [ ] Si 3 de 5 completan pero mencionan lo mismo

### ¿Parar o pivotear?
- [ ] Si mediana < 3/5
- [ ] Si <3 de 5 completan hora pico
- [ ] Si comentarios indican rechazo fundamental ("No lo usaría")
- [ ] Si la hipótesis sobre "horas pico" no se valida

---

## 10. PRÓXIMOS PASOS DESPUÉS DE VALIDACIÓN

### Si resulta positivo:
1. **Integración real con SAT:** Conectar registro de ventas
2. **Estadísticas más ricas:** Gráficos de ventas por hora
3. **Múltiples tenderos:** Supervisión de sucursales
4. **Análisis de márgenes:** Por producto, por categoría
5. **Integración de inventario:** Restar stock automáticamente

### Si es neutral:
1. **Rediseña de UX:** Simplificar más (menos clics)
2. **Prueba A/B:** Compara interfaces
3. **Encuesta cualitativa:** ¿Qué falta? ¿Qué molesta?

### Si es negativo:
1. **Análisis de barreras:** ¿Es confianza? ¿Complejidad? ¿Valor?
2. **Pivote:** Tal vez no es "horas pico" sino educación o hábito
3. **Entrevistas:** Habla directamente con tenderos

---

## 11. CONTACTO Y VERSIÓN

- **Versión:** MVP 1.0 (2026-10-18)
- **Última actualización:** Este documento
- **Arquitectura:** HTML + JavaScript vanilla + Local Storage
- **Dependencias:** Ninguna (funciona en cualquier navegador moderno)

---

**Recuerda:** Este MVP es para validar rápido, no para ser perfecto. Cada error que encuentres es información valiosa.
