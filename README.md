# Rutina de entrenamiento general · 12 semanas

Aplicación de una sola página (HTML + CSS + JS, sin dependencias de build) para
seguir un programa de entrenamiento general de gimnasio orientado a **déficit
calórico con mantenimiento de masa muscular**: 3 sesiones full body por
semana, ≤90 minutos por sesión, en 3 bloques de 4 semanas cada uno.

No requiere backend, ni instalación, ni build step: es un único archivo
`index.html` que corre entero en el navegador.

## Funcionalidades

- **Rutina**: los 3 días de entrenamiento de cada una de las 12 semanas, con
  series/repeticiones/RPE calculados según el bloque (Adaptación →
  Intensificación → Consolidación).
- **Registro de cargas**: campo de peso (kg) por ejercicio y semana, para
  llevar el registro de progresión.
- **Checklist de sesión**: tildá cada ejercicio a medida que lo hacés durante
  el entrenamiento, con un botón para reiniciar el checklist de la semana.
- **Timer de descanso**: cuenta regresiva (90s en principales, 60s en
  accesorios) con pausa, +/-15s y aviso sonoro al terminar.
- **Cambiar ejercicios**: reemplazá cualquier ejercicio por una alternativa
  del mismo grupo muscular, semana por semana.
- **Cómo hacerlo**: ficha por ejercicio con diagrama esquemático, cómo
  armarlo, ejecución y errores comunes. Incluye buscador y filtro por grupo
  muscular.
- **Renombrar ejercicios**: cada ejercicio se puede renombrar de forma global
  (por ejemplo, para usar el nombre que usan en tu gimnasio); el cambio se
  refleja en todas las solapas.
- **Info general**: glosario de términos (RPE, RIR, progresión doble, etc.).
- Diseño responsive pensado para usarse desde el celular en el gimnasio.

## Cómo usarlo

### Opción 1: abrir el archivo directo
Descargá `index.html` y abrilo con cualquier navegador (funciona sin
conexión a internet, salvo por la tipografía que se carga desde Google
Fonts).

### Opción 2: GitHub Pages (recomendado para usar desde el celular)
1. Subí este repositorio a GitHub.
2. Andá a **Settings → Pages**.
3. En "Branch" elegí `main` y carpeta `/ (root)`, guardá.
4. GitHub va a publicar el sitio en una URL del tipo:
   `https://<tu-usuario>.github.io/<nombre-del-repo>/`
5. Guardá esa URL como acceso directo en tu celular (en iOS/Android: "Agregar
   a pantalla de inicio" desde el navegador) para abrirla como si fuera una
   app.

## Guardado de datos

Los datos que cargás (peso levantado, checklist, ejercicios reemplazados,
nombres personalizados) se guardan en el `localStorage` del navegador donde
abrís la app. Esto significa:

- Persisten entre sesiones **en el mismo navegador y dispositivo**.
- No se sincronizan entre dispositivos ni navegadores distintos (por
  ejemplo, si lo abrís en el Chrome del celular y en el Safari de la compu,
  son dos "guardados" independientes).
- No hay ningún servidor de por medio: los datos nunca salen de tu
  navegador.

## Personalizar la rutina

Todo el contenido (ejercicios, alternativas, esquemas de series/reps,
glosario, guías) está en un solo array/objeto de JavaScript dentro de
`index.html`, buscá estas variables:

- `DAYS`: los 3 días de entrenamiento y sus ejercicios por defecto.
- `ALTERNATIVES`: las alternativas disponibles por grupo muscular.
- `EXERCISE_GUIDE`: el texto de cómo armar/ejecutar cada ejercicio.
- `EXERCISE_POSE` / `POSE_SVG`: el diagrama esquemático de cada ejercicio.
- `mainScheme` / `accScheme`: las series, repeticiones y RPE por semana.

## Licencia

MIT. Ver [LICENSE](LICENSE).
