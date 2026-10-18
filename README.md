# NIC Analyzer

<img src="nica-v1.png" alt="NIC Analyzer" width="180">

**Convierte el tráfico de red en información útil para tu diagnóstico.**

Identifica interfaces, inspecciona paquetes y encuentra texto y direcciones IP / MAC anunciadas por equipos de red e industriales. Una herramienta portable de **Dysco Exploration and Production**, parte de **Field Tools / cloudLOGGER SCADA**.

**V1.1.3 · compilación 2.3 · Windows x64 · Interfaz en español**

[**Descargar para Windows x64**](https://github.com/DyscoEP/nic-analyzer/releases/latest/download/NIC-Analyzer-Windows-x64.zip) · [Guía de uso](docs/guia-de-uso.md) · [Soporte](SUPPORT.md)

## Funciones

| Capacidad | Qué puedes hacer |
|---|---|
| Interfaces de red | Consulta adaptadores Ethernet, Wi-Fi y otras interfaces informadas por Windows; distingue físicos y virtuales. |
| Captura de tráfico | Inicia y detén por interfaz o mediante controles generales. |
| Diagnóstico de equipos | Consulta identificaciones, descripciones y direcciones anunciadas cuando están presentes en el tráfico. |
| Búsqueda y filtros | Combina texto, protocolo, interfaz e IP; oculta tráfico habitual que no necesitas revisar. |
| IP / MAC detectadas | Reúne direcciones con su contexto y línea; limita la búsqueda al contenido cuando lo necesites. |
| Lectura cómoda | Paquetes recientes arriba, bloques seleccionables y detalle estable mientras llegan nuevos paquetes; ventana ampliable independiente. |
| Exportación | Guarda paquetes en PCAP, CSV o texto y direcciones en CSV. Importa PCAP clásico para revisar capturas guardadas. |
| Proyectos | Conserva filtros y configuración en archivos .nica. |

## Encuentra la información que buscas

Escribe una palabra, por ejemplo `siemens`, en **Buscar texto en paquetes**. Activa **Detectar IP**, **Detectar MAC** o ambas para localizar paquetes coincidentes que también contienen direcciones. **Solo contenido** permite concentrarte en la información anunciada dentro del mensaje. La pestaña **IP / MAC detectadas** muestra dirección y contexto.

Consulta los [protocolos y capacidades](docs/protocolos-y-limites.md) y el [alcance de uso](docs/limitaciones-y-problemas.md). La información disponible depende del tráfico recibido y de las funciones admitidas para cada protocolo; no se descifra tráfico cifrado.

## Empieza a usarlo

1. Descarga y extrae el ZIP; ejecuta `NIC-Analyzer.exe`.
2. Selecciona una interfaz para consultar sus propiedades. Doble clic inicia su captura.
3. Si falta el controlador de captura, pulsa **Descargar Npcap** en el aviso para abrir [su descarga oficial](https://npcap.com/#download). Instálalo y pulsa **Volver a comprobar** para continuar con NIC Analyzer abierto. Sigue las indicaciones del instalador si solicita reiniciar Windows.
4. Selecciona un paquete, busca información y exporta lo que necesites.

Windows x64. La captura en vivo requiere Npcap instalado por separado y acceso a la interfaz. Para consultar interfaces o analizar un PCAP guardado no necesitas capturar. [Requisitos de uso](docs/prerrequisitos.md).

## Descarga, ayuda y avisos

El ZIP incluye `NIC-Analyzer.exe`, `LEEME.txt`, `LICENSE.txt` y `THIRD-PARTY-NOTICES.txt`. [Checksum de descarga](https://github.com/DyscoEP/nic-analyzer/releases/latest/download/NIC-Analyzer-SHA256SUMS.txt) · [Novedades](CHANGELOG.md) · [Releases](https://github.com/DyscoEP/nic-analyzer/releases/latest).

Descarga el programa desde el adjunto portable de Releases. Los archivos automáticos Source code de GitHub contienen la documentación del repositorio; las fuentes de la aplicación no se publican aquí.

Consulta las condiciones incluidas en [LICENSE.txt](LICENSE.txt) y los [avisos de terceros](THIRD-PARTY-NOTICES.txt). Reporta incidencias en [Soporte](SUPPORT.md) sin adjuntar tráfico privado, credenciales ni datos de clientes.

[cloudLOGGER SCADA](https://cloudloggerscada.com) · [DYSCO EP](https://dyscoep.com/descargas/nic-analyzer/)
