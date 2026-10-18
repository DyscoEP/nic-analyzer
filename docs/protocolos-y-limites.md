# Protocolos y capacidades

El alcance depende del protocolo, servicio y tráfico disponible.

| Protocolo | Capacidad | Alcance |
|---|---|---|
| LLDP y CDP | Identificación de dispositivos | Consulta identificadores, descripciones, puertos y direcciones anunciadas. |
| PROFINET DCP | Identificación de equipos | Consulta nombres, identificadores y parámetros de red presentes en los anuncios. No modifica la configuración. |
| PROFINET RT | Inspección básica | Muestra identificación de trama y contenido. No interpreta datos cíclicos ni IRT. |
| EtherNet/IP | Identificación y comunicación | Consulta identidad de equipos y mensajes admitidos. No interpreta todos los servicios CIP ni I/O implícita. |
| DNS, mDNS y LLMNR | Nombres y servicios | Consulta nombres, direcciones y registros de servicios admitidos. |
| DHCP, BOOTP y DHCPv6 | Parámetros de red | Revisa direcciones y opciones de configuración presentes en los mensajes admitidos. |
| ARP y NDP | Direcciones de red | Revisa asociaciones IP/MAC y anuncios de red. |
| SNMP | Información disponible | Consulta valores y direcciones en mensajes admitidos. No ofrece interpretación completa de todas las MIB ni descifra SNMPv3. |
| Modbus TCP | Inspección de mensajes | Consulta identificación, funciones, valores y errores admitidos. No sustituye una herramienta de configuración o programación. |
| S7comm y COTP | Inspección básica | Consulta información básica de comunicación. No interpreta variables, SZL, S7CommPlus ni comunicación cifrada. |
| BACnet/IP | Identificación y mensajes | Consulta anuncios I-Am e información básica. No cubre todos los servicios ni BACnet/SC. |
| OPC UA | Información de conexión | Consulta información básica de conexión. No interpreta todos los servicios ni descifra sesiones seguras. |
| MQTT | Mensajes y temas | Consulta campos y contenido de mensajes admitidos. Soporte parcial de MQTT 5; no descifra sesiones seguras. |
| HTTP y SSDP | Información de servicios | Consulta encabezados e información de servicios visibles. No descifra HTTPS ni interpreta todos los cuerpos o formatos. |

El contenido no interpretado puede revisarse en hexadecimal. No se descifra tráfico cifrado ni se configura el equipo inspeccionado.
