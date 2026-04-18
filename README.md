# Programaci-n-avanzada
Aquí se documenta el avance del proyecto


# Radar de Intercepción RF - Fusión Sensorial

## Prerrequisitos de Hardware
- Placa LilyGo T-Display-S3 V1.3.
- **CRÍTICO:** Antena omnidireccional de 2.4 GHz acoplada al puerto U.FL. NO ENERGIZAR sin la antena conectada para evitar ROE (Standing Wave Ratio) masivo en el amplificador PHY.

## Entorno de Desarrollo
- PlatformIO bajo VS Code.
- Dependencias estrictas: `TFT_eSPI` (v2.5.0 o superior), `lvgl` (v8.x).

## Instrucciones de Ejecución
1. Clonar el repositorio.
2. Configurar el `platformio.ini` para la placa `lilygo-t-display-s3`. Asegurar que el nivel de debug esté silenciado (`build_flags = -DCORE_DEBUG_LEVEL=0`) para evitar asfixia del bus I2C.
3. Compilar y flashear el código (`Upload`).
4. El sistema iniciará en modo inactivo. Acceder al menú táctil y activar la telemetría para iniciar el motor Kismet y el escáner BLE en el Core 0.
