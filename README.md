# Servicios DODA

La url para acceder al servicio es la siguiente:

https://trafico.io/aduanet/webservices/doda.php?wsdl

El cual ofrece el siguiente metodo:

## firmar

Firma y sella un xml de doda, recibe los siguientes datos:

Campo|Tipo|Descripción
--- | --- | ---
**documento** | string en base 64 | El xml a firmar
**cadenaOriginal** | string en base 64 | Se define solo en el caso de firmar un doda de eliminacion
**key** | string en base 64 | El contenido del archivo key
**cer** | string en base 64 | El contenido del archivo cer
**password** | string en base 64 | La contraseña de la llave privada