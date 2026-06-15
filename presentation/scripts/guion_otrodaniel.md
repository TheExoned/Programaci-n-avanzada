
## Guion de Daniel Reyes:

Fui el responsable del control de bajo nivel del bus I2C para la pantalla táctil CST816 y la eficiencia térmica del hardware. Escribi el driver puente que extrae las coordenadas físicas del panel y las
traduce a la máquina de estados de LVGL.

El sistema presentaba un sobrecalentamiento crítico debido a la retroiluminación y al procesamiento continuo de los núcleos. Para evitar quemar el silicio, diseñé un cortafuegos anti-rebote en el touchpad y un protector de pantalla que manipula directamente el bus PWM ( LedcWrite ). A los 5 segundos de inactividad estática, estrangulo la energía del backlight y dibujo un render RAW oscuro para conservar bateria, permitiendo una resurrección instantánea al toque. 

El reto aquí fue que el hardware táctil bloqueaba el bus de datos si el ESP32 entraba en suspensión profunda. La estabilización requirió reescribir los timeouts de la librería Wire. El hardware exige respeto
absoluto a sus tiempos físicos.
