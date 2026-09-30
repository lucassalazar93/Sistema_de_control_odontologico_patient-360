# Patient 360 — código editable

Copia del prototipo publicado el 30 de septiembre de 2026, con el nuevo ícono de diente.
HTML, CSS y JavaScript sin framework. No necesita instalar paquetes ni compilar.

## Abrir y editar

1. Extrae TODO el ZIP en una carpeta de tu computador.
2. Abre Visual Studio Code y selecciona Archivo > Abrir carpeta. Escoge Patient_360.
3. Para una vista rápida, abre dist/index.html con tu navegador.
4. Edita los archivos, guarda y recarga el navegador para ver los cambios.
5. Para mantener el código legible en VS Code, usa Formatear documento (Shift + Alt + F en Windows), con un formateador compatible si el editor lo solicita.

Opcional: si tienes Python instalado, abre una terminal en Patient_360 y ejecuta:

    python -m http.server 8000 --bind 127.0.0.1 --directory dist

En Windows también puedes usar `py` en lugar de `python`. Abre http://localhost:8000 y deja la terminal abierta. Ctrl+C detiene el servidor.

## Dónde cambiar cada parte

| Archivo | Contenido |
| --- | --- |
| dist/index.html | Estructura principal, nombre, logotipo del diente, favicon, estilos base e inclusión de scripts. |
| dist/app.js | Datos ficticios de pacientes, tratamientos, citas, facturas y pagos; vistas y funciones base. |
| dist/enhancements.js | Agenda por profesional, reservas VIP, conflictos de horarios y atribución de campañas. |
| dist/enhancements.css | Diseño de agenda y atribución. |
| dist/vip.js | Preferencias del paciente, preparación de visitas, planes y acompañamiento. |
| dist/vip.css | Diseño de experiencia VIP. |
| dist/workspaces.js | Separación clínica/administración, inicios, recorrido del paciente, salida administrativa, control contable y asistente demo. |
| dist/workspaces.css | Diseño de los dos espacios, tablero del recorrido y adaptación por tamaño de pantalla. |

El orden de ejecución es app.js → enhancements.js → vip.js → workspaces.js. Los archivos posteriores amplían o sustituyen funciones anteriores. Conserva ese orden al editar. Para cambiar una vista busca también su asignación en `views`; editar la función original puede no cambiar la vista final si otra la reemplaza.

## Cambios habituales

- Nombre e ícono de la plataforma: busca `brand` y `brand-mark` en index.html.
- Colores: estilos base de index.html y reglas de workspaces.css; los estilos posteriores pueden sobrescribir los anteriores.
- Datos: arreglos `patients`, `appointments`, `treatments`, `quotes`, `invoices` y `payments` en app.js. Conserva las relaciones por ID.
- Menús por espacio: `clinicNav` y `businessNav` en workspaces.js.
- Pasos del recorrido: `flowStages`, `visitFlow` y `advanceFlow` en workspaces.js. Si cambias las etapas, ajusta también las reglas de transición y entrega administrativa.
- Reservas VIP: `vipBlocks`, `scheduleConflict`, `vipForm` y `toggleVip` en enhancements.js.
- Textos de bienvenida: `clinicHome` y `businessHome` en workspaces.js.

## Qué incluye y qué falta para producción

Incluye el frontend completo del prototipo, las interacciones y los datos ficticios. El escenario inicial usa el 28 de septiembre de 2026; existen otras fechas fijas en los datos y funciones. No cambia automáticamente al día actual.

Los cambios realizados dentro de la demo viven en memoria y se pierden al recargar. Los cambios que guardes en los archivos sí permanecen.

La separación de espacios es una demostración visual: no es autenticación ni autorización real. El código contiene todos los datos demo y no debe alojar historias clínicas reales. El acceso privado de la versión alojada depende del servicio de alojamiento y no está incluido en esta copia local.

No incluye servidor, base de datos, usuarios reales, integración bancaria, facturación fiscal, envío de WhatsApp ni IA conectada. El asistente calcula respuestas con reglas. Para uso real habrá que implementar persistencia, permisos en el servidor, auditoría y las integraciones correspondientes.

Las tipografías se solicitan a Google Fonts; sin internet el navegador usa las alternativas declaradas. El código de la aplicación y sus íconos están en esta carpeta.

## Publicar tu versión

Puedes servir el contenido de dist en un alojamiento compatible con sitios estáticos. No requiere build. Conserva juntos los archivos y sus nombres relativos. Tus ediciones locales no actualizan automáticamente el sitio ya publicado: tendrás que publicar la nueva versión.

Este paquete contiene el código de la aplicación y esta guía. No incluye historial Git, credenciales ni configuración privada del servicio de alojamiento.
