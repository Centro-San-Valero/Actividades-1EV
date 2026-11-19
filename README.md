# San Valero a la fresca · Un estreno en AWS

El viernes a las nueve de la noche, el patio de San Valero se convierte en un cine al aire libre. El proyector está reservado, las sillas están listas y los carteles ya llevan un código QR para visitar la web del festival. El jueves, durante el ensayo, Marta, la coordinadora, escanea uno con su móvil. La página no carga.

—En mi portátil funciona —dice uno de los desarrolladores.

—Estupendo —contesta Marta—. Mañana vienen doscientas personas. ¿A quién le dejamos el portátil?

Ahí entráis vosotros. Sois el equipo encargado de poner en marcha **cuatro aplicaciones en AWS Academy**. En **Cloud y DevOps** os ocuparéis del libro de visitas. En **Despliegue de Aplicaciones Web** tendréis tres encargos antes de que empiece la proyección.

## Cloud y DevOps

### GuestBook-App · El libro de visitas

El año pasado circuló un cuaderno por las filas para que el público dejara sus comentarios. Al terminar la noche, nadie sabía quién se lo había llevado. Esta vez, Marta quiere un libro de visitas digital que cualquiera pueda abrir desde su móvil.

**Vuestro encargo.** Desplegad [GuestBook-App](./GuestBook-App/) en AWS Academy con una **arquitectura de dos capas (2-tier) y alta disponibilidad (HA)**. En vuestro esquema, distinguid la capa web (PHP) de la capa de datos (MySQL o MariaDB). Mostrad cómo se distribuyen los recursos entre dos zonas de disponibilidad y cómo se recupera el servicio en cada capa ante un fallo.

**Prueba de estreno.** Una compañera escribe «Yo voto por una segunda sesión» desde su móvil. Durante el ensayo dejáis fuera de servicio una de las instancias web. Desde la misma URL, otro compañero debe poder leer ese mensaje y publicar su respuesta.

## Despliegue de Aplicaciones Web

### 1. Movie Review App · ¿Qué proyectamos el próximo viernes?

Mientras se forma la cola, Marta pregunta al público qué película recomendaría para la próxima sesión. Quiere que cada persona pueda proponer un título, puntuarlo y explicar por qué merece verse en pantalla grande.

**Vuestro encargo.** Desplegad [Movie-Review-App](./Movie-Review-App/) con **Docker** en AWS Academy.

**Prueba de estreno.** Una espectadora publica una reseña con su puntuación. Desde otro dispositivo, Marta filtra por el género de la película y encuentra la recomendación.

### 2. Temperaturas · ¿Patio o salón de actos?

A las siete, el conserje tiene que decidir dónde colocar las sillas. Si refresca demasiado, la sesión pasará al salón de actos. Marta quiere saber qué temperaturas se esperan en Zaragoza antes de darle una respuesta.

**Vuestro encargo.** Desplegad [Temperaturas-App](./Temperaturas-App/) con **Docker Compose** en AWS Academy.

**Prueba de estreno.** El conserje busca Zaragoza, selecciona el municipio y lee en pantalla la máxima y la mínima previstas. Con esos dos datos decide dónde preparar la proyección.

### 3. Website App · El QR de los carteles

Queda repetir la prueba que falló el jueves. Una visitante escanea el cartel desde la calle. Tiene que llegar a la web oficial del festival mediante un nombre de dominio y una conexión HTTPS válida.

**Vuestro encargo.** Publicad [Website-App](./Website-App/) en AWS Academy detrás de un **Application Load Balancer (ALB)**. Configurad el nombre de la web en **DNSExit** para que apunte al balanceador. En el ALB, configurad un *listener* HTTPS en el puerto 443 con un certificado válido para ese nombre y haced que envíe las peticiones a la aplicación.

> **Si no podéis usar DNSExit, pedidme el certificado.** Os indicaré qué nombre de dominio utilizar para la prueba.

**Prueba de estreno.** Marta abre desde su móvil vuestro dominio mediante HTTPS. La web del festival carga y el navegador reconoce el certificado como válido.

## Cinco minutos para el estreno

Son las 20:55. Esta vez, Marta le da el móvil a alguien que acaba de llegar. La visitante abre la web del cartel, lee una reseña, mira la temperatura y deja un mensaje en el libro de visitas. Otra persona lo lee desde la última fila.

*«La próxima vez, traed palomitas».*

Ya podéis apagar las luces.

