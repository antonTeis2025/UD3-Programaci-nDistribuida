Los sockets stream soportan envío de **cadenas de texto, clases primitivas de java y objetos**. Estos objetos que queramos transmitir mediante sockets, deben **implementar la interfaz `Serializable`**.
### Operaciones principales

- **Leer del socket**

Para ello tenemos que obtener su flujo de entrada.
```java
ObjectInputStream inObjeto = new ObjectInputStream( socket.getInputStream() );
```

- **Escribir en el socket**

Obtenemos el flujo de salida
```java
ObjectOutputStream outObjeto= new ObjectOutputStream( socket.getOutpuStream() );
```

### Atender múltiples clientes

Para poder atender a múltiples clientes **usando un solo servidor**, tendremos que emplear **hilos**. Cada cliente será atendido en un hilo. 

Para este modelado:
- Se crea **un solo servidor** ([[Clase ServerSocket]]) invocando el método ``accept`` para ponerlo en escucha.
- Al **recibir una conexión**, devuelve un objeto ``Socket`` ([[Clase Socket]]) que se usará para **crear un hilo que atienda al cliente**.
- Volver a **invocar el método `accept`** (habitualmente en bucle) para seguir en escucha.