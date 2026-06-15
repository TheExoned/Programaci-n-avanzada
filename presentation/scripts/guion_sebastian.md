

## Guion de sebastian - Redes Ofensivas

Estuve a cargo del arsenal ofensivo del sistema. Desarrollé dos vectores principales. Primero, la inyección nativa de paquetes de desautenticación. Construí los frames hexadecimales en crudo para forzar la desconexión de clientes específicos, superando la limitación estándar del framework de Arduino.

El segundo vector es el Espejismo Cautivo, un ataque Evil Twin. Despliego un Hotspot malicioso, enciendo un sumidero DNS en el puerto 53 para secuestrar todo el tráfico y lanzo un servidor web asíncrono con portales clonados (como el de RIUV). La dificultad principal fue lograr que los teléfonos modernos abrieran el portal automáticamente sin marcar alertas de seguridad. Esto se resolvió manipulando las respuestas HTTP de los endpoints de conectividad de Android e iOS.

Queda demostrado que la seguridad inalámbrica es frágil frente a inyecciones directas de capa 2.
