# Práctica 1 de SAD · SecureCorp — Respuestas

**Nombre y apellidos:**
**Usuario:**

Responde con tus palabras, en 1-3 líneas. En la defensa te preguntaré lo mismo en voz alta.

**Contraseñas que has usado** (solo porque es un laboratorio; en una empresa, jamás en un fichero):

- Tu usuario: Hector2026
- mtorres: Marta2026

---

**1. (A1)** ¿Quién es el `issuer` de tu `ca.crt`? ¿Hasta qué fecha es válido? ¿Por qué el `subject`
y el `issuer` de la CA son iguales y los de `ldap.crt` no?

-El issuer es hmortej
-Tiene una duración de 3650 días
-


**2. (A3)** Pega el comando y el resultado de tus dos búsquedas:

```
a) miembros de rrhh:

dn: cn=rrhh,ou=groups,dc=securecorp,dc=local
member: uid=lromero,ou=people,dc=securecorp,dc=local
member: uid=mtorres,ou=people,dc=securecorp,dc=local

b) cn y mail de todas las personas:

dn: uid=lromero,ou=people,dc=securecorp,dc=local
cn: Lucia Romero
mail: lromero@securecorp.local

dn: uid=mtorres,ou=people,dc=securecorp,dc=local
cn: Marta Torres
mail: mtorres@securecorp.local

dn: uid=hmortej,ou=people,dc=securecorp,dc=local
cn: Hector Moreno
mail: hmortej@securecorp.local

```

**3. (A4)** ¿Por qué la clave `ldap.key` tiene que ser de `openldap` y tener permisos 600?


**4. (A4)** ¿Qué valor has puesto en `SLAPD_SERVICES` y por qué?


**5. (A4)** Antes de añadir `TLS_CACERT` en el cliente, `ldaps://` no funcionaba. ¿Por qué?


**6. (B3)** Pega la salida de `klist` con tus dos tickets. ¿Para qué sirve cada uno? ¿Ha viajado tu
contraseña por la red?

```
Ticket cache: FILE:/tmp/krb5cc_0
Default principal: hmortej@SECURECORP.LOCAL

Valid starting     Expires            Service principal
10/08/26 15:19:46  10/09/26 01:19:46  krbtgt/SECURECORP.LOCAL@SECURECORP.LOCAL
	renew until 10/15/26 15:19:46
10/08/26 15:20:45  10/09/26 01:19:46  host/web.securecorp.local@SECURECORP.LOCAL
	renew until 10/15/26 15:19:46

```

**7. (C)** En el `docker-compose.yml`, ¿qué diferencia hay entre `build:` e `image:`? ¿Qué
significa la línea `- "8081:80"` del servicio `phpldapadmin`?


**8. (C)** ¿Por qué en la máquina `web` no has tenido que escribir a mano `TLS_CACERT`, y en el
cliente sí? ¿Qué pasaría con esa línea del cliente si hicieras `./lab.sh reset`?

