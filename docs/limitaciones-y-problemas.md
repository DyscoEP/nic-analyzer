# Limitaciones y solución de problemas

## No inicia la captura

Comprueba que Npcap esté instalado y que permita abrir la NIC. Si está configurado en modo exclusivo de administrador, ejecuta NIC Analyzer como administrador. El programa no instala Npcap. Inventariar una interfaz no garantiza que esa interfaz pueda capturarse.

NIC virtual, Bluetooth o celular depende del acceso de Npcap. No hay captura directa Bluetooth HCI ni módem serial. Wi-Fi usa el tráfico que entrega el controlador, sin modo monitor 802.11. Loopback usa NPF_Loopback.

## No encuentro texto o direcciones

El filtro IP origen/destino busca solo las direcciones de extremos. Para texto usa Buscar texto en paquetes. Todos los filtros se combinan: prueba Quitar filtros y después aplica solo los necesarios.

La detección encuentra direcciones reales de las cabeceras y las escritas como texto en el contenido. Solo contenido elimina las primeras. La palabra y la dirección deben aparecer en el mismo paquete, aunque pueden estar en líneas distintas.

No descifra TLS ni reconstruye texto dividido entre paquetes. No deduce fabricantes ausentes del contenido ni IP binarias de protocolos sin decodificador. IPv6 con extensiones conserva bytes sin interpretar el transporte.

## Paquetes perdidos o filas ausentes

Se retienen hasta 10000 paquetes; se retiran los más antiguos al alcanzar el límite. La cola de adquisición admite 5000 eventos y puede descartar bajo carga. El contador informa descartes. No hay adquisición sin pérdidas ni captura continua en disco.

La tabla de paquetes y la de direcciones muestran hasta 2000 coincidencias cada una. Exportar incluye todas las coincidencias retenidas. Pausar visor no pausa la captura; el historial puede seguir rotando. Limpiar elimina el contenido retenido y deja activa la captura si lo estaba.

## Archivo incompatible

Importar admite PCAP clásico con marcas de microsegundos. PCAPNG no está admitido. Si las capturas usan diferentes tipos de enlace, filtra y exporta por NIC.

## Datos no guardados en el proyecto

.nica guarda configuración, filtros y NIC incluidas, no paquetes. Para conservarlos utiliza Exportar paquetes antes de limpiar o perderlos por rotación.

## Reportar

Incluye versión, Windows, tipo de NIC, versión de Npcap, mensaje de error y pasos reproducibles. Depura capturas de datos privados antes de adjuntarlas al soporte público.
