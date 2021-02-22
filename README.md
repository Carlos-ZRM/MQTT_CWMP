# MQTT (Message Queuing Telemetry Transport Protocol )
MQTT notes
https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=mqtt

http://public.dhe.ibm.com/software/dw/webservices/ws-mqtt/mqtt-v3r1.html

Providing a lightweight publish/subscribe reliable messaging transport protocol suitable for communication in M2M/IoT contexts where a small code footprint is required and/or network bandwidth is at a premium. Is designed to support messaging transport from remote locations/devices involving small code footprints (e.g., 8-bit, 256KB ram controllers), low power, low bandwidth, high-cost connections, high latency, variable availability, and negotiated delivery guarantees. 

MQTT proporciona un protocolo de transporte de mensajes Publicar/Suscribir ligero y confiable para  comunicaciones Maquina a Maquina o Internet de las cosas donde se necesita "small code footprint " y /o los recursos de red son escasos. 

Las caracteristicas del protocolo incluyen: 

- Patron de mensajjes Publicar/Suscribir para proveeer una distribucion de mensajers uno a muchos y un desacoplamiento de aplicaciones 
- El transporte de mensajes es agnbostico al contenido útil del mensaje. 
- El uso de TCP/IP para proveer una red de conectividad de red basica 
- Tres calidades de servicio para la entreega de mensajes: 
  - **Cómo máximo una vez**   
  - **Al menos una vez**
  - **Exactamente una vez**

## Message format
 La cabecera para cada mensaje MQTT de tipo comando contiene una cabecera fija. ALgunos mensajes solo requieren un encabezado variable y un Mensaje util. 
 
 ### Cabezera fija
<div>
<table>
<thead>
  <tr>
    <th>Bit</th>
    <th>7</th>
    <th>6</th>
    <th>5 </th>
    <th>4 </th>
    <th>3</th>
    <th>2</th>
    <th>1</th>
    <th>0</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Byte 1</td>
    <td colspan="4">Message Type</td>
    <td>DUP flag</td>
    <td colspan="2">QoS level</td>
    <td>Retain</td>
  </tr>
  <tr>
    <td>Byte 2 </td>
    <td colspan="8">Remaining Length</td>
  </tr>
</tbody>
</table>
</div>