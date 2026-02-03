No están orientados a conexión, se usan para **enviar mensajes (datagramas) a múltiples receptores.** 

**Un mismo socket** se puede usar para **enviar mensajes a distintos receptores**, especificando sus IP y puertos destino en cada operación send. **No hay un canal privado permanente** entre emisor y receptor. El close se hace solo cuando ya no se desea seguir usando el socket.

Se usa **un canal temporal para cada envío**. Estos no son fiables ni aseguran el orden de llegada, ya que hacen uso del protocolo **UDP**. 

**No se diferencia claramente el papel de cliente / servidor**.

![[Pasted image 20260203014514.png]]
#### Secuencia de operaciones 
1. **Crear el socket**
2. **Asignar IP y puerto** (bind): Si se quieren recibir mensajes es importante especificarlos para que los emisores puedan localizarlo. 
3. **Envío y recepción de datagramas** (send / recieve): Send necesita la IP y puerto del destinatario.
4. **Cierre de conexión** (close)