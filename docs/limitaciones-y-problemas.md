# Alcance y ayuda

## Tráfico disponible

NIC Analyzer muestra el tráfico que la interfaz y su controlador permiten capturar. Detectar un adaptador no garantiza acceso a su tráfico. No ofrece modo monitor Wi-Fi 802.11, captura Bluetooth HCI ni conexión directa a módem serial.

## Información de los equipos

La información depende de los mensajes recibidos. Una marca, modelo o dirección puede no estar presente. Las direcciones anunciadas no garantizan que un equipo sea accesible ni que una dirección esté asignada actualmente. No se descifra tráfico cifrado.

El soporte varía por protocolo y servicio. Consulta [Protocolos y capacidades](protocolos-y-limites.md). La inspección no configura equipos ni realiza escrituras sobre ellos.

## Historial y archivos

El historial y las vistas tienen capacidad limitada y pueden descartar tráfico bajo carga. Pausar visor no detiene la captura. Exporta la información importante; .nica guarda configuración, no paquetes. La importación admite PCAP clásico con marcas de microsegundos, no PCAPNG.

## Si no inicia la captura

Comprueba la instalación de Npcap, los permisos y el estado de la interfaz. Usa Descargar Npcap y Volver a comprobar cuando el aviso lo ofrezca. Si la instalación exige reiniciar Windows, completa ese paso.

## Si no encuentras una coincidencia

Pulsa Quitar filtros y aplica solo los necesarios. Usa Buscar texto en paquetes para palabras e IP de cabecera / anunciada para direcciones. No es posible mostrar información ausente, cifrada o de servicios no admitidos.

[Solicitar soporte](../SUPPORT.md)
