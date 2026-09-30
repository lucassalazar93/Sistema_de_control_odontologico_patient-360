# Desplegar Patient 360 en Vercel

Este paquete está preparado, pero todavía no está desplegado en tu cuenta de Vercel.

## Condiciones del plan
Vercel Hobby está limitado al uso personal no comercial. Una demostración para un cliente puede ser un uso comercial. No asumas que es elegible solo porque tiene datos ficticios: valida el caso con Vercel o utiliza un plan que permita ese uso.
Referencia: https://vercel.com/docs/plans/hobby

## Opción directa, sin repositorio
1. Extrae el ZIP completo.
2. Abre la carpeta Patient_360 en VS Code.
3. Abre una terminal dentro de esa carpeta: debes ver vercel.json y la carpeta dist.
4. Con Node.js y npm instalados, ejecuta:

   npx vercel@latest login
   npx vercel@latest --prod

El primer comando autentica tu cuenta. El segundo publica el sitio: acepta instalar la CLI si lo solicita, selecciona tu cuenta/equipo y un plan compatible con el uso. Crea un proyecto nuevo llamado patient-360-demo y usa ./ como carpeta. No enlaces otro proyecto existente. La configuración incluida define dist como salida y no requiere compilación.

No necesitas ejecutar npm install en este proyecto: no tiene dependencias de aplicación. npx descarga la herramienta de publicación.

Al terminar, Vercel entrega la URL real. Abre esa URL en una ventana de incógnito para verificar el acceso del cliente. Si solicita acceso, revisa Deployment Protection en Vercel; no compartas credenciales. Cambiar protección a acceso abierto hace visible la demo a quien tenga el enlace.

## Opción con GitHub
Crea un repositorio y sube el contenido de Patient_360, no el ZIP. vercel.json y dist deben quedar en la raíz del repositorio. Importa el repositorio en Vercel con:
- Framework Preset: Other
- Root Directory: raíz del repositorio
- Output Directory: dist
- Build Command: vacío
- Install Command: vacío

Referencia: https://vercel.com/docs/project-configuration/vercel-json

## Recorrido para presentar
1. Atención clínica > Recorrido del paciente.
2. Fecha: 28 de septiembre de 2026; Todas las sedes.
3. Avanza una tarjeta con Registrar llegada e Iniciar atención.
4. Pulsa Entregar a administración.
5. Cambia a Administración > Salidas y coordinación.
6. Revisa la cuenta y completa la salida.
7. Explora agenda, reservas VIP y origen de campañas.

La demo tiene datos ficticios. Cada navegador mantiene sus cambios en memoria: no se sincronizan entre usuarios y se reinician al recargar. No introduce base de datos, autenticación ni cobros reales. La separación de perfiles no es control de acceso real.

Se incluye una cabecera noindex para pedir a buscadores que no indexen la demo. No es protección de acceso.
