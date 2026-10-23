# Documentación de mi entorno de desarrollo · Práctica 2

**Luis Belmonte**
**URL de mi repositorio:https://github.com/bevil98k/Luis-Belmonte-V-lchez**

> Rellena cada apartado a medida que avanzas. Donde pone «pega aquí», copia el texto
> de la terminal (no hace falta captura). Escribe con tus palabras: no se valora la longitud,
> sino que se note que entiendes lo que has hecho.

---

## 1. Instalación de entornos (CE 2.a)

### 1.1. Entorno vacío (paso 3)

Resultado de `java -version` y `node -v` **antes** de instalar nada:

```
bash: java:command not found
bash: node:command not found
```

¿Por qué crees que aparece ese mensaje? (relaciónalo con la diapositiva «Problemas habituales del entorno»)
Que no esta instalado ni java ni node
> 

### 1.2. Después de la 1.ª reconstrucción (paso 5)

Resultado de `java -version`, `node -v` y `jupyter lab --version` **después**:

```
openjdk version "27" 2026-09-15
OpenJDK Runtime Environment Temurin-27+35 (build 27+35)
OpenJDK 64-Bit Server VM Temurin-27+35 (build 27+35, mixed mode, sharing)
v24.22.1
4.6.4
```

¿Qué líneas nuevas han aparecido en `devcontainer.json`? Explica con tus palabras qué hace cada una:

Cambiar de 0, a 1, supongo que de esa manera esta instalado el programa

### 1.3. Comparativa de los dos IDE (paso 6)

|                                         | Editor de GitHub Codespaces | JupyterLab |
|-----------------------------------------|-----------------------------|------------|
| ¿Libre o propietario?                   |Propietario                  |  Libre          |
| Licencia / empresa o comunidad          |GitHub/Microsoft.            | BSD de claúsulas           |
| ¿Tiene coste? ¿Con qué límites?         |La cuota es gratuita , pero si se supera se cobra por el uso| NO tiene coste de licencia, el coste depende del servidor              |
| ¿Se puede usar fuera de GitHub?         | VS code si, pero Codespaces necesita la infraestructura |Si, puede instalarse y ejecutarse localmente            |
| Lo que más me ha gustado                |Permite programar desde el navegador con el entorno ya preparado| Permite combinar explicaciones, código y resultados en un mismo documento |
| Lo que menos me ha gustado              |Depende de Internet y las cuotas pueden limitar el uso| No es tan cómodo para organizar proyectos grandes con muchos archivos |
| ¿Para qué tipo de trabajo lo elegiría?  |Para desarrollar proyectos completos desde cualquier ordenador|Para prácticas, análisis de datos, experimentos y aprendizaje paso a paso|

---

## 2. Módulos y extensiones (CE 2.b)

| Extensión | ¿Para qué sirve? | ¿Qué cambió al instalarla? | ¿La mantengo? ¿Por qué? |
|-----------|------------------|----------------------------|-------------------------|
| Extension Pack for Java |Sirve para programar, compilar y ejecutar aplicaciones Java desde VS Code. Incluye herramientas para depurar, gestionar proyectos y trabajar con Maven|Se activó el soporte para Java, aparecieron opciones para ejecutar y depurar archivos .java, y se pudieron detectar errores en el código|Sí, porque necesito Java para trabajar con el archivo Factura.java|
| Code Spell Checker      |Sirve para detectar errores ortográficos en los comentarios, textos y nombres escritos en el código|Empezó a señalar palabras posiblemente mal escritas y ofreció sugerencias de corrección|No, porque el corrector marca como errores palabras correctas en español: en un equipo de habla hispana molesta más de lo que ayuda|

¿Qué diferencia hay entre instalar una extensión **solo desde el panel** y añadirla **también a `devcontainer.json`**?

> Instalar una extensión solo desde el panel la instala únicamente en tu entorno actual. Si añades la extensión también a devcontainer.json, queda incluida en la configuración del proyecto y se instalará automáticamente para cualquier persona que reconstruya el contenedor.

---

