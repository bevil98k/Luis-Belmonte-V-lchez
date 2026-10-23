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
pega aquí
```

| Lenguaje | Archivo fuente | Herramienta que lo traduce | Archivo generado | Cómo se ejecuta |
|----------|----------------|----------------------------|------------------|-----------------|
| Java       | `src/java/Factura.java` |   |   |   |
| TypeScript | `src/ts/factura.ts`     |   |   |   |

**Opcional:** ¿has podido ejecutar los mismos archivos desde JupyterLab (paso 19)? ¿Por qué funciona en los dos IDE sin instalar nada más?

> 

---

## 5. Sistema de actualizaciones (CE 2.d)

| Elemento | ¿Quién lo actualiza? | Modo (automático / manual / ninguno) | Qué he configurado yo |
|----------|----------------------|--------------------------------------|-----------------------|
| El editor de Codespaces |   |   |   |
| Las extensiones         |   |   |   |
| Java                    |   |   |   |
| Node.js                 |   |   |   |
| Dependencias npm (lodash, typescript…) |   |   |   |

Versión de Java **antes** (paso 5) y **después** (paso 18):

```
pega aquí
```

Resultado de `npm outdated` (paso 17):

```
pega aquí
```

Resultado de `npm audit` **antes** de actualizar lodash (solo el resumen final):

```
pega aquí
```

Resultado de `npm audit` **después**:

```
pega aquí
```

**Mi política de actualizaciones**: si este entorno lo usara un equipo de 5 personas durante todo el curso, ¿qué dejarías en automático y qué fijarías a mano? Justifícalo.

> 

---

## 6. Incidencias

Anota cualquier problema que hayas tenido y cómo lo resolviste (también si usaste un fragmento completo).

> 

## 7. Reflexión final

¿Qué ventaja tiene describir el entorno «como código» frente a instalar cada programa a mano en tu ordenador? Piensa en un equipo con Mac y Windows.

> 
