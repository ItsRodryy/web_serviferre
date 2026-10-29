# Servi-Ferre web

Web en PHP del servicio técnico Servi-Ferre (antenas, videovigilancia, electricidad, iluminación). Contacto por teléfono y correo; sin formulario (el de Web3Forms se retiró el 29/10/2026).

Autoría: Adrián Rodríguez Rodríguez (GitHub: ItsRodryy). Ninguna IA figura como autora ni firma nada.

## Forma de trabajar

- Responde en español, breve y directo. Durante el trabajo da un aviso breve cada 30–45 segundos, nunca más de 60 en silencio: qué has comprobado, qué haces y qué falta.
- Antes de una tarea mediana o grande, indica en una línea el modelo en uso y el esfuerzo que recomiendas.
- No expongas el enfoque salvo al planificar. Si una duda cambia el resultado, pregunta (cinco como
  máximo, juntas) y espera; después trabaja sin paradas salvo un bloqueo real. Sin dudas, actúa.
- El chat prevalece sobre estos documentos. Si el usuario decide algo nuevo o cambia algo escrito,
  actualiza el documento afectado en el mismo trabajo, sin esperar a que lo pida.
- Comprueba rutas y datos reales antes de usarlos; no inventes. Di lo que no hayas podido comprobar.
- Git: lee sin pedir permiso (`status`, `diff`, `log`, `show`, `blame`, `branch --list`, `remote -v`). Antes de cualquier operación que cambie algo (`add`, `commit`, `push`, `pull`, `fetch`, `checkout`, `switch`, `restore`, `reset`, `stash`, `merge`, `rebase`, `tag`, crear o borrar ramas, `config`, `init`, `clone`, `clean` o publicación), di exactamente qué vas a hacer, pide permiso y espera. El permiso vale solo para esa operación.
- Al terminar: qué se hizo, cómo se verificó y qué queda. Sin volcados de consola.

## Proyecto

- Plataformas: Web (Apache + PHP).
- Tecnologías: PHP; HTML; CSS; JavaScript; Apache .htaccess; SQL.
- Las URL públicas no cambian: /, /servicios.php, /contacto.php, /css/estilos.css, /js/animaciones.js, /img/...
- Los .php de la raíz solo cargan su página; el contenido va en src/pages/ y el layout en src/layout/.
- src/ y database/ no deben ser accesibles por web (bloqueo en .htaccess).
- Comunica en castellano claro; explica los términos técnicos cuando haga falta.
- Distingue lo comprobado de lo supuesto, lo propuesto y lo pendiente.
- No digas que algo compila, funciona o está validado sin haberlo comprobado.
- Archivos y carpetas nuevos en minúsculas con guion bajo; respeta los nombres obligatorios y los existentes.
- Commits y push solo como ItsRodryy (nunca 2DAM-adrianrod493), mensaje «vX.Y.Z - Descripción» y sin firma de IA.
- Al acabar cada tarea, añade una fila en ai_workspace/registro_trabajo.md.
- Intocable sin orden expresa: img/ (imágenes originales); recursos_vinilado/originales/ (fuentes del material de rotulación).

## Verificación

Proporcional al riesgo: en cambios pequeños, solo lo afectado; todo en cambios grandes y al cerrar.

- `php -l <archivo.php>`
- `php -S localhost:8000`

## Estado, planes y memoria

- Estado: `ai_workspace/ESTADO.md`. Si existe `PLAN_ACTUAL.md`, léelo antes de retomar.
- Skills: `crear-plan` planifica y para; `ejecutar-plan` ejecuta (la orden aprueba el plan);
  `cerrar` verifica, compacta y archiva, o deja el traspaso si solo se pausa; `error` diagnostica;
  `progreso` (= `estado`) retoma y da el avance (`ai_workspace/progreso.md`). Mensajes: según
  `ai_workspace/contexto/personas.md`; nada está enviado sin confirmarlo el usuario.
- `ai_workspace/` guarda solo documentos breves y vigentes: ni copias de código, ni binarios, ni
  informes viejos, ni traspasos duplicados. Los temporales van fuera del proyecto. Los límites de
  tamaño están en `ai_workspace/configuracion.json`.
- Graphify: antes de abrir archivos grandes, `graphify explain <símbolo>` o `graphify affected <símbolo>`. `cerrar` lo actualiza.

## Documentación bajo demanda

Rutas dentro de `ai_workspace/`.

| Si vas a… | Lee |
|---|---|
| crear o cambiar interfaz | `contexto/estilo.md` |
