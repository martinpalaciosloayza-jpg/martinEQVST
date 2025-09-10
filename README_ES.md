# EQ3 VST3 — Instrucciones (español, optimizado para NVDA)

Este repositorio contiene el código y herramientas para generar el plugin **EQ3.vst3**.

## Opciones para obtener el `.vst3`

### Opción A — Usar GitHub Actions (recomendado si no quieres compilar localmente)
1. Sube este repositorio a GitHub en la rama `main`.
2. Ve a la pestaña **Actions** en tu repositorio y ejecuta el flujo `Build EQ3 VST3 (Windows)` (o espera a que se ejecute al hacer push).
3. Cuando termine, en la propia ejecución del workflow abre **Artifacts** y descarga `EQ3-vst3.zip` o el archivo `EQ3.vst3`.

> Nota NVDA: al navegar por la interfaz web, usa las teclas de navegación habitual del navegador con NVDA. GitHub es razonablemente accesible.

### Opción B — Compilar localmente en Windows
1. Instala FAUST y el VST3 SDK (descarga `vst3sdk` desde GitHub y descomprímelo en una carpeta, por ejemplo `C:\vst3sdk`).
2. Abre PowerShell en la carpeta raíz del proyecto y ejecuta:
   ```powershell
   .\build\build-windows.ps1 -VST3_SDK_Path "C:\vst3sdk"
   ```
3. Si todo va bien tendrás `build\EQ3.vst3`.

## Instalación del plugin en Windows (ruta VST3)
1. Copia `EQ3.vst3` a `C:\Program Files\Common Files\VST3\` (requiere permisos de administrador).
2. Abre Reaper.
3. En Reaper, añade un FX a una pista: selecciona la pista → `Shift+F` → escribe `EQ3` → Enter para cargar.

## Uso con NVDA en Reaper
- Reaper expone los parámetros del plugin al host. Para que NVDA anuncie parámetros:
  - Asegúrate de que el foco esté en la ventana de FX del plugin o en la lista de parámetros.
  - En la ventana de FX, navega con Tab/Shift+Tab; NVDA leerá etiquetas si Reaper las muestra.
  - Para valores precisos, usa la lista de parámetros del plugin en Reaper (botón "Param") que muestra nombres y valores.

## Nota sobre VST2
No se incluye VST2 por restricciones de licencia del SDK VST2. Si obtienes licencia VST2, te indicaré los pasos para compilar el VST2.