## 3. Personalización y automatización (CE 2.c)

- **Default High Contrast** (paso 10) y por qué: Porque esta bien, y no es necesario instalarse una extension
- **Ajuste del proyecto** (paso 10). ¿Qué archivo se ha creado y qué contiene?
setting.json , un archivo con el tema visual

```
pega aquí el contenido de .vscode/settings.json
```
{
    "workbench.colorTheme": "Default High Contrast",
    "editor.formatOnSave": true
}

- **Atajo de teclado** (paso 11). ¿Qué acción, qué combinación y para qué te sirve?
Codespaces: Rebuild Container; sirve para reconstruir el contenedor de desarrollo usando de nuevo la configuración de devcontainer.json. 
- **Snippet** (paso 12). ¿Qué escribes y qué aparece? cabecera y aparece: 
/*
 * Archivo: Prueba.java
 * Autor/a: Luis Belmonte Vílchez
 * Fecha:   23/10/2026
 * Módulo:  Entornos de Desarrollo - DAW
 */
- **Automatización al crear el entorno** (paso 14). ¿Qué hace `postCreateCommand` y qué archivos/carpetas han aparecido después de reconstruir?
- **Tareas** (paso 13). ¿Cuántas tareas hay en `tasks.json` y qué hace cada una?
Java: compilar, empaquetar y 
TypeScript: compilar y 
Build completo (Java + TypeScript)
¿Qué parte de toda esta configuración es **personal** (solo para ti) y qué parte es **del proyecto** (la recibe cualquiera que abra el repositorio)?

> La parte personal es el tema visual que he elegido, el atajo de teclado y mis preferencias de uso del editor. Estas configuraciones solo me afectan a mí, salvo que las guarde dentro del repositorio.

La parte del proyecto es la configuración de devcontainer.json, las extensiones añadidas, etc.

---

## 4. Ejecutables de diferentes lenguajes en el mismo entorno (CE 2.e)

Salida completa de la tarea **Build completo** (paso 15):

```
=== FACTURA generada con Java 27 ===
Dominio web anual              12.00 EUR
Alojamiento web                59.90 EUR
Logotipo corporativo          150.00 EUR
-----------------------------------------
Base imponible                221.90 EUR
IVA (21 %)                     46.60 EUR
TOTAL                         268.50 EUR

=== FACTURA generada con Node.js v24.22.1 ===
Dominio web anual              12.00 EUR
Alojamiento web                59.90 EUR
Logotipo corporativo          150.00 EUR
-----------------------------------------
Base imponible                221.90 EUR
IVA (21 %)                     46.60 EUR
TOTAL                         268.50 EUR
```

| Lenguaje | Archivo fuente | Herramienta que lo traduce | Archivo generado | Cómo se ejecuta |
|----------|----------------|----------------------------|------------------|-----------------|
| Java       | `src/java/Factura.java` | `javac` y `jar` | `build/java/Factura.class` y `build/factura.jar` | `java -jar build/factura.jar` |
| TypeScript | `src/ts/factura.ts`     | `tsc` | `dist/factura.js` | `node dist/factura.js` (o `npm start`) |

**Opcional:** ¿has podido ejecutar los mismos archivos desde JupyterLab (paso 19)? ¿Por qué funciona en los dos IDE sin instalar nada más?

> No, porque no funciona

---

## 5. Sistema de actualizaciones (CE 2.d)

