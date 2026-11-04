# ✂️ Manual de Usuario · Salón de Peluquería

¡Bienvenida a la aplicación web de gestión de clientas, fidelización, agenda en la nube y cobro para tu salón de peluquería! Esta herramienta fue creada para acompañarte en el salón, agilizar la atención entre tinturas y cortes, enviar avisos de retoque por WhatsApp en 1 toque y permitir que tus clientas se anoten solas sin que se te superpongan los turnos.

---

## 1. Pantalla Principal: ¿Qué vas a ver?

1. **Cabecera del Salón:**
   * **Nombre y Foto de Portada/Logo:** Podés subir el logo o foto de tu peluquería y cambiar el nombre del local desde los ajustes.
   * **Indicador de Turnero:** Señal en vivo de si la agenda online está abierta para recibir reservas (`🟢 Turnero Activo`) o pausada.
   * **📷 Cobro QR:** Botón directo para mostrar en pantalla grande tu QR de Mercado Pago o transferencias para mostrador.
   * **⚙️ Ajustes:** Modificar datos del salón, horarios de atención, mensaje de WhatsApp y respaldo en Google Drive.

2. **Panel de Clientas:**
   * Listado organizado de clientas con fecha del último servicio, tratamiento realizado y semanas transcurridas.
   * **Cero etiquetas innecesarias:** Si la clienta está al día no muestra carteles molestos; si registra saldo pendiente se destaca en rojo con botón para cobro inmediato por QR.
   * **Filtros rápidos:** Ver todas, clientas con tiempo cumplido para retoque o clientas con deuda pendiente.

3. **Acciones Rápidas en cada Ficha:**
   * **💬 WhatsApp:** Envía el aviso de retoque automático en 1 solo clic.
   * **⭐ Sumar Sello:** Registra la visita en la tarjeta de fidelidad de la clienta.
   * **💳 Cobrar:** Abre el modal de cobro QR con el monto exacto adeudado en pesos argentinos (ARS $).

---

## 2. Flujo de Trabajo en el Salón

### Nueva Clienta o Visita
1. Tocá el botón verde **+ Nueva Clienta**.
2. Escribí el **Nombre** y su **WhatsApp** (con código de área sin el 15).
3. Seleccioná el servicio realizado (ej: *Color y Reflejos*, *Balayage*, *Alisado*, *Corte y Peinado*).
4. Guardá la ficha.

### Enviar Mensaje de Retoque por WhatsApp
1. En la tarjeta vas a ver el tiempo desde la última visita (ej: `Hace 4 semanas`).
2. Tocá el botón de **WhatsApp**.
3. Se abre WhatsApp con el mensaje ya listo:
   > *"¡Hola Romina! Ya pasaron 4 semanas de tu Balayage, ¿te reservo turno para el retoque?"*
4. Lo mandás con 1 toque sin tener que escribirlo a mano.

---

## 3. Turnero en la Nube con Bloqueo Real

Tus clientas pueden agendar su turno desde su teléfono:
1. En **Ajustes**, habilitá el switch **Turnero Online**.
2. Compartí el link con tus clientas por WhatsApp o en la bio de tu Instagram.
3. **Bloqueo Automático en la Nube:** Cuando una clienta elige un horario (ej: sábado 16:00 hs), ese casillero se bloquea en la nube y se desactiva en gris (`🔒 Ocupado`) para todas las demás personas.
4. **Freno de Colisión:** Si dos clientas intentan reservar el mismo horario al mismo tiempo, el sistema protege el turno y le indica a la segunda que elija otro casillero libre.
5. **📅 Control Manual del Salón (Agenda):**
   * En cualquier momento podés abrir **📅 Control Manual de Horarios**.
   * Podés ocupar manualmente un turno (si una clienta te pidió turno en el salón o por teléfono).
   * Podés liberar horarios cancelados.
   * Podés cerrar el salón por el día completo con un solo toque.

---

## 4. Cobro con QR (Mercado Pago y Bancos)

* Tocá el botón **📷 Cobro QR** en el encabezado o en la ficha de cobro de una clienta.
* La app muestra el código QR vinculado a tu Alias/CBU y el monto en pesos argentinos ($ ARS).
* La clienta escanea con Mercado Pago, MODO o cualquier app bancaria y te transfiere en el acto.
* Posee redundancia garantizada: si el generador local no responde, se activa un motor de respaldo automático para asegurar el cobro.

---

## 5. Respaldo y Copia de Seguridad

* **Google Drive Automático:** Sincroniza periódicamente tus clientas y configuraciones a una carpeta privada en tu Drive.
* **Exportar / Importar JSON:** Descarga un archivo de copia de seguridad con un solo clic para guardar o transferir a otro teléfono o computadora.
