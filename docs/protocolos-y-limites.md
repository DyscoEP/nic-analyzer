# Protocolos y límites · V1.1.1

Lectores propios bajo MIT. La presencia de un protocolo no implica decodificación completa de todos sus servicios. Los datos desconocidos se conservan en hexadecimal.


LLDP — Campos TLV
Management Address IPv4/IPv6, Chassis/Port ID, PROFINET Chassis MAC, TTL y descripciones. TLV organizacionales desconocidos quedan en hexadecimal.

PROFINET DCP — Bloques de descubrimiento
Identify/Get/Set/Hello: IP, máscara, gateway, MAC, tipo de dispositivo, nombre, vendor/device ID y rol. Solo interpreta tráfico observado; no envía DCP.

PROFINET RT — Cabecera
Frame ID y bytes. No decodifica datos cíclicos ni IRT.

CDP — Campos TLV
Device ID, plataforma, software, puerto, direcciones de red/administración, capacidades y VLAN. Requiere LLC/SNAP Cisco sobre Ethernet 802.3.

EtherNet/IP — ListIdentity y CPF/CIP parcial
Socket IPv4, fabricante ID (Rockwell ID 1), tipo, producto, revisión, serial y nombre en ListIdentity. RegisterSession, ListServices, CPF sockets, servicios CIP y ruta class/instance/attribute. Datos de respuesta CIP sin contexto de objeto permanecen hex; no interpreta todo CIP ni I/O implícita.

DNS / mDNS / LLMNR — Preguntas y RR
Nombres comprimidos, A, AAAA, PTR, CNAME, NS, SRV, TXT y MX; respuestas/autoridad/adicionales. Registros desconocidos quedan hex. DNS TCP admite mensajes reensamblados.

DHCP / BOOTP — Cabecera y opciones seleccionadas
IP cliente/asignada/servidor/relay, MAC, máscara, router, DNS, NTP, dirección solicitada, hostname, vendor class, cliente y opciones overload. No interpreta todas las opciones propietarias.

DHCPv6 — Opciones seleccionadas
DUID MAC, IA_NA/IA_TA, IAADDR, IA_PD/IAPREFIX, DNS, servidor unicast y relay. No interpreta todas las opciones de fabricantes.

ARP / NDP — Direcciones y anuncios
ARP sender/target MAC e IPv4. NDP target/redirect, MAC origen/destino, prefijos, DNS RDNSS y MTU. IPv6 con extensiones básicas; fragmentos IPv6 no se reensamblan.

SNMP — BER v1/v2c parcial
OID, enteros, cadenas, IpAddress e ifPhysAddress con OID reconocido. No interpreta todas las MIB ni descifra SNMPv3; sus campos cifrados permanecen hex.

Modbus TCP — MBAP y PDU seleccionadas
FC 1-6, 15, 16, excepciones y FC43/MEI14 Device Identification. Dirección, cantidad, registros o identificación cuando la estructura lo permite. Otras funciones quedan hex; respuesta se identifica por puerto origen 502.

S7comm / COTP — Cabeceras y negociación
TPKT/COTP, ROSCTR, referencia PDU, función, errores y Setup Communication. SZL, variables, S7CommPlus y cifrado no se interpretan.

BACnet/IP — BVLC/NPDU e I-Am
Origen de Forwarded NPDU, redes BACnet, APDU y anuncio I-Am (instancia, vendor ID, max APDU, segmentación). No interpreta todos los servicios BACnet ni BACnet/SC.

OPC UA — Transporte UA-TCP
HEL/ACK/ERR: versión, buffers, límites, endpoint y errores. OPN/MSG/CLO: cabecera/canal y cuerpo hexadecimal. No interpreta servicios binarios ni descifra SecureConversation.

MQTT — Campos 3.1/3.1.1 seleccionados
CONNECT, Client ID, flags, keepalive, usuario, Will, PUBLISH topic y payload, IDs/ACK. Propiedades MQTT5 no separadas; otros cuerpos quedan hex. No descifra MQTT/TLS.

HTTP / SSDP — Cabeceras de texto
Start line, cabeceras, Server, Location, Host y direcciones literales. No descifra HTTPS/QUIC ni interpreta todos los cuerpos, XML, compresión o HTTP/2.

Reensamblado — Con límites explícitos
IPv4 sin superposición: 64 datagramas, hasta 65535 bytes por datagrama y 30 s de espera. TCP para DNS, Modbus, EtherNet/IP, S7, OPC UA y MQTT: 64 flujos, 256 KiB por flujo y 30 s. Admite segmentos fuera de orden después del inicio observado. No recupera bytes no capturados ni aplica heurísticas a protocolos desconocidos; no reensambla HTTP ni mensajes IPv6 fragmentados.

Integridad — Análisis pasivo
Valida tamaños y límites; no valida todos los checksums, firmas ni autenticidad del emisor. Los campos son anuncios observados, no prueba de alcance, fabricante auténtico ni control del equipo.

PUERTOS Y REENSAMBLADO
Se reconocen EtherType/LLC o puertos habituales: DNS 53, mDNS 5353, LLMNR 5355,
DHCP 67/68, DHCPv6 546/547, SNMP 161/162, Modbus TCP 502, S7/COTP 102,
EtherNet/IP 44818, BACnet/IP 47808, OPC UA TCP 4840, MQTT 1883 y SSDP 1900.
HTTP se reconoce por su línea inicial de texto. Servicios sobre otros puertos
pueden quedar sin identificar. No se adivinan objetos ni esquemas propietarios.
Una respuesta CIP sin contexto de objeto no se convierte en IP a ciegas.
Para ver nombres/modelos es necesario capturar los mensajes que los contienen;
no se consultan ni escanean equipos activamente. El programa no envía comandos
DCP Set, escrituras CIP/Modbus/S7 ni cambios de configuración.
La falta de bytes, el inicio de captura a mitad de una conversación, pérdidas,
puertos distintos o cifrado pueden impedir la interpretación. Los bytes quedan
visibles aunque el protocolo o servicio aún no tenga lector propio.
No se descifran TLS, QUIC, SNMPv3 cifrado, S7 seguro ni OPC UA cifrado.

TShark solo se utilizó como referencia externa de pruebas; no se ejecuta, enlaza ni distribuye con NIC Analyzer.
