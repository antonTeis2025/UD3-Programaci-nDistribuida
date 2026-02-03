Se emplea para **representar una dirección IP** como objeto en java. Cuenta con ``Inet4Address`` para ipv4 y ``Inet6Address`` para ipv6.

Sus métodos principales son:

|**Método**|**Tipo de Retorno**|**Función**|
|---|---|---|
|`getLocalHost()`|`InetAddress`|Devuelve un objeto `InetAddress` que representa la dirección IP de la máquina donde se está ejecutando el programa. Puede lanzar la excepción `UnknownHostException`.|
|`getByName(String host)`|`InetAddress`|Devuelve un objeto `InetAddress` que representa la dirección IP de la máquina que se especifica como parámetro (`host`). Este parámetro puede ser el nombre de la máquina, un nombre de dominio o una dirección IP. Puede lanzar la excepción `UnknownHostException`.|
|`getAllByName(String host)`|`InetAddress[]`|Devuelve un array de objetos de tipo `InetAddress`. Este método es útil para averiguar todas las direcciones IP que tenga asignada una máquina en particular. Puede lanzar la excepción `UnknownHostException`.|
|`getHostAddress()`|`String`|Devuelve la dirección IP de un objeto `InetAddress` en forma de cadena.|
|`getHostName()`|`String`|Devuelve el nombre del host de un objeto `InetAddress`.|
|`getCanonicalHostName()`|`String`|Obtiene el nombre canónico completo de un objeto `InetAddress` (suele ser la dirección real del host).|