# Tarea 3: Timbiriche :school_satchel:

## Consideraciones generales :octocat:

Mi tarea permite registrarse (falla al verificar la clave), muestra el perfil del jugador y se puede añadir una foto (no tiene manejo de bytes), la foto se guarda en el server pero no muestra fotos guardadas con anterioridad (no logré que se abrieran correctamente). Se puede crear una nueva sala, cerrar, sesión, chatear y jugar pero ocasionalmente tira un ResetConnectionError que no permite apretar nada más. Solo permite que el lider pueda oprimir jugar y no permite que se ingrese a la sala si tiene más de 15 jugadores. No tiene nada del juego.

### Cosas implementadas y no implementadas :white_check_mark: :x:

** NO REVISAR NI JUEGO NI MANEJO DE BYTES, AHORRATE EL TIEMPO AYUDANTE HERMANO Y ESTUDIA PARA TUS EXÁMENES, NO ESTÁ NADA DE ESO HECHO.

1. Flujo del juego:
- Se permite al usuario registrarse con un nombre de usuario que sea nuevo y almacena la clave.
- Se codifica y guarda la clave del usuario pero por alguna razón no verifica la clave (siempre tira error aunque la clave codificada y la ingresada sean iguales). Pedi ayuda a muchos ayudantes de este y otros semestres en este tema pero nadie supo decirme cual era el error, sin embargo, si se analiza el código, se muestra un correcto entendimiento de la función que hashea y del almacenamiento de la info (si se pudiese revisar).
- Se cuenta con un boton volver para poder cambiar la opcion: inicio sesion o registrarse.
- Se puede ingresar a una sala de preparacion donde se muestran las salas disponibles con labels oprimibles junto a su número de participantes, se actualizan en vivo para todos los clientes.
- El perfil muestra nombre y permite subir una foto al perfil y guardar el path en el archivo usuarios.txt, sin embargo, por alguna razón no muestra la foto al leer el archivo de algun usuario con una foto subida anteriormente (se nota que hay una foto ahí pero sale en blanco, no la muestra).
- No hay filtro dibujo ni nada de manejo de bytes
- Al oprimir un label de sala se puede ingresar y ver el nombre de la sala y el lider, además se puede chatear y se actualiza en vivo para los clientes, hay un botón para jugar y solo el lider puede oprimirlo.
** Pasa algo muy raro donde ocasionalmente tira el error de ConnectionResetError, subí una issue al respecto pero la ayudante que intentó ayudarme (Jesu) me dijo que a ella no se le caía el programa y que quizas era problema de mi computador por lo que no pude arreglar el problema, a veces funcionaba correctamente y a veces no.
- Si la sala está vacía se elimina y si tiene más de 15 jugadores no permite que se ingrese a la sala.
- El comando chao funciona correctamente, en el caso límite de ser un jugador falla ya que se utilizo que el minimo de los votos es de N//2 + 1 (N numero de jugadores), por ende requiere que 2 jugadores voten por expulsar a la persona. Se activa poniendo "/chao NOMBRE JUGADOR" y se vota enviando "chao".

2. Juego
- No hay nada hecho del juego.

**SI SE IMPLEMENTÓ GIT IGNORE

## Ejecución :computer:
El módulo principal de la tarea a ejecutar es  ```Cliente.py```


## Librerías :books:
### Librerías externas utilizadas
La lista de librerías externas que utilicé fue la siguiente:

import threading as th
import socket
import json
from collections import defaultdict
import os.path
import bcrypt
import random
from PyQt5.QtCore import pyqtSignal
from PyQt5.QtWidgets import QWidget, QLabel, QLineEdit, QHBoxLayout, QVBoxLayout, QGridLayout, QFormLayout
from PyQt5.QtWidgets import QPushButton, QScrollArea, QFrame, QGroupBox, QFileDialog
from PyQt5.QtCore import Qt, QRect
from PyQt5.QtGui import QTextCursor, QPixmap


## Referencias de código externo :book:

Para realizar mi tarea saqué código de:
1. https://www.tutorialspoint.com/pyqt/pyqt_qfiledialog_widget.htm --> Para subir la foto del perfil del usuario

2. Ayudantia 11 2018-2 --> Para implementar el chat



## Descuentos
**Hay un archivo con más de 400 líneas de código
**Hay líneas con más de 80 caractéres (pocas según yo, no estoy segura)
