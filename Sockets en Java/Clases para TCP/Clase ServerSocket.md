Crea un **socket stream servidor** ([[Sockets Stream (TCP)]]).

Sus métodos más destacables:

| **Método / Constructor**                                | **Tipo de Retorno** | **Función**                                                                                                                                        |
| ------------------------------------------------------- | ------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ServerSocket()`                                        | `ServerSocket`      | Constructor básico de la clase. Crea un socket stream servidor.                                                                                    |
| `ServerSocket(int port)`                                | `ServerSocket`      | Crea un socket servidor que enlaza al puerto especificado.                                                                                         |
| `ServerSocket(int port, int maximo)`                    | `ServerSocket`      | Crea un socket servidor y lo enlaza al puerto local especificado; el parámetro `maximo` indica el número máximo de peticiones de conexión en cola. |
| `ServerSocket(int port, int maximo, InetAddress direc)` | `ServerSocket`      | Crea un socket de servidor y lo enlaza al puerto local especificado, indicando el máximo de conexiones y la dirección IP local.                    |
| `bind(SocketAddress bindpoint)`                         | `void`              | Asigna al socket creado una dirección y número de puerto determinado.                                                                              |
| `accept()`                                              | `Socket`            | El proceso servidor escucha y espera conexiones. Al llegar una, devuelve un nuevo objeto `Socket` conectado al cliente.                            |
| `getInputStream()`                                      | `InputStream`       | Obtiene un flujo de entrada (`InputStream`) para realizar operaciones de lectura de bytes desde el socket.                                         |
| `getOutputStream()`                                     | `OutputStream`      | Obtiene un flujo de salida (`OutputStream`) para realizar operaciones de escritura de bytes en el socket.                                          |
| `getLocalPort()`                                        | `int`               | Devuelve el puerto local al que está enlazado el `ServerSocket`.                                                                                   |
| `close()`                                               | `void`              | Cierra el socket.                                                                                                                                  |