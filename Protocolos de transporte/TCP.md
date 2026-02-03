Se encarga de dividir los mensajes recibidos a nivel de aplicación. En el lado del **emisor**, **crea los paquetes y los envía a nivel de internet**; y en el lado del **receptor**, **combina los paquetes y forma el mensaje para la aplicación**. 

Concretamente el protocolo TCP se emplea cuándo queremos garantizar que la información llegue **íntegra** (sin perderse) y en **el mismo orden que se envió**.

---

El protocolo TCP está **orientado a conexión**. El canal permanece abierto para que se envíen varios mensajes por él. 

1. **Establecimiento de conexión**: Se crea el canal de comunicación (que se mantiene abierto hasta que alguien lo cierre).
2. **Envío del mensaje**: Tantas veces como se desee.
3. **Cierre de conexión**: Cuando se quiere terminar la comunicación.