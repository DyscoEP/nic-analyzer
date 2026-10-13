# Guía de uso · V1.0.2

El [LEEME](../LEEME.txt) contiene las instrucciones y límites completos del portable.

## Interfaces y captura

Al iniciar se detectan interfaces reales de Windows sin iniciar captura. Selecciona una NIC para consultar propiedades y su clasificación. Si CIM está restringido, el inventario .NET muestra una clase estimada.

Npcap debe estar instalado por separado. Si su instalación limita la captura a administradores, ejecuta la aplicación con esa cuenta. Doble clic en una NIC inicia la captura y abre Paquetes. Seleccionar Paquetes en el árbol solo navega.

Guardar interfaz conserva si esa NIC está incluida. Iniciar general actúa sobre todas las conectadas incluidas; Detener general detiene todas. Los controles de una vista actúan sobre la NIC seleccionada.

## Inspección y búsqueda

Selecciona un paquete para ver cabeceras y carga útil. Seleccionar un bloque copia su contenido. Copiar línea copia los datos de la fila; doble clic en un paquete o bloque abre pantalla completa. Regresar o Escape vuelve a la vista anterior.

**Filtrar IP origen/destino** busca coincidencias parciales en las direcciones de los extremos. **Buscar texto en paquetes** busca texto decodificado y bytes completos, sin distinguir mayúsculas, incluido ASCII en UTF-16 LE/BE.

Combina búsqueda con filtros de protocolo, NIC y opciones de ruido. IP del equipo oculta todo tráfico con una IP local en cualquier extremo; no identifica procesos ni distingue tráfico útil de ruido.

## IP / MAC detectadas

Escribe una palabra, como siemens, y marca Detectar IP o Detectar MAC. Si marcas ambas se acepta cualquiera de los dos tipos. Solo se muestran paquetes que coinciden también con los demás filtros.

La vista reúne direcciones de las cabeceras y las escritas en el contenido completo. **Solo contenido** excluye las cabeceras. La palabra y dirección pueden aparecer en líneas diferentes del mismo paquete.

Se validan IPv4/IPv6 y MAC con dos puntos, guiones o formato Cisco. No se convierten bytes arbitrarios en direcciones. Seleccionar una fila copia sus datos y línea. Doble clic abre el paquete cuando está entre las 2000 filas de la tabla superior.

Exportar direcciones guarda CSV con todas las coincidencias retenidas; la vista inferior muestra hasta 2000 filas e indica al alcanzar el límite.

## Pausa, exportaciones y proyectos

Seguir contenido mantiene arriba los más recientes sin cambiar el seleccionado. Pausar visor congela tabla y detalles mientras la adquisición continúa. Reanudar muestra los datos actuales. Quitar filtros recupera los paquetes retenidos y desactiva detección.

Exportar paquetes guarda las coincidencias a PCAP, CSV o texto. Si hay tipos de enlace diferentes, exporta cada NIC por separado. Importar admite PCAP clásico con marcas de microsegundos, no PCAPNG.

Archivo → Guardar conserva filtros, NIC incluidas y detección en .nica; no guarda los paquetes. El proyecto acepta configuraciones anteriores.

Minimizar conserva la app en bandeja; el icono permite restaurar, iniciar/detener general y salir. Ver permite desactivar esa preferencia. Ayuda → Acerca de muestra identidad, versión y licencia MIT.