| Elemento | ¿Quién lo actualiza? | Modo (automático / manual / ninguno) | Qué he configurado yo |
|----------|----------------------|--------------------------------------|-----------------------|
| El editor de Codespaces | GitHub/Microsoft | Automático | No he fijado una versión; uso el editor que proporciona Codespaces. |
| Las extensiones         | VS Code y quienes publican cada extensión | Automático para sus actualizaciones; la instalación se repite al reconstruir el contenedor | He incluido `vscjava.vscode-java-pack` en `devcontainer.json`; no he fijado su versión. |
| Java                    | La característica Java de Dev Containers instala el JDK | Manual | He fijado Java en la versión 21 (`"version": "21"`); para cambiarla debo editar la configuración y reconstruir el contenedor. |
| Node.js                 | La característica Node.js de Dev Containers lo instala | Automático al crear o reconstruir el contenedor | He añadido la característica `ghcr.io/devcontainers/features/node:1`, sin fijar una versión. |
| Dependencias npm (lodash, typescript…) | Los mantenedores de los paquetes publican versiones; yo decido cuándo adoptarlas | Manual | `postCreateCommand` ejecuta `npm install`; las versiones están declaradas en `package.json` y bloqueadas en `package-lock.json`. Para actualizarlas debo cambiar las versiones y actualizar el lockfile. |

Versión de Java **antes** (paso 5) y **después** (paso 18):

``` Antes: openjdk version "27" 2026-09-15
OpenJDK Runtime Environment Temurin-27+35 (build 27+35)
OpenJDK 64-Bit Server VM Temurin-27+35 (build 27+35, mixed mode, sharing)
Despues: openjdk version "21" 2023-09-19 LTS OpenJDK Runtime Environment Microsoft-8425986 (build 21+35-LTS) OpenJDK 64-Bit Server VM Microsoft-8425986 (build 21+35-LTS, mixed mode, sharing)
```

Resultado de `npm outdated` (paso 17):

```
Package         Current    Wanted   Latest  Location                    Depended by
@types/lodash  4.14.202  4.14.202  4.17.27  node_modules/@types/lodash  Luis-Belmonte-V-lchez
@types/node    20.11.30  20.11.30   26.6.5  node_modules/@types/node    Luis-Belmonte-V-lchez
typescript        5.4.5     5.4.5    7.0.2  node_modules/typescript     Luis-Belmonte-V-lchez
```

Resultado de `npm audit` **antes** de actualizar lodash (solo el resumen final):

```
Package Current Wanted Latest Location Depended by @types/lodash 4.14.202 4.14.202 4.17.27 node_modules/@types/lodash plantilla-entorno-daw-ismael @types/node 20.11.30 20.11.30 26.6.5 node_modules/@types/node plantilla-entorno-daw-ismael lodash 4.17.20 4.17.20 4.18.1 node_modules/lodash plantilla-entorno-daw-ismael typescript 5.4.5 5.4.5 7.0.2 node_modules/typescript plantilla-entorno-daw-ismael
```

Resultado de `npm audit` **después**:

```
found 0 vulnerabilities
```

**Mi política de actualizaciones**: si este entorno lo usara un equipo de 5 personas durante todo el curso, ¿qué dejarías en automático y qué fijarías a mano? Justifícalo.

> Dejaría automáticas las actualizaciones del editor de Codespaces y aplicaría pronto las actualizaciones de seguridad. En cambio, fijaría las versiones de Java y Node.js y mantendría bloqueadas las dependencias npm en el archivo de bloqueo para que las cinco personas trabajemos con las mismas versiones durante el curso. Revisaría las actualizaciones de herramientas y dependencias periódicamente; antes de incorporarlas, comprobaría que las compilaciones y pruebas sigan funcionando y actualizaría la configuración del proyecto para que el cambio sea igual para todo el equipo.


---

## 6. Incidencias

Anota cualquier problema que hayas tenido y cómo lo resolviste (también si usaste un fragmento completo).

>Al guardar entorno.md, VS Code avisó de que el archivo en disco era más reciente que el que tenía abierto. Para no perder los cambios, comparé las dos versiones y conservé la más reciente. No utilicé ningún fragmento completo.

## 7. Reflexión final

¿Qué ventaja tiene describir el entorno «como código» frente a instalar cada programa a mano en tu ordenador? Piensa en un equipo con Mac y Windows.

> Describir el entorno como código permite que todo el equipo use las mismas herramientas y versiones sin instalarlas una por una. Así, una persona con Mac y otra con Windows pueden abrir el proyecto y obtener un entorno equivalente, reduciendo errores de configuración y facilitando reproducirlo si hay que reinstalarlo o cambiar de ordenador
