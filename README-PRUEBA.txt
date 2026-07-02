TabBuilder CLI — proyecto de prueba
====================================

Estructura (deben quedar como carpetas HERMANAS, no las muevas por separado):

  tabbuilder-workspace/
    TabBuilder/        <- extensión VS Code + Core (src/core)
    tabbuilder-cli/     <- la CLI, ya lista para correr (node_modules incluido)

Cómo probarla:

  cd tabbuilder-workspace/tabbuilder-cli
  node bin/tabbuilder.js new

  (o, si prefieres usar el binario declarado en package.json)
  npm link
  tabbuilder new

Requisitos ya cubiertos en este zip:
  - tabbuilder-cli/node_modules ya incluye @inquirer/prompts, commander, etc.
  - TabBuilder/node_modules ya incluye "archiver" (dependencia del Core, usada
    solo por la función de exportación a ZIP de la extensión).

Comandos disponibles:
  tabbuilder new         Genera un proyecto (nombre, lenguaje, framework,
                          arquitectura, base de datos, carpeta, instala
                          dependencias si el lenguaje las requiere).
  tabbuilder doctor       Verifica herramientas instaladas en el sistema.
  tabbuilder info         Muestra versión de la CLI y del Core compartido.
  tabbuilder templates    Lista frameworks y arquitecturas disponibles.
  tabbuilder config       Configura valores por defecto en ~/.tabbuilder/config.json.

No se incluye node_modules/.git de repositorio; si necesitas reinstalar:
  cd TabBuilder && npm install --omit=dev
  cd tabbuilder-cli && npm install
