# Buzón de sugerencias

Página pública donde cualquiera deja su nombre, un mensaje y, si quiere, una calificación
del buzón entre excelente, bueno y malo, y ve lo que escribieron los demás. No pide cuenta
ni contraseña: basta la liga. Está publicada en https://mi-pagina-avm-s7.netlify.app

**De dónde salen los datos.** De la tabla `registros` de Supabase, en el proyecto
`curso-S7claude-`. Nada de lo que se ve está escrito a mano en el HTML. Quien entra puede
leer y agregar renglones; no puede modificar, borrar ni vaciar, y eso lo impone la base, no
la página. La dirección del proyecto y la llave publicable están dentro de `index.html`;
una llave que empiece con `sb_secret_` o diga `service_role` nunca va aquí.

**Qué hay en `.claude`.** El archivo `agents/revisor-antes-de-publicar.md`: un revisor que
se pide diciendo "revisa antes de publicar". Compara la rama contra `main` y reporta llaves
filtradas, cambios de más y código mejorable. No arregla nada, solo dice qué encontró.

**Para continuar.** Abre una sesión de Claude sobre este repositorio y lee `CLAUDE.md`
antes que nada: ahí están las reglas del proyecto y de dónde sale cada dato. Pide los
cambios en una rama, nunca sobre `main`. Al fusionar a `main`, Netlify publica solo.
