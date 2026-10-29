# Cierre general: logo SF limpio, Telazocraft unificado y verificación de proyectos personales

> **Estado:** COMPLETADO

## Objetivo

1. Rehacer `logo_sf_servicio_tecnico` sin sombra ni contorno negro.
2. Terminar Telazocraft: workspace único en la app, biblioteca dentro de la app y carpeta antigua retirada.
3. Verificar que todo funciona en los proyectos personales y subirlo como ItsRodryy.

## Alcance y permisos (dados por el usuario)

- Proyectos **personales** (sí): `D:\Proyectos\personal\web_serviferre`, `...\web_pokemon_tcg`,
  `...\fishery_app`, `...\telazocraft` (con `biblioteca\`).
- Proyectos **del trabajo** (NO tocar, ni leer git): `D:\Proyectos\iovi\**` (vision_driver),
  `C:\Users\adria\Desktop\io-066-saintgobain-placas-feature-linear-cam`, `D:\Proyectos\ia\**`.
- Git: autorizados los commits y `push` de este plan como **ItsRodryy**, sin firma de IA, mensaje
  `vX.Y.Z - Descripción`. Prohibido: `--force`, reescribir historial, crear etiquetas (en
  Telazocraft una etiqueta publica una Release), tocar ramas.
- Antes de cada commit: `git config user.name` debe ser `ItsRodryy`; si no, ponerlo en local.
- Nombres nuevos: minúsculas y guion bajo. Temporales en `%TEMP%\ai_workspace_codex\`.

## Estado de partida (comprobado por Claude, 29/10 22:50)

- web_serviferre `v0.0.2`, web_pokemon_tcg `v1.0.0`, fishery_app `v1.0.1`: AI Workspace 2.3.0
  subido. `recursos_vinilado/` (11 MB) sin subir.
- Telazocraft: biblioteca copiada con robocopy a `D:\Proyectos\personal\telazocraft\biblioteca`
  (3.145 archivos, 13,55 GB; lista, tamaños y fechas iguales; `servidores/` igual byte a byte).
  `%LOCALAPPDATA%\Telazocraft\ajustes.json` y la carpeta Syncthing `lepazo-vice-server` ya apuntan
  ahí (Syncthing en reposo, `need 0`; el dispositivo Portátil sigue en pausa a propósito).
  Smoke de la app (desarrollo e instalada) correcto; ve `hardcore` y `lepazo`.
- Workspace viejo de la biblioteca movido a `biblioteca/archivo/workspace_biblioteca_antiguo/`;
  su contexto, planes, CHANGELOG y ESTADO copiados a `telazocraft/ai_workspace/`.
- Sin commit en Telazocraft: `.gitignore` (+`/biblioteca/`), `README.md` y `ai_workspace/`.
- La vista previa del instalador en Telazocraft salió limpia (solo crea; sin conflictos).
- La carpeta original `C:\Users\adria\Desktop\minecraft_server_neoforge_1_21_1` **sigue existiendo**.

## Bloques

1. [HECHO] SF geometrico sin negro, sombra ni contorno; tipografia web en verde, PDF/PNG/catalogo regenerados y siete piezas comparadas visualmente.
2. [HECHO] Workspace 2.3.0 instalado en Telazocraft (Codex), sin conflictos ni copia de seguridad residual.
3. [HECHO] (Claude) Comparación repetida: 3.145 archivos iguales salvo `LEEME.md` y la IA movida a
   `archivo/workspace_biblioteca_antiguo/`. Sin servidores ni Telazocraft abiertos. Carpeta del
   Escritorio borrada. Copias antiguas sin tocar, anotadas en el ESTADO de Telazocraft.
4. [HECHO] (Claude) web_serviferre: `php -l` sin errores; 200 en todas las páginas, CSS y JS (el
   formulario se retiró en este trabajo: `/procesar_contacto.php` da 404 y ya no hay `config/`).
   web_pokemon_tcg: validador correcto (177 fichas; se le añadió `.github`), `node --check` y
   tres pruebas simuladas OK. fishery_app: lint y typecheck OK; RLS pendiente (Supabase pausado).
   telazocraft: 57 pruebas OK, smoke OK, `ajustes.json` y Syncthing en `biblioteca`, en reposo y
   sin error; git no ve `biblioteca/`. El Portátil **no estaba en pausa** (conectado desde el
   29/10 09:46, sin intervención de la IA): anotado. Los 4 en 2.3.0 y `Medir` sin excesos nuevos.
5. [HECHO] Subido como ItsRodryy, sin force ni etiquetas: telazocraft `v0.3.1`, web_pokemon_tcg
   `v1.0.1`/`v1.0.2`, fishery_app `v1.0.2`, web_serviferre `v0.0.3` y `v0.0.4`.
6. [HECHO] Cierre y resumen al usuario.

## Criterios de aceptación

- El SVG nuevo del logo SF no contiene `#040917` ni ningún negro, ni `<image>`; ≤ 4 rellenos; se
  ve limpio junto al original (mirado de verdad, no supuesto). PDF sin imágenes incrustadas.
- La carpeta del Escritorio ya no existe; la app y Syncthing usan `telazocraft\biblioteca`; los
  dos servidores aparecen; los servidores nuevos se crearían en `biblioteca\servidores\`.
- Todas las verificaciones del bloque 4 en verde o con su motivo explicado.
- Todo subido como ItsRodryy, sin force, sin etiquetas, sin tocar proyectos del trabajo.

## Riesgos y vuelta atrás

- Borrar la carpeta antigua es irreversible: solo tras la comparación del bloque 3. Si algo falla
  antes, `ajustes.json` original está en `%TEMP%\ai_workspace_codex\telazocraft_ajustes_antes.json`
  y en Syncthing basta volver a poner la ruta antigua.
- Un commit incorrecto se corrige con un commit nuevo, nunca con force.
