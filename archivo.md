Elabora un documento en markdown que incluya lo siguiente:

El código del diagrama de secuencia.

```mermaid
sequenceDiagram
participant cliente
participant interfazCajero
participant lectorTarjeta
participant cuentaBancaria


%% enchufar tarjeta
activate cliente
cliente ->> lectorTarjeta: Insertamos tarjeta
activate lectorTarjeta
lectorTarjeta ->> interfazCajero: leyendo tarjeta
deactivate lectorTarjeta
interfazCajero ->> cliente: Introduzca el pin
cliente ->> interfazCajero: envia el pin
deactivate cliente
activate interfazCajero
interfazCajero ->> cuentaBancaria: comprueba el pin
activate cuentaBancaria
cuentaBancaria ->> interfazCajero: confirma el pin
deactivate cuentaBancaria



%% realizar operaciones sobre tarjeta
interfazCajero ->> cliente: pregunta cuanto dinero quiere sacar
activate cliente
cliente ->> interfazCajero: introduce la cantidad a extraer
deactivate cliente
interfazCajero ->> cuentaBancaria: consulta saldo
activate cuentaBancaria
cuentaBancaria ->> interfazCajero: confirma que se puede quitar
deactivate cuentaBancaria
interfazCajero ->> interfazCajero: saca el dinero

%% pasos finales
interfazCajero ->> lectorTarjeta: extrae tarjeta
deactivate interfazCajero
activate lectorTarjeta
lectorTarjeta ->> cliente: recoge el dinero y tarjeta
deactivate lectorTarjeta
activate cliente
deactivate cliente
```

Descripción del diagrama elaborado.

El primera paso sería insertar la tarjeta

El segundo paso sería que la interfaz del cajero diga algo de leyendo tarjeta

El tercero sería que te pida introducir el pin

El cuarto sería que tu introduzcan el pin y lo envies

El quinto es la interfaz grafica contrasta tu pin contra la cuenta bancaria

El sexto si es correcto te permite hacer la operación de quitar saldo

El septimo te pregunta cuanto dinero quieres

El octavo indicas la cantidad

El noveno es que consulta la cantidad introducidad contra el saldo de tu cuenta
bancaria

El decimo confirma que tu saldo no se queda en negativo y te devuelve el mensaje de todo correcto en la interfaz

El undecimo paso consistiría en que la interfaz del cajero empieza quitar dinero

El duodecimo es que la interfaz de cajero te saca la tarjeta del lector

El decimotercero es que tu recoges el dinero y la tarjeta