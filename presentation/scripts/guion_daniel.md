# Guion de Daniel - Arquitectura y Hardware GNSS

Mi nombre es Daniel Luna, y fui el encargado de la arquitectura base del firmware y de dirgir a grandes rasgos el proyecto (tanto de la idea general como de introducir a mis compñaeros a varios conceptos) y de la integración física del hardware en la LilyGo T-Display S3; lo que incluye que yo hice la selección de todo el hardware. El sistema opera bajo un RTOS de doble núcleo. Asigné el Core 0 exclusivamente a los motores de radiofrecuencia para evitar que el escaneo promiscuo entre otras cosas colapsara la interfaz gráfica, la cual corre dentro del Core 1 mediante LVGL.

En cuanto a la telemetría, implementé un módulo u-blox M8N por hardware serial. Una de las dificultades más destacables, por decir lo menos, fue el cuello de botella físico: la interferencia electromagnética (EMI) del ESP32 saturaba el amplificador de la antena cerámica, dejándola ciega. Lo resolví separando las cargas de procesamiento e inyectando un, digamos, bypass táctico en el bus I2C para liberar ciclos de reloj y permitir la triangulación orbital pura. La lección principal de mi fase fue que el hardware es muy sensible; si no aíslas tus módulos de radio, tu software, por más optimizado que esté, simplemente no va a funcionar. 

También estuve en el diseño e impresión de carcasas prototipadas para cada nuevo móduulo añadido.
