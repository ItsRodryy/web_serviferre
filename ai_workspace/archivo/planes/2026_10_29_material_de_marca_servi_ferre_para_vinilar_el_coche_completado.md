# Material de marca Servi-Ferre para vinilar el coche

> **Estado:** COMPLETADO

## Objetivo

Dejar en `recursos_vinilado/` todo el material de logos de Servi-Ferre listo para un rotulista:
originales, PNG a máxima calidad, vectores SVG y PDF vectoriales. Sin fotos del coche ni furgonetas.

## Decisiones

- Nombres de carpetas y archivos: **minúsculas y guiones bajos**, nunca guiones medios ni mayúsculas.
- La carpeta actual `recursos-vinilado/` pasa a `recursos_vinilado/`; se borra `referencia-furgonetas/`.
- Solo trabajo local: sin commits ni push (la carpeta no está en git). Git solo lectura.
- Vectorizar = calcar los raster a SVG con colores planos (sin sombras, brillos ni degradados),
  que es lo que necesita el plotter de corte de vinilo.

## Intocables

- `C:\Users\adria\Downloads\`: solo **copiar** los 2 archivos indicados abajo. No abrir, mover ni
  copiar ningún otro archivo (hay documentos personales).
- `img/` de la web (se sirve por URL): solo lectura, no renombrar.
- Código de la web, `config/`, `storage/`, git.

## Fuentes (las únicas 4)

| Origen | Contenido | Tamaño | Nombre en `originales/` |
|---|---|---|---|
| `img/logo-serviferre-symbol.png` | Símbolo «SF» con marco azul | 1200×1200 | `logo_simbolo_sf_web.png` |
| `img/logo-serviferre-horizontal.png` | «SERVI-FERRE» en blanco + «SERVICIO TECNICO» verde, fondo transparente | 1853×283 | `logo_horizontal_web.png` |
| `C:\Users\adria\Downloads\486114975_1259696812828009_8492919286634443231_n.jpg` | «SF» azul/verde con sombra negra + «SERVICIO TECNICO» | 2048×2048 | `logo_sf_servicio_tecnico.jpg` |
| `C:\Users\adria\Downloads\473993096_2069691540143080_3154596670757943753_n.jpg` | Tarjeta de visita: wordmark azul/verde, antena, cámara, servicios, 655 606 926, MANUEL JESUS, servi-ferre@hotmail.com | 847×478 | `tarjeta_visita.jpg` |

Colores medidos: azul web `#2913B0`, verde web `#76BC34`; logo SF descarga: azul `#0735E0`,
verde `#35A813`, negro `#040917`; tarjeta: azul oscuro `#081C70`.

## Estructura final

```text
recursos_vinilado/
|-- leeme.txt
|-- originales/          # las 4 fuentes copiadas sin tocar, renombradas
|-- vectores/            # .svg
|-- pdf/                 # .pdf vectoriales + catalogo_serviferre.pdf
`-- png_alta_calidad/    # .png renderizados desde los SVG, fondo transparente
```

Piezas (cada una en `vectores/*.svg`, `pdf/*.pdf` y `png_alta_calidad/*.png`):

1. `logo_simbolo_sf` — símbolo SF de la web, sin el marco difuminado.
2. `logo_sf_servicio_tecnico` — logo SF de la descarga con «SERVICIO TECNICO», colores planos,
   contorno negro sólido en vez de sombra difusa.
3. `logo_horizontal_color` — wordmark «SERVI-FERRE» azul + «SERVICIO TECNICO» verde (para fondo
   blanco, el coche). Fuente: el PNG web recoloreando el blanco a azul, usando la tarjeta como
   referencia visual del color.
4. `logo_horizontal_blanco` — igual que el web: blanco + verde (para fondos oscuros).
5. `tarjeta_visita` — tarjeta completa vectorizada (textos e iconos), como referencia de datos.
6. `icono_antena` e `icono_camara` — iconos de la tarjeta sueltos, en negro.

## Bloques

1. [HECHO] Preparación: Python y las cinco dependencias disponibles; temporales en %TEMP%/serviferre_vinilo/.
2. [HECHO] Carpeta renombrada y limpia; cuatro fuentes copiadas y las dos referencias de ruta actualizadas.
3. [HECHO] Siete piezas recortadas, ampliadas ×4 con LANCZOS y cuantizadas a colores planos sobre transparencia.
4. [HECHO] Siete SVG trazados con vtracer, spline, filtro de motas y paletas exactas; ajuste visual final en marcha.
5. [HECHO] Siete PDF vectoriales proporcionales y catalogo de siete paginas con nombres y HEX.
6. [HECHO] Siete PNG RGBA transparentes renderizados desde los SVG, lado mayor 6000 px.
7. [HECHO] leeme.txt: piezas, fondos, paletas, contacto y limitaciones del calco.
8. [HECHO] Criterios automaticos y comparacion visual de las siete piezas superados; PHP sin errores y servidor probado.

Siguiente paso: cerrar, actualizar estado y archivar el plan completado.

## Pruebas y criterios de aceptación

- Todos los nombres bajo `recursos_vinilado/` cumplen `^[a-z0-9_]+(\.[a-z0-9]+)?$`.
- No queda `recursos-vinilado/` ni ninguna foto de coches/furgonetas.
- Cada SVG: abre sin error, sin `<image>`, ≤ 6 colores de relleno.
- Cada PDF de `pdf/`: sin imágenes incrustadas (`pypdf`: página sin `/XObject` de tipo `/Image`).
- Cada PNG: lado mayor ≥ 6000 px, modo RGBA.
- Comparación visual: renderizar cada SVG pequeño y ponerlo junto al original; la forma y el texto
  deben coincidir (mirarlo, no suponerlo).
- `git status` del proyecto igual que antes salvo la carpeta (no rastreada).

### Resultado comprobado

- Nombres: 27 archivos y todas las carpetas cumplen el patron; no queda la carpeta antigua ni fotos de vehiculos en el material.
- SVG: siete abiertos y renderizados, viewBox, curvas, sin rasters ni fuentes, 1 a 3 rellenos exactos de paleta.
- PDF: ocho, sin /Image incluso dentro de /Form; catalogo de siete paginas con nombre y HEX.
- PNG: siete RGBA transparentes, lado mayor exactamente 6000 px.
- Visual: las siete piezas vistas junto a su fuente. Formas y textos conservados; letras pequenas y rayitas/huecos de camara simplificados; leves irregularidades en bordes y transicion azul del SF. Sombras y degradados eliminados segun el plan.
- Git antes del cierre: status identico al inicial salvo recursos_vinilado/ en lugar de recursos-vinilado/. El cierre anade unicamente la documentacion exigida por la skill. Sin operaciones de escritura en Git.
- Verificacion web: 17 archivos PHP sin errores; php -S localhost:8000 arranca y escucha, luego detenido sin peticiones HTTP ni sesiones nuevas. No cambio codigo; no procede actualizar Graphify.

## Riesgos y vuelta atrás

- Calco imperfecto en letras pequeñas de la tarjeta: aceptable como referencia; avisar.
- Si algo sale mal: `originales/` conserva las fuentes y las de `img/` y Descargas no se tocan;
  basta borrar `recursos_vinilado/` y repetir.
