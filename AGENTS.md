# Servi-Ferre web

Web en PHP del servicio técnico Servi-Ferre (antenas, videovigilancia, electricidad, iluminación). Formulario de contacto enviado por Web3Forms.

Autoría: Adrián Rodríguez Rodríguez (GitHub: ItsRodryy). Ninguna IA figura como autora ni firma nada.

## Forma de trabajar

- Responde en español, breve y directo. Da un aviso breve al empezar cada fase (investigar, cambiar, verificar).
- Antes de una tarea mediana o grande, indica en una línea el modelo en uso y el esfuerzo que recomiendas.
- No expongas el enfoque salvo al planificar. Si una duda cambia el resultado, pregunta (cinco como
  máximo, juntas) y espera; después trabaja sin paradas salvo un bloqueo real. Sin dudas, actúa.
- El chat prevalece sobre estos documentos. Si el usuario decide algo nuevo o cambia algo escrito,
  actualiza el documento afectado en el mismo trabajo, sin esperar a que lo pida.
- Comprueba rutas y datos reales antes de usarlos; no inventes. Di lo que no hayas podido comprobar.
- Git permitido para el trabajo pedido; nunca reescribas el historial ni fuerces un push sin permiso.
- Al terminar: qué se hizo, cómo se verificó y qué queda. Sin volcados de consola.

## Proyecto

- Plataformas: Web (Apache + PHP).
- Tecnologías: PHP; HTML; CSS; JavaScript; Apache .htaccess; SQL.
- Las URL públicas no cambian: /, /servicios.php, /contacto.php, /css/estilos.css, /js/animaciones.js, /img/...
- Los .php de la raíz solo cargan su página; el contenido va en src/pages/ y el layout en src/layout/.
- src/, config/, storage/ y database/ no deben ser accesibles por web (bloqueo en .htaccess).
- Commits como ItsRodryy, nunca con la cuenta 2DAM-adrianrod493; mensaje «vX.Y.Z - Descripción».
- Intocable sin orden expresa: config/mail.php (claves del formulario); storage/sessions/ (sesiones generadas); img/ (imágenes originales); recursos-vinilado/ (logos para rotulación).

## Verificación

Proporcional al riesgo: en cambios pequeños, solo lo afectado; todo en cambios grandes y al cerrar.

- `php -l <archivo.php>`
- `php -S localhost:8000`

## Estado, planes y memoria

- Estado: `ai_workspace/ESTADO.md`. Si existe `PLAN_ACTUAL.md`, léelo antes de retomar.
- Skills: `crear-plan` planifica y para; `ejecutar-plan` ejecuta (la orden aprueba el plan);
  `cerrar` verifica, compacta y archiva, o deja el traspaso si solo se pausa; `error` diagnostica.
- `ai_workspace/` guarda solo documentos breves y vigentes: ni copias de código, ni binarios, ni
  informes viejos, ni traspasos duplicados. Los temporales van fuera del proyecto. Los límites de
  tamaño están en `ai_workspace/configuracion.json`.
- Graphify: antes de abrir archivos grandes, `graphify explain <símbolo>` o `graphify affected <símbolo>`. `cerrar` lo actualiza.

## Documentación bajo demanda

Rutas dentro de `ai_workspace/`.

| Si vas a… | Lee |
|---|---|
| crear o cambiar interfaz | `contexto/estilo.md` |
