# Servi-Ferre web

Web PHP estatica/dinamica sencilla para Servi-Ferre.

## Estructura

```text
.
|-- index.php                  # Entradas publicas que mantienen las URLs actuales
|-- servicios.php
|-- tecnologias.php
|-- empleados.php
|-- contacto.php               # Telefono y correo (sin formulario)
|-- css/                       # Estilos publicos
|-- js/                        # Scripts publicos
|-- img/                       # Imagenes publicas
|-- src/
|   |-- pages/                 # Contenido de paginas
|   |-- layout/                # Header y footer
|   |-- helpers/               # Utilidades compartidas
|   `-- auth/                  # Entradas auxiliares de autenticacion
|-- database/                  # SQL y material de base de datos
`-- recursos_vinilado/         # Logos y material para rotular el coche
```

Las rutas publicas se mantienen igual: `/`, `/servicios.php`, `/contacto.php`,
`/css/estilos.css`, `/js/animaciones.js` e `/img/...`.

## Desarrollo local

```powershell
php -S localhost:8000
```

Abre `http://localhost:8000` en el navegador.
