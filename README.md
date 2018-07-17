# Servicios DODA

La url para acceder al servicio es la siguiente:

https://trafico.io/aduanet/webservices/doda.php?wsdl

El cual ofrece el siguiente metodo:

- **firmar** (**string** documento, **string** cadenaOriginal, **string** key, **string** cer, **string** password) donde:

* **documento** es el xml a firmar
* **cadenaOriginal** se define solo en el caso de firmar un doda de eliminacion
* **key** el contenido del archivo key
* **cer** el contenido del archivo cer
* **password** la contraseña de la llave privada

Todos estos parametros deben enviarse en base 64