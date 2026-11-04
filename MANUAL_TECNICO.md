# 🛠️ Manual Técnico · Salón de Peluquería

**Stack:** HTML5, Tailwind CSS (CDN), Vanilla JavaScript (ES6+), LocalStorage, Cloudflare Worker / JSONBin Cloud API, QRCode.js, Canvas Confetti.  
**Despliegue:** GitHub Pages (`https://juancdgo.github.io/peluqueria/`).  
**Copia de Seguridad:** Google Drive / LocalStorage JSON.

---

## 1. Arquitectura de la Aplicación

Construida bajo el estándar **Single-Page Application (SPA)** de carga instantánea sin servidor Node/backend relacional:
* Ejecución completa en el navegador de la usuaria.
* Capa de persistencia local offline-first en `localStorage`.
* Servicio serverless de sincronización de agenda para reserva colaborativa de turnos.

### Árbol del Repositorio:
```text
Mini Apps/peluqueria/
├── index.html            # Aplicación completa (Panel Admin + Turnero Online + Cobro QR)
├── MANUAL_USUARIO.md     # Manual de uso diario para la peluquera
└── MANUAL_TECNICO.md     # Especificación técnica, esquemas y endpoints
```

---

## 2. Esquema de Persistencia (LocalStorage)

### 1. `microapp_settings`
```typescript
{
  salonName: string;          // "Color · Laura"
  paymentAlias: string;       // "peluqueria.laura.mp"
  paymentHolder: string;      // "Laura Gómez"
  salonLogo: string;          // Imagen comprimida en base64
  template: string;           // Plantilla con {nombre}, {servicio}, {semanas}
  bookingEnabled: boolean;    // Estado de la agenda online
  bookingStartHour: number;   // Hora de inicio (ej: 9)
  bookingEndHour: number;     // Hora de cierre (ej: 20)
  workDays: number[];         // Días laborables [1, 2, 3, 4, 5, 6]
  loyaltyEnabled: boolean;    // Sistema de sellos habilitado
  loyaltyTarget: number;      // Cantidad de sellos para recompensa (default: 6)
  loyaltyReward: string;      // "1 Baño de Crema o Nutrición Gratis"
}
```

### 2. `microapp_clients`
```typescript
Array<{
  id: string;                 // "c_1730000000000"
  name: string;               // Nombre de la clienta
  phone: string;              // Teléfono WhatsApp
  lastCutDate: string;        // Fecha de último servicio "YYYY-MM-DD"
  habitualService: string;    // "Color y Reflejos", "Balayage", etc.
  notes: string;              // Ficha técnica (fórmulas de color, etc.)
  stamps: number;             // Sellos acumulados
  totalVisits: number;        // Contador histórico
  debt: number;               // Deuda en ARS $ (0 = al día)
}>
```

---

## 3. Protocolo de Turnero en la Nube y Bloqueo

* **Identificador Cloud:** `CLOUD_APP_ID = 'peluqueria'`
* **Control de Concurrencia:**
  1. `fetchCloudDay(dateStr)` verifica atómicamente si el casillero horario ya fue ocupado antes de registrarlo.
  2. Al confirmarse la reserva, el horario se añade al array del día y se guarda en la nube con `saveCloudDay`.
  3. Para los demás visitantes, `renderCloudBookingHoursUI()` marca el botón como deshabilitado con `bg-slate-100 text-slate-400 cursor-not-allowed` y etiqueta `🔒 Ocupado`.
* **Panel Dueña:** `openOwnerAgendaModal()` permite ocupar o liberar horarios manualmente y cerrar fechas completas.

---

## 4. Cobro QR y Seguridad

* **Motor Dual QR:** `QRCode.js` local + respaldo automático a través de `QuickChart.io`.
* **Privacidad de Clientas:** La vista pública de turnero no expone nombres completos de otras clientas ni fórmulas técnicas de color.
* **Formatos Argentinos:** Manejo de moneda en pesos argentinos (ARS $) con separador de miles y horarios en huso GMT-3 (24hs).
