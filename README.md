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

#### Contenido del xml a firmar

El xml debe enviarse con el nodo raíz de la operación a realizar (altaDoda, eliminarDoda ó modificarDoda), ejemplo:

```xml
<altaDoda>
    <dodas>
        ...
    </dodas>
</altaDoda>
```

#### Ejemplo de envío

```xml
<urn:firmar soapenv:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">
    <documento xsi:type="xsd:string">PGV...</documento>
    <cadenaOriginal xsi:type="xsd:string">fHw...</cadenaOriginal>
    <key xsi:type="xsd:string">MIIC...</key>
    <cer xsi:type="xsd:string">MIIES...</cer>
    <password xsi:type="xsd:string">MTIzNDU2Nzhh</password>
</urn:firmar>

```

### Respuesta

Campo|Tipo|Descripción
--- | --- | ---
**ConError** | Boleano | Indica si hubo algun error en el servicio
**mensaje** | string en base 64 | Resultado de la operación
**documento** | string en base 64 | El xml sellado y firmado

#### Ejemplo de respuesta correcta
```xml
<ns1:firmarResponse xmlns:ns1="urn:trafico">
    <ObjetoRespuestaFrimarDoda xsi:type="tns:RespuestaFrimarDoda">
    <ConError xsi:type="xsd:boolean">false</ConError>
    <mensaje xsi:type="xsd:string">correcto</mensaje>
    <documento xsi:type="xsd:string">Cjxkb2...</documento>
    </ObjetoRespuestaFrimarDoda>
</ns1:firmarResponse>
```