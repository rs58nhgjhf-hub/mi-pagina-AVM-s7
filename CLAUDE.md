# CLAUDE.md

Este archivo lo lee Claude cada vez que trabaja en esta carpeta, sin que se lo pidas.
Está lleno. Si algo de aquí deja de ser cierto, se corrige aquí antes de seguir
trabajando.

---

## 1. Qué es este proyecto y quién lo usa

Es un buzón de sugerencias publicado en internet. Quien entra deja su nombre, su
mensaje y, si quiere, una calificación del buzón, y ve lo que han escrito los demás.

Lo usa cualquiera: no pide contraseña ni cuenta, basta tener la liga. Sin frecuencia
fija, se usa cuando alguien tiene algo que decir.

## 2. De dónde sale cada cifra

Los datos de esta página viven en una tabla de Supabase llamada `registros`.
Ninguna cifra ni ningún texto que se muestre se escribe a mano en el HTML: todo
sale de esa tabla o de lo que la persona escriba en el formulario.

La tabla `registros` tiene estas columnas:

| Columna | Tipo | Quién la llena |
|---|---|---|
| `id` | número consecutivo | la base, sola |
| `nombre` | texto, obligatorio | la persona, en el formulario |
| `mensaje` | texto, obligatorio | la persona, en el formulario |
| `creado_en` | fecha y hora | la base, sola, al momento de guardar |
| `calificacion` | texto, opcional | la persona, en el formulario |

`calificacion` solo acepta tres palabras, `excelente`, `bueno` o `malo`, y puede
quedar vacía. La base rechaza cualquier otra cosa; no es una validación de la
página, es una restricción de la tabla.

Permisos de la tabla para quien entra a la página: puede **leer** y puede
**agregar** renglones. No puede modificar, ni borrar, ni vaciar. Eso no es un
acuerdo de palabra: son los permisos que tiene la tabla en la base, y ahí está
comprobado.

Los datos de conexión están escritos dentro de `index.html`: la dirección del
proyecto y la llave publicable. No hay más lugares donde buscarlos.

## 3. Cómo quiero que trabajes aquí

- Antes de un cambio grande, dame el plan por escrito y espera mi visto bueno.
- Un cambio a la vez. Enséñame qué cambió antes de escribirlo.
- Trabaja siempre en una rama, nunca directo sobre `main`.
- No publiques a producción sin que yo lo pida: fusionar es una decisión mía.
- **Si tienes acceso a mi base de datos, enséñame el SQL antes de correrlo y espera mi
  respuesta.** Crear o borrar tablas, agregar o quitar columnas y cambiar permisos no se
  deshacen con una rama: en cuanto corren, ya está.

## 4. Lo que nunca debes hacer

- **Nunca escribas en esta carpeta una llave que empiece con `sb_secret_` o que
  diga `service_role`.** La única llave que puede estar aquí es la que empieza
  con `sb_publishable_`, que está hecha para andar a la vista.
- No inventes datos. Si algo no está en la tabla, que la página diga que no hay
  nada todavía, no un ejemplo.
- No borres el historial ni fuerces cambios sobre lo ya publicado.

## 5. Mi regla de verificación

Nada está entregado hasta que está fusionado y publicado. La frase con la que se
cierra un trabajo es **hecho pull y despliegue**.

Para poder decirla tienen que ser ciertas tres cosas: que el cambio esté fusionado
en `main`; que Netlify haya publicado un despliegue de ese mismo commit y haya
quedado en estado listo; y que lo que cambió se pueda comprobar en la página
publicada o en la tabla, con el dato a la vista. Comprobado quiere decir visto, no
supuesto.

## 6. Cómo vuelvo a abrir esto

- El proyecto vive en `rs58nhgjhf-hub/mi-pagina-AVM-s7`, en GitHub.
- Se abre pidiéndole a Claude una sesión sobre este repo; no hace falta descargarlo.
- La página publicada está en `https://mi-pagina-avm-s7.netlify.app`. El proyecto
  en Netlify se llama **mi-pagina-avm-s7** y está amarrado a este repositorio: cada
  cambio que llega a `main` se publica solo, sin oprimir nada.
- La base de datos está en supabase.com, en el proyecto **curso-S7claude-**,
  región us-east-1. Su dirección es `https://aheqqfzgfgjxwylupmrd.supabase.co`.

> **Si la página deja de mostrar datos después de una semana sin usarla**, casi
> siempre es que el proyecto gratuito de Supabase se pausó. Se despierta con el
> botón **Resume project**.

## 7. Sistema de diseño

Tres colores y una tipografía. No se agrega ninguno más sin que yo lo pida.

| Papel | Color | Dónde va |
|---|---|---|
| Azul | `#2b5f96` | botón de guardar, marca de la calificación, contorno de foco |
| Gris | `#f4f6f8` al fondo, `#dde3ea` en los bordes | fondo de la página y líneas que separan |
| Negro | `#1a2027` | todo el texto |

La tipografía es **Arial**, con `Helvetica, sans-serif` de respaldo por si el
aparato no la tiene.

En modo oscuro se conservan los mismos tres papeles con versiones aclaradas u
oscurecidas de esos colores, que ya están escritas en `index.html`. El azul es el
único acento: si algo necesita destacar, se destaca con azul, no con un color
nuevo.
