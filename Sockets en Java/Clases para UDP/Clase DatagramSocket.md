Da **soporte a sockets** que envían y reciben datagramas UDP ([[Clase DatagramPacket]]). 

### Constructores

| **Constructor**                            | **Tipo de Retorno** | **Función**                                                                                         |
| ------------------------------------------ | ------------------- | --------------------------------------------------------------------------------------------------- |
| `DatagramSocket()`                         | `DatagramSocket`    | Construye un socket para datagramas. El sistema elige un puerto disponible de los que están libres. |
| `DatagramSocket(int port)`                 | `DatagramSocket`    | Construye un socket para datagramas y lo conecta (vincula) al puerto local especificado.            |
| `DatagramSocket(int port, InetAddress ip)` | `DatagramSocket`    | Permite especificar el puerto local y la dirección IP local a la que se asociará el socket.         |

### Métodos

| **Método**                               | **Tipo de Retorno** | **Función**                                                                                                                                                                                                                   |
| ---------------------------------------- | ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `receive(DatagramPacket paquete)`        | `void`              | Recibe un `DatagramPacket` del socket y llena el objeto `paquete` con los datos recibidos (mensaje, longitud, origen). Puede lanzar `IOException`.                                                                            |
| `send(DatagramPacket paquete)`           | `void`              | Envía un `DatagramPacket` a través del socket. El argumento `paquete` ya contiene el mensaje y su destino. Puede lanzar `IOException`.                                                                                        |
| `connect(InetAddress address, int port)` | `void`              | Conecta el socket a un puerto remoto y a una dirección IP concretos. El socket solo podrá enviar y recibir mensajes a/desde esa dirección específica.                                                                         |
| `close()`                                | `void`              | Cierra el socket.                                                                                                                                                                                                             |
| `getLocalPort()`                         | `int`               | Devuelve el número de puerto en el host local al que el socket está enlazado. `-1` si el socket está cerrado y `0` si no está enlazado.                                                                                       |
| `getPort()`                              | `int`               | Devuelve el número de puerto al que está conectado el socket (remoto), o `-1` si no está conectado.                                                                                                                           |
| `setSoTimeout(int timeout)`              | `void`              | Permite establecer un tiempo de espera límite (en milisegundos). El método `receive` se bloqueará durante el tiempo fijado. Si no se reciben datos, lanza la excepción `InterruptedIOException` (o `SocketTimeoutException`). |