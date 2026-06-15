## Guion Integrante 2: Rio - Motor de Inteligencia de Señales (SIGINT)

"Mi responsabilidad fue el desarrollo del sniffer en modo promiscuo dentro del Core 0. Diseñé la función de callback que intercepta directamente las tramas 802.11 en bruto. El sistema no se conecta a las redes, simplemente extrae los Probe Requests de los teléfonos móviles y los Beacons de los routers en el aire.

Para el filtrado de objetivos, programé un diccionario heurístico con 96 firmas de redes públicas comunes en México. El problema inicial fue el desbordamiento de memoria; el ESP32 colapsaba al intentar procesar miles de paquetes basura por segundo. La solución técnica fue aplicar una máscara de filtro estricta (WIFI_PROMIS_FILTER_MASK_MGMT) para descartar el ruido y almacenar solo las direcciones MAC viables en una matriz de RAM aislada. Comprobé que el espectro de 2.4 GHz es un caos, y sin una disección algorítmica precisa desde la antena, extraer inteligencia útil es imposible."
