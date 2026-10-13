# NIC Analyzer

<img src="nica-v1.png" alt="Icono oficial NICA V1" width="180">

**Inspecciona tus interfaces y encuentra información en el tráfico de red.**

NIC Analyzer es una herramienta de escritorio de **Dysco Exploration and Production**, parte de **Field Tools de cloudLOGGER SCADA**, para identificar interfaces de red, capturar paquetes e inspeccionar su contenido.

**V1.0.2 · compilación 1.2 · Windows x64 · Portable**

[**Descargar NIC Analyzer para Windows x64**](https://github.com/DyscoEP/nic-analyzer/releases/download/v1.0.2/NIC-Analyzer-V1.0.2-Windows-x64.zip)

> La aplicación es portable; **la captura requiere [Npcap](https://npcap.com/) instalado por separado**. NIC Analyzer no instala ni redistribuye Npcap. Detectar interfaces o iniciar el programa no inicia una captura automáticamente.

[Guía de uso](docs/guia-de-uso.md) · [Limitaciones y problemas](docs/limitaciones-y-problemas.md) · [LEEME del paquete](LEEME.txt) · [Soporte](https://github.com/DyscoEP/nic-analyzer/issues/new/choose)

## Qué puedes hacer

| Función | Características |
|---|---|
| Inventario de interfaces | Propiedades y clasificación física/virtual de las NIC que informa Windows; Ethernet, Wi-Fi, Bluetooth y celular según el adaptador. |
| Captura | Captura pasiva por NIC o inicio/detención general sobre las NIC conectadas incluidas. |
| Inspección | Detalles de cabeceras y carga útil, bytes crudos, copia de bloques y vista a pantalla completa. |
| Filtros | NIC, IP origen/destino, TCP, UDP, Modbus TCP, ARP e ICMP; opciones para ocultar ruido. |
| Búsqueda de texto | Busca en contenido decodificado y bytes completos del paquete, sin distinguir mayúsculas; admite texto ASCII en UTF-16 LE/BE. |
| Detección IP/MAC | Extrae direcciones de cabeceras y direcciones escritas en texto dentro del contenido, con su ubicación y línea. Solo contenido excluye cabeceras. |
| Exportación | Paquetes filtrados a PCAP, CSV o texto decodificado; direcciones detectadas a CSV. |
| Importación | PCAP clásico con marcas de microsegundos. PCAPNG no está admitido. |
| Proyectos | Archivos .nica para filtros, selección de NIC y opciones de detección; no guardan paquetes. |
| Escritorio | Paquetes más nuevos arriba, pausa del visor, seguimiento y bandeja de Windows. |

## Ejemplo: buscar Siemens y direcciones

Escribe `siemens` en **Buscar texto en paquetes** y activa **Detectar IP**, **Detectar MAC** o ambas. La pestaña **IP / MAC detectadas** reúne direcciones de los paquetes que coinciden con los filtros, mostrando hora, NIC, ubicación y línea completa.

Marca **Solo contenido** para encontrar únicamente direcciones escritas dentro del mensaje. La palabra y la dirección pueden estar en líneas distintas del mismo paquete. Buscar una palabra no identifica automáticamente al fabricante del equipo.

## Prerrequisitos y descargas oficiales

| Componente | Cuándo se necesita | Descarga |
|---|---|---|
| **Npcap para Windows** | **Obligatorio para captura en vivo** | [Descargar el instalador oficial de Npcap](https://npcap.com/#download). Selecciona el installer para Windows; no necesitas el SDK. |
| Controlador de tu NIC | Para que Windows detecte y pueda utilizar la interfaz | Windows o soporte oficial del fabricante de tu PC/NIC. |
| Python, Wireshark o WinPcap | **No son prerrequisitos de NIC Analyzer** | El portable incluye su runtime; la captura utiliza Npcap. |

Para consultar interfaces o importar y analizar un PCAP guardado no necesitas iniciar una captura ni instalar Npcap. Para capturar, instala Npcap y vuelve a iniciar NIC Analyzer. Si Npcap fue instalado con acceso exclusivo para administradores, ejecuta NIC Analyzer como administrador.

Npcap se obtiene por separado y conserva [sus propias condiciones de licencia](https://npcap.com/#licensing); no viene dentro del ZIP. La instalación no garantiza captura en todos los adaptadores: depende del soporte de la NIC y de su controlador.

[Guía completa de prerrequisitos](docs/prerrequisitos.md)

## Inicio y requisitos

1. Extrae todo el ZIP y ejecuta `NIC-Analyzer.exe`. No necesitas instalar Python ni copiar iconos externos.
2. Selecciona una interfaz para revisar sus propiedades.
3. Para capturar, instala Npcap desde su sitio oficial. Si se instaló en modo exclusivo de administrador, ejecuta NIC Analyzer como administrador.
4. Doble clic en una NIC inicia su captura y abre Paquetes; los controles generales actúan sobre las NIC conectadas marcadas como incluidas.

La captura de una NIC depende de que Npcap permita abrirla. Loopback usa NPF_Loopback; no hay captura Bluetooth HCI ni módem serial directo, ni modo monitor Wi-Fi 802.11.

## Alcance y límites

- Retiene **10 000 paquetes**; la tabla muestra las últimas **2 000 coincidencias** y exporta todas las coincidencias retenidas.
- La cola tiene **5 000 eventos**; bajo carga puede descartar paquetes. No es una auditoría sin pérdidas ni una captura continua en disco.
- Decodifica Ethernet, VLAN, ARP, IPv4, IPv6 básico, TCP, UDP, ICMP, DNS/mDNS básico y cabecera MBAP/función de Modbus TCP presentes en cada paquete.
- No reconstruye flujos TCP, no reensambla fragmentos IP ni descifra TLS. IPv6 con extensiones conserva los bytes sin interpretar el transporte.
- Pausar visor congela la vista, pero la adquisición sigue y el historial continúa rotando.

El chat de desarrollo registra **13 pruebas aprobadas** para V1.0.2. No se garantiza captura en todos los modelos de adaptador; consulta el [alcance completo](docs/limitaciones-y-problemas.md).

## Paquete oficial

El ZIP contiene exactamente `NIC-Analyzer.exe`, `LEEME.txt`, `LICENSE.txt` y `THIRD-PARTY-NOTICES.txt`. Los tres textos se conservan aquí con el mismo contenido que dentro del paquete.

[Releases y descarga oficial](https://github.com/DyscoEP/nic-analyzer/releases/tag/v1.0.2) · [Historial](CHANGELOG.md)

**Code → Download ZIP** y los archivos automáticos **Source code** de GitHub contienen la documentación; el programa es el ZIP portable adjunto a la Release.

## Licencia y soporte

El código propio utiliza la [licencia MIT](LICENSE.txt). Los componentes incluidos conservan sus licencias en [THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt); Npcap es un requisito externo con sus propias condiciones. Este repositorio no contiene el código fuente de la aplicación.

Reporta fallos o sugiere mejoras en [Issues](https://github.com/DyscoEP/nic-analyzer/issues/new/choose). Usa capturas y archivos depurados de datos privados; no publiques tráfico de clientes ni credenciales.

[cloudLOGGER SCADA](https://cloudloggerscada.com) · [Modbus Audit, otra herramienta de Field Tools](https://github.com/DyscoEP/modbus-audit)
