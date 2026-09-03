# CLAUDE.md

Este archivo lo lee Claude cada vez que trabaja en esta carpeta, sin que se lo pidas.
Lo vas a llenar en la sesión. Por ahora trae solo las reglas que aplican desde el
primer minuto.

---

## 1. Qué es este proyecto y quién lo usa

*(Lo escribes tú en la sesión: dos líneas. Qué es la página, para quién es y cada
cuándo se usa.)*

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

*(La escribes tú en la sesión: con qué frase cierras lo que entregas y qué tiene
que ser cierto para que puedas publicarlo.)*

## 6. Cómo vuelvo a abrir esto

- El proyecto vive en `rs58nhgjhf-hub/mi-pagina-AVM-s7`, en GitHub.
- Se abre pidiéndole a Claude una sesión sobre este repo; no hace falta descargarlo.
- La página publicada está en la liga que da Netlify. *(Pendiente: todavía no se
  ha conectado Netlify a este repositorio.)*
- La base de datos está en supabase.com, en el proyecto **curso-S7claude-**,
  región us-east-1. Su dirección es `https://aheqqfzgfgjxwylupmrd.supabase.co`.

> **Si la página deja de mostrar datos después de una semana sin usarla**, casi
> siempre es que el proyecto gratuito de Supabase se pausó. Se despierta con el
> botón **Resume project**.
