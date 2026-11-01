# ✂️ Micro App Peluquería ("Color · Laura")

Micro aplicación móvil hiperenfocada para estilistas, coloristas y peluquerías independientes. Inspirada en el modelo de Micro Apps para negocios locales de **Máximo Ramos**.

---

## 🚀 Cómo probarla localmente

1. Puedes simplemente hacer **doble clic en `index.html`** y se abrirá directamente en tu navegador (Chrome, Edge, Safari, etc.).
2. O bien iniciar un servidor local rápido abriendo la terminal en esta carpeta y ejecutando:
   ```bash
   python -m http.server 3000
   ```
   Luego visita `http://localhost:3000`.

---

## 🌐 Cómo publicarla en Netlify en 30 segundos (Gratis)

1. Inicia sesión en [app.netlify.com](https://app.netlify.com).
2. Ve a la pestaña **"Sites"**.
3. Arrastra y suelta la carpeta `peluqueria` directamente en la sección que dice **"Want to deploy a new site without connecting to Git? Drag and drop your site output folder here"**.
4. ¡Listo! Netlify te dará una URL pública al instante (ej: `https://color-laura.netlify.app`), la cual puedes compartir o abrir desde el celular y añadir a la pantalla de inicio como App.

---

## ✨ Características implementadas

- **Diseño Mobile-First fiel al video:** Interfaz cálida, limpia y con marco de teléfono para computadoras, 100% responsiva para pantallas móviles.
- **Clientas Demo precargadas:** Martina (Cobrizo), Lucía (Rubio), Carla (Violeta) y Sofía (Fantasía).
- **Cálculo dinámico de semanas:** Cuenta las semanas desde la última visita e indica con alerta `⏰ Toca Retoque` cuando ya cumplieron el tiempo recomendado.
- **Botón de WhatsApp en 1 Clic:** Genera y abre el enlace directo `https://wa.me/` con mensaje personalizado (*"¡Hola Martina! 💜 Ya pasaron 6 semanas de tu Cobrizo, ¿te reservo turno para el retoque?"*). Al hacer clic cambia el estado a `Enviado ✓`.
- **Botón "Vino hoy ✂️":** Actualiza en 1 toque la última fecha de visita y resetea las semanas a 0.
- **Control de Cobros:** Distingue entre clientas `"al día ✓"` y clientas con saldo pendiente (ej. `$12.000`), con suma total en el panel superior.
- **Buscador y Filtros rápidos:** Por nombre, servicio, retoque pendiente o estado de pago.
- **Configuración editable:** Permite cambiar el nombre del salón y personalizar la plantilla de texto del mensaje de WhatsApp.
- **Persistencia Local (LocalStorage):** Todo queda guardado en el navegador del usuario sin necesidad de servidores externos.
