Son más **simples y eficientes** que los sockets TCP, pero no garantizan la entrega de paquetes.

Se establecen dos roles: **emisor y receptor**. Entre ellos no se establece una conexión exclusiva, por lo que en el datagrama del emisor ha de ir especificada la IP y puerto del receptor. Después para contestarle, el receptor recoge la IP origen para saber a donde enviar la respuesta.

### Lado emisor

- **Construcción** del datagrama para enviar:
![[Pasted image 20260203173850.png]]
```java
DatagramPacket envio= new DatagramPacket(mensaje, mensaje.lenght,destino, port); 
DatagramSocket socket= new DatagramSocket(34567); 
socket.send(envio);
```

### Lado receptor

- **Crear socket** para recibir el datagrama
```java
DatagramSocket socket= new DatagramSocket(12345);
```
- **Construcción** del datagrama a recibir:
![[{F721717A-07AF-42D3-B714-2EB29C2F3D22}.png]]
```java
DatagramPacket recibo = new DatagramPacket(buffer, buffer.length); 

socket.receive(recibo); // recibo datagrama 

int bytesrecibidos = recibo.getLength(); 
String paquete = new String(recibo.getData());
 
System.out.println("número de bytes recibidos: " + bytesrecibidos);
System.out.println ("contenido del paquete: " + paquete.trim()); 
System.out.println("IP de origen: " + recibo.getAddress().getHostAddress()); 
System.out.println("Puerto origen del mensaje: "+ recibo.getPort()); 
System.out.println("Puerto destino del mensaje: " + socket.getLocalPort());
```