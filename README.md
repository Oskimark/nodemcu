# nodemcu
Error while setting serial port parameters

Recientemente me di cuenta de que tengo dos grupos de placas NodeMCU que son diferentes. Al programar unas con el IDE de Arduino, no hay problemas. Sin embargo, al intentar programar las otras, me encuentro con el siguiente error:

"serial.serialutil.SerialException: Cannot configure port, something went wrong. Original message: PermissionError(13, 'The device connected to the system is not working.', None, 31)"

Sin embargo, al utilizar NodeMCU Flasher, funciona presionando el botón de flash y reset en la placa, pero en Arduino no. Al examinar más de cerca, noté algunas diferencias en el diseño cerca del puerto USB, y el chip CH341 no tiene ningún texto. El pinout también es diferente y no hay un cristal de 12 MHz. Parece que es otro chip, pero Windows lo detecta como uno y usa los controladores correspondientes.

Finalmente, estoy seguro de que estas placas son falsas, y el problema, al igual que con los chips FTDI, surge debido a una actualización de los controladores que ya no los reconoce. La solución consistió en instalar controladores antiguos y reiniciar, aunque fue un desafío, ya que incluso después de cargar el controlador nuevo (que en realidad era viejo), todavía era necesario reiniciar.

Otra diferencia es que estas placas tienen un firmware diferente que crea un punto de acceso (AP) llamado "FaryLink_XXXXXX" (los caracteres corresponden a la dirección MAC).
hay una captura mostrando el driver correcto. y es el CH34x_Install_Windows_v3_4.zipde esta carpeta
