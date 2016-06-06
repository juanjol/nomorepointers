---
id: 77
title: Script Python para apagar la Raspberry PI con GPIO
date: 2015-02-05T00:59:41+00:00
author: Mr. bug
layout: post
guid: http://nomorepointers.com/?p=77
permalink: /script-python-para-apagar-la-raspberry-pi-con-gpio/
audiourl:
  - 
videourl:
  - 
categories:
  - Desarrollo
  - raspberry
tags:
  - gpio
  - python
  - Raspberry
  - Raspberry PI
  - reboot
  - script
  - shutdown
---
Aquí os voy a dejar un pequeño script en python que he hecho para poder apagar la raspberry conectada a mi pantalla de leds (os la mostraré en otro post) con un botón conectado a la gpio. Lo he dejado en github:

[ https://github.com/enfuse/raspberry-gpi-shutdown/blob/master/shutdown.py](https://github.com/enfuse/raspberry-gpi-shutdown/blob/master/shutdown.py)

<pre>import RPi.GPIO as GPIO
import time
import os
GPIO.setmode(GPIO.BCM)
GPIO.setup(17, GPIO.IN,pull_up_down=GPIO.PUD_UP)
GPIO.setup(18, GPIO.IN,pull_up_down=GPIO.PUD_UP)
while True:
    if(GPIO.input(17) == False):
        os.system("sudo shutdown -h now")
        break   
    if(GPIO.input(18) == False):
        os.system("sudo shutdown -r now")
        break
    time.sleep(1)</pre>

El esquema de conexión de cables en una Raspberry B+ sería el siguiente:

<img class=" wp-image-80 aligncenter" src="http://nomorepointers.com/wp-content/uploads/2015/02/raspgpio_bb-1.png" alt="raspgpio_bb" width="400" height="470" />

&nbsp;