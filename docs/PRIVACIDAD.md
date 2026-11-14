# Privacidad y datos personales

Criterios del proyecto (31-10-2026). Cambiarlos exige una tarea en la cola y una nota aquí.

## Qué datos existen hoy
| Dato | Dónde | Quién lo ve | Personal |
|---|---|---|---|
| Contador de visitas: dos números agregados (total y por país) | `sk-atlas`, el servidor de sukima-labs (`busqueda_servicio.py`) | el autor | no: ni IP, ni cookies, ni identificadores |
| País de visita | se deduce en el navegador (zona horaria o idioma) y no se envía con identidad | nadie fuera del navegador | no |
| Marcas en el navegador (`localStorage`): `atlas_visita2` (hora de la última visita contada, para no contar dos veces a la misma persona en 12 h), `atlas_idioma` (idioma elegido), `atlas-tema` (modo de color: automático, claro u oscuro) y `atlas-vista` (ver en ancho completo o como en celular) | solo en el navegador de quien visita; no se envían a ningún sitio | nadie fuera del navegador | no: ni identificador ni datos de la persona |
| Búsquedas en vivo | el servicio las recibe para consultar la Biblioteca Digital | el servicio, sin registro | en principio no; no se guardan |
| Datos de personas de los mandatos | solo funciones públicas: titulares, nacionalidad y actos oficiales | público | sí, pero son información pública de la función |

## Criterios
1. **Solo información pública de la función.** Para la sección de relatores (T40): nombre del mandato, periodo, país de nacionalidad, actos oficiales y enlaces a la fuente. Nada de vida privada, contacto personal, redes sociales ni fotos sin fuente.
2. **Ninguna IP ni identificador en ningún registro.** Si algún día se registran búsquedas sin resultado (para solicitudes de verificación), solo se guardan agregadas, sin IP y sin el texto libre de la persona.
3. **Ninguna cookie ni almacenamiento propio** salvo que el autor lo decida y lo declare aquí. Declarado hoy: solo las dos marcas de `localStorage` de la tabla de arriba. Cookies, ninguna.
4. **Nada de terceros.** Ningún script, fuente o servicio externo que registre a quien visita (ver la regla gratis, abierto y privado en la cola).
5. **Derecho de rectificación:** quien aparezca en una ficha puede pedir corrección o retirada escribiendo en privado al autor (ver `SECURITY.md`).

## Decisiones tomadas (14-11-2026, aprobó Patricio, #244)
- **El historial no se reescribe.** La pantalla «Prepara tu EPU» (PR 67 y 69) sigue en el historial público, sin datos personales: se retiró para conservarla en privado. Reescribir con `git filter-repo` no la quitaría de la vista, porque GitHub guarda las referencias de esos PR (`refs/pull/67/head` y `refs/pull/69/head`) y no se pueden borrar desde el repositorio; en cambio, cambiaría todos los hashes y obligaría a volver a clonar cada copia.
- **No se registran las búsquedas sin resultado.** Sería una función nueva, y el alcance está cerrado (#337); la idea queda anotada allí. El criterio 2 se mantiene por si algún día se retoma.
