Este tipo de socket está **orientado a la conexión**. Se emplea cuando se necesita comunicar siempre con el **mismo receptor**, para mantener el canal abierto y poder reutilizarlo para varios mensajes.

Al realizarse con el protocolo TCP, se garantiza la integridad tanto de los datos como de su orden de llegada.

Los procesos a comunicarse deben establecer antes una **conexión stream** (secuencia ordenada de información que fluye en ambas direcciones). 

Una de las aplicaciones hará el papel de **servidor** y la otra de **cliente**.


![[Pasted image 20260203013521.png]]
#### Proceso desde cliente
1. **Crear el socket**: Se le asigna un puerto (suele hacerlo el S.O.).
2. **Conexión** (connect): Se localiza el socket servidor (con su IP y puerto) y se crea el canal de comunicación.  
3. **Envío y recepción de mensajes**
4. **Cierre de conexión** (close)

#### Proceso desde servidor
1. **Crear el socket**
2. **Asignación de IP y puerto** (bind)
3. **Escucha** (listen): Configurar para que escuche por el puerto asginado y acepte conexiones.
4. **Aceptación de conexiones** (accept): Cuando llega una conexión, se crea un nuevo socket que se conecta al cliente, dejando así el socket servidor libre para otras conexiones.
5. **Envío / Recepción**: Se hace a través del nuevo socket creado en accept, no se usa el socket servidor.
6. **Cierre de conexión** (close): Se cierra el socket conectado al cliente. El socket servidor sigue activo en escucha.