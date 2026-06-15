Guion de Yahir - Seguimiento CQC (BLE) y Memoria No Vólatil
Mi rol abarcó el escáner táctico de rango corto (CQC) y el almacenamiento persistente.
Implementé un rastreador Bluetooth Low Energy que filtra pasivamente las transmisiones en el aire,
buscando una MAC especifica asociada a un objetivo VIP (en nuestras pruebas, un dispositivo
Honor). Esto alimenta el indicador radial de proximidad de nuestra interfaz.
A la par, programé el subsistema de la caja fuerte de credenciales. Almacenar el botin en RAM era
inútil si el dispositivo perdia energia, asi que integré la libreria Preferences para escribir las
contraseñas interceptadas directo en la memoria Flash NVS. Nos topamos con bucles de reinicio
severos por corrupción de sectores de memoria al escribir rápido; lo solucionamos forzando un
borrado térmico ( nvs_flash_erase )en el arranque si detectábamos firmas corruptas. Aprendi
que la gestión de memoria en sistemas embebidos no perdona errores de punteros
