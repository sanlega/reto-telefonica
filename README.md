:rocket: INFO PARA PARTICIPAR EN EL PROCESO DE SELECCIÓN :rocket:

:page_facing_up: AQUÍ esta la presentación que ha utilizado José Luis en la explicación del reto con toda la info.
https://docs.google.com/presentation/d/16jAs5QXRdp5hM0rOLEXgMxLbOT4dukSL/edit?usp=sharing&ouid=104451871311555801960&rtpof=true&sd=true

:alarm_clock:  FECHA LÍMITE PARA LA ENTREGA :point_right:  DOMINGO 16 DE JULIO A LAS 22:42 HORAS

Sube tu solución a ESTE enlace:
https://telefonica-fundacion.typeform.com/42Madrid-Telf

:link: Enlaces de los grupos de Developers de Google que compartió Cecilio:

- https://developers.google.com/?hl=es-419
- https://developers.google.com/community/gdg?hl=es-419
- https://developers.google.com/community/gdsc?hl=es-419
- https://developers.google.com/community/experts?hl=es-419
- https://developers.google.com/womentechmakers

:people_hugging: Y, por último, los nombres y LinkedIn de las personas que han estado hoy en :42::

- Elena Parreño Turrión - Incorporación de Talento de Telefónica España
- Cecilio Peral - Google Cloud Customer Experience Lead
- Jose Maldonado - Google Cloud Customer Engineering Manager
- José Luis Robles Urquiza - Jefe Oficina Estrategia Tecnológica - Tecnología Digital - Canal Online Telefónica

# Arquitectura?

1. **Web App de Agente**: Los agentes interactuarán con los clientes a través de una interfaz web tipo chat. Puedes construir una aplicación web utilizando tecnologías como HTML, CSS y JavaScript, y utilizar un framework de desarrollo web como React.js o Angular.js. Esta aplicación web permitirá a los agentes recibir y enviar mensajes a través de una interfaz de chat.

2. **Google Cloud Pub/Sub**: Utiliza el servicio de Google Cloud Pub/Sub para implementar la comunicación asincrónica y los eventos entre los clientes y los agentes. Los mensajes enviados por los clientes de Telegram se publicarán en un tema (topic) de Pub/Sub, y los agentes se suscribirán a ese tema para recibir los mensajes. De manera similar, cuando los agentes envíen mensajes, se publicarán en otro tema de Pub/Sub, y los clientes estarán suscritos a ese tema para recibir los mensajes de respuesta.

5. **Cloud Functions**: Utiliza Cloud Functions de Google Cloud para crear funciones serverless que actuarán como controladores de eventos. Puedes crear una función que se active cada vez que se publique un mensaje en el tema de Pub/Sub correspondiente a los mensajes de los clientes de Telegram. Esta función recibirá el mensaje, realizará cualquier procesamiento necesario y luego enviará el mensaje a la interfaz web de los agentes utilizando un mecanismo de notificación en tiempo real como Firebase Cloud Messaging (FCM) o WebSockets. De manera similar, puedes tener otra función que se active cuando los agentes envíen mensajes y que publique los mensajes en el tema de Pub/Sub correspondiente para que los clientes de Telegram puedan recibirlos.

6. **Firebase Cloud Messaging o WebSockets**: Utiliza Firebase Cloud Messaging (FCM) o WebSockets para enviar notificaciones en tiempo real desde la función de Cloud Functions a la interfaz web de los agentes cuando se reciban nuevos mensajes de los clientes. Esto permitirá que los agentes vean los mensajes entrantes sin necesidad de actualizar la página manualmente.

7. **Google Cloud Firestore**: Utiliza Google Cloud Firestore para almacenar y sincronizar los mensajes entre los clientes y los agentes. Puedes utilizar Firestore para almacenar el historial de mensajes y para mantener la sincronización en tiempo real entre los diferentes clientes y agentes.

Esta arquitectura utiliza servicios de Google Cloud y está diseñada para ser escalable y autogestionada. Los eventos y la comunicación asincrónica se realizan a través de Pub/Sub, y las funciones serverless de Cloud Functions actúan como controladores de eventos para procesar los mensajes y enviar notificaciones en tiempo real. Firestore se utiliza para almacenar y sincronizar los mensajes entre los diferentes componentes.

Recuerda que esta es solo una propuesta y puedes adaptarla según tus necesidades específicas.
