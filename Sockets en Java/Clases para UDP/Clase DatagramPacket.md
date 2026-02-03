
Es la **abstracción** de un datagrama (paquete) del protocolo [[UDP]].
### Constructores

| **Constructor**                                                         | **Tipo de Retorno** | **Función**                                                                                                                                                                      |
| ----------------------------------------------------------------------- | ------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `DatagramPacket(byte[] buf, int length)`                                | `DatagramPacket`    | Constructor para datagramas **recibidos**. Especificamos la cadena de bytes en la que se alojará el mensaje y la longitud del mismo.                                             |
| `DatagramPacket(byte[] buf, int length, InetAddress address, int port)` | `DatagramPacket`    | Constructor para el **envío** de datagramas. Especificamos la cadena de bytes a enviar, la longitud de la misma, además el host (dirección IP) y el número de puerto de destino. |

### Métodos

|**Método**|**Tipo de Retorno**|**Función**|
|---|---|---|
|`getAddress()`|`InetAddress`|Devuelve la dirección IP del host al cual se envía el datagrama o del que se recibió el datagrama.|
|`getData()`|`byte[]`|Obtiene el mensaje contenido en el datagrama, tanto del datagrama recibido como del enviado.|
|`getLength()`|`int`|Obtiene la longitud de los datos a enviar o recibir.|
|`getPort()`|`int`|Obtiene el número de puerto de la máquina remota a la que se le va a enviar el datagrama o de la que se recibió.|
|`setAddress(InetAddress addr)`|`void`|Establece la dirección IP de la máquina a la que se le envía el datagrama. Se usa para construir el paquete a enviar.|
|`setData(byte[] buf)`|`void`|Establece el buffer de datos para el paquete datagrama. Se usa para construir el paquete a enviar.|
|`setLength(int length)`|`void`|Almacena la longitud de este paquete. Se usa para construir el paquete a enviar.|
|`setPort(int port)`|`void`|Almacena el número de puerto del host remoto al que este datagrama se enviará. Se usa para construir el paquete a enviar.|