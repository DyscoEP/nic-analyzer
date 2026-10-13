# Prerrequisitos · NIC Analyzer

| Componente | Cuándo se necesita | Descarga |
|---|---|---|
| **Npcap para Windows** | **Obligatorio para captura en vivo** | [Descargar el instalador oficial de Npcap](https://npcap.com/#download). Selecciona el installer para Windows; no necesitas el SDK. |
| Controlador de tu NIC | Para que Windows detecte y pueda utilizar la interfaz | Windows o soporte oficial del fabricante de tu PC/NIC. |
| Python, Wireshark o WinPcap | **No son prerrequisitos de NIC Analyzer** | El portable incluye su runtime; la captura utiliza Npcap. |

Para consultar interfaces o importar y analizar un PCAP guardado no necesitas iniciar una captura ni instalar Npcap. Para capturar, instala Npcap y vuelve a iniciar NIC Analyzer. Si Npcap fue instalado con acceso exclusivo para administradores, ejecuta NIC Analyzer como administrador.

Npcap se obtiene por separado y conserva [sus propias condiciones de licencia](https://npcap.com/#licensing); no viene dentro del ZIP. La instalación no garantiza captura en todos los adaptadores: depende del soporte de la NIC y de su controlador.


Los enlaces llevan al sitio oficial del proveedor para obtener el controlador vigente. Esta documentación no instala componentes ni modifica el portable publicado.
