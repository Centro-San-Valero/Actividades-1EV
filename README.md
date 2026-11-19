# San Valero a la fresca · Un estreno en AWS

El viernes a las nueve de la noche, el patio de San Valero se convierte en un cine al aire libre. El proyector está reservado, las sillas están listas y los carteles ya llevan un código QR para visitar la web del festival. El jueves, durante el ensayo, Marta, la coordinadora, escanea uno con su móvil. La página no carga.

—En mi portátil funciona —dice uno de los desarrolladores.

—Estupendo —contesta Marta—. Mañana vienen doscientas personas. ¿A quién le dejamos el portátil?

Ahí entráis vosotros. Sois el equipo encargado de poner en marcha **cuatro aplicaciones en AWS Academy**. En **Cloud y DevOps** os ocuparéis del libro de visitas. En **Despliegue de Aplicaciones Web** tendréis tres encargos antes de que empiece la proyección.

## Cloud y DevOps

### Guestbook App · El libro de visitas

El año pasado circuló un cuaderno por las filas para que el público dejara sus comentarios. Al terminar la noche, nadie sabía quién se lo había llevado. Esta vez, Marta quiere un libro de visitas digital que cualquiera pueda abrir desde su móvil.

**Vuestro encargo.** Montad `guestbook-app` en AWS Academy y comprobad el recorrido completo de un mensaje.

**Prueba de estreno.** Una compañera escribe «Yo voto por una segunda sesión» desde su móvil. Otro compañero abre el libro desde un equipo distinto. Cuando pueda leer el comentario, Marta dará el servicio por listo.

## Despliegue de Aplicaciones Web

### 1. Movie App · La película de esta noche

A media tarde llega la pregunta que más se repite en la entrada. «¿Qué película vais a poner?» La organización quiere enseñar la aplicación de películas al público, pero hasta ahora solo la ha visto funcionar en el ordenador de quien la preparó.

**Vuestro encargo.** Desplegad Movie App en un **contenedor Docker** en AWS Academy.

**Prueba de estreno.** Una persona del equipo abre la aplicación desde el navegador de otro dispositivo. Mientras tanto, otra ejecuta `docker ps` en el servidor e identifica el contenedor que atiende la petición y el puerto publicado.

### 2. Temperaturas · ¿Patio o salón de actos?

A las siete, el conserje tiene que decidir dónde colocar las sillas. Si refresca demasiado, la sesión pasará al salón de actos. Marta quiere consultar la temperatura antes de darle una respuesta. Justo entonces cambia el turno del equipo técnico. ¿Podrá la persona que entra poner en marcha la aplicación?

**Vuestro encargo.** Desplegad la aplicación de temperaturas con **Docker Compose** en AWS Academy. Dejad definidos en el fichero de Compose los servicios que necesita la aplicación.

**Prueba de estreno.** Un compañero del siguiente turno entra en la carpeta del proyecto y ejecuta:

```bash
docker compose up -d
docker compose ps
```

El compañero comprueba que los servicios están en marcha y abre la aplicación en el navegador para consultar la temperatura.

### 3. Website App · El QR de los carteles

Queda repetir la prueba que falló el jueves. Una visitante escanea el cartel desde la calle. Tiene que llegar a la web oficial del festival mediante un nombre de dominio y una conexión HTTPS válida.

**Vuestro encargo.** Publicad `website-app` en AWS Academy detrás de un **Application Load Balancer (ALB)**. Configurad el nombre de la web en **DNSExit** para que apunte al balanceador. En el ALB, configurad un *listener* HTTPS en el puerto 443 con un certificado válido para ese nombre y haced que envíe las peticiones a la aplicación.

> **Si no podéis usar DNSExit, pedidme el certificado.** Os indicaré qué nombre de dominio utilizar para la prueba.

**Prueba de estreno.** Marta abre desde su móvil la dirección `https://` de vuestro dominio. La web del festival carga y el navegador reconoce el certificado como válido.

## Cinco minutos para el estreno

Son las 20:55. Esta vez, Marta le da el móvil a alguien que acaba de llegar. La visitante abre la web del cartel, consulta la película, mira la temperatura y deja un mensaje en el libro de visitas. Otra persona lo lee desde la última fila.

*«La próxima vez, traed palomitas».*

Ya podéis apagar las luces.

