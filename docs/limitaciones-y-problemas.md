# Limitaciones y solución de problemas

## No inicia la captura

Comprueba que Npcap esté instalado y que permita abrir la NIC. Si está configurado en modo exclusivo de administrador, ejecuta NIC Analyzer como administrador. El programa no instala Npcap. Inventariar una interfaz no garantiza que esa interfaz pueda capturarse.

NIC virtual, Bluetooth o celular depende del acceso de Npcap. No hay captura directa Bluetooth HCI ni módem serial. Wi-Fi usa el tráfico que entrega el controlador, sin modo monitor 802.11. Loopback usa NPF_Loopback.

## No encuentro texto o direcciones

El filtro IP de cabecera / anunciada busca extremos y campos de direcciones reconocidos. Para texto usa Buscar texto en paquetes. Todos los filtros se combinan: prueba Quitar filtros y después aplica solo los necesarios.

La detección encuentra direcciones reales de las cabeceras y las de campos binarios reconocidos o escritas como texto en el contenido. Solo contenido elimina las primeras. La palabra y la dirección deben aparecer en el mismo paquete, aunque pueden estar en líneas distintas.

Reensambla IPv4 y mensajes TCP de protocolos seleccionados con límites explícitos; consulta [la cobertura](protocolos-y-limites.md). No descifra TLS/QUIC ni protocolos industriales cifrados, no reensambla HTTP ni fragmentos IPv6. No deduce fabricantes ausentes ni IP binarias de protocolos sin lector propio. Capturas incompletas, puertos no habituales y pérdidas pueden impedir la decodificación.

## Paquetes perdidos o filas ausentes

Se retienen hasta 10000 paquetes físicos más un paquete inspeccionado adicional; se retiran los más antiguos al alcanzar el límite. La cola de adquisición admite 5000 eventos y puede descartar bajo carga. El contador informa descartes. No hay adquisición sin pérdidas ni captura continua en disco.

La tabla de paquetes y la de direcciones muestran hasta 2000 coincidencias cada una. Exportar incluye todas las coincidencias retenidas. Pausar visor no pausa la captura; el historial puede seguir rotando. Limpiar elimina el contenido retenido y deja activa la captura si lo estaba.

## Archivo incompatible

Importar admite PCAP clásico con marcas de microsegundos. PCAPNG no está admitido. Si las capturas usan diferentes tipos de enlace, filtra y exporta por NIC.

## Datos no guardados en el proyecto

.nica guarda configuración, filtros y NIC incluidas, no paquetes. Para conservarlos utiliza Exportar paquetes antes de limpiar o perderlos por rotación.

## Reportar

Incluye versión, Windows, tipo de NIC, versión de Npcap, mensaje de error y pasos reproducibles. Depura capturas de datos privados antes de adjuntarlas al soporte público.
