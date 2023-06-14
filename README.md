# nodemcu
Error while setting serial port parameters

Recientemente  me di cuenta que tengo dos grupos de placas nodeMCU y son diferentes.
unas me dejan programarlas sin problemas ocn el IDE de arduino. pero las otras al intentarlo tiran el error:
serial.serialutil.SerialException: Cannot configure port, something went wrong. Original message: PermissionError(13, 'The device connected to the system is not working.', None, 31) 

y mas. 
sin embargo usando NodeMCU Flasher funciona (pulsando el boton de flash y reset en la placa)
pero en arduino ni asi.
examinando de cerca veo que tienen algunas diferencias en el layout cerca del puerto usb y el chip ch341 no tiene texto. 
el pinout del mismo es diferente,
no hay cristal de 12mhz,
sin duda que es otro chip. pero windows lo detecta como uno y usa los drivers. 
al final estoy seguro qeu son falsos y el problema al igual que paso con ftdi, en alguna actualizacion de los drivers estos ya no funcionan.
solucion , instalar drivers viejos y reiniciar, esa parte me costo horas. por mas qeu veamos el driver nuevo (viejo) cargado  igual reiniciar.
otra diferencia es que estas placas tienen otro firmware que crea un AP llamado FaryLink_XXXXXX (caracteres de la MAC)
