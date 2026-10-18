# Guía de uso

## Interfaces y captura

Al abrir NIC Analyzer se muestran las interfaces que informa Windows. Selecciona una para consultar propiedades; doble clic inicia la captura. Seleccionar Paquetes en el árbol solamente abre esa vista.

Los controles generales actúan sobre las NIC conectadas incluidas. Los controles de la vista actúan sobre la NIC seleccionada. Detener general detiene las capturas y cancela solicitudes pendientes.

Si falta el controlador de captura, el aviso ofrece Descargar Npcap y Volver a comprobar. Instálalo desde el sitio oficial y vuelve a comprobar para iniciar las interfaces solicitadas sin cerrar NIC Analyzer. Cerrar el aviso cancela esas solicitudes. Si el instalador exige reiniciar Windows, completa ese paso.

## Buscar y filtrar

Buscar texto en paquetes encuentra palabras en la información disponible del paquete. Combina esta búsqueda con interfaz, protocolo, IP y opciones para ocultar tráfico habitual. IP del equipo oculta todo tráfico con una IP local; úsalo solo cuando quieras excluir ese tráfico.

Detectar IP y Detectar MAC muestran coincidencias que también tienen direcciones del tipo elegido. Si activas ambas, basta cualquiera de los dos tipos. Solo contenido excluye direcciones de los encabezados Ethernet/IP y conserva las anunciadas dentro del mensaje. La palabra y la dirección pueden estar en líneas diferentes del mismo mensaje.

La vista IP / MAC detectadas muestra dirección, ubicación y contexto. Seleccionar una fila copia sus datos; Exportar direcciones guarda CSV.

## Leer e inspeccionar

Selecciona un paquete para revisar sus bloques. Seleccionar un bloque copia su contenido. Copiar línea copia la información de la fila. Doble clic abre una ventana ampliable independiente; usa Cerrar ventana, la X de Windows o Escape para regresar.

Los paquetes recientes aparecen arriba y el detalle conserva tu posición de lectura mientras llega tráfico. Seguir contenido mantiene la lista al día; Pausar visor congela la visualización mientras la captura continúa. Quitar filtros recupera las coincidencias aún disponibles.

## Guardar y compartir resultados

Exportar guarda paquetes filtrados en PCAP, CSV o texto. Importar admite PCAP clásico con marcas de microsegundos; PCAPNG no está admitido. Si hay interfaces con diferentes tipos de enlace, exporta cada una por separado.

Archivo > Guardar conserva filtros y configuración en .nica; para guardar paquetes utiliza Exportar. Limpiar retira los datos disponibles. El historial es limitado: exporta la información importante antes de que salga del historial.

Minimizar puede conservar la aplicación en la bandeja de Windows. Desde su menú puedes restaurar, iniciar/detener capturas generales o salir.
