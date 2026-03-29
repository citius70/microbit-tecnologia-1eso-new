# 🔘 Botones Sonrientes: Expresando Emociones

## El reto de hoy @unplugged
¡Hola de nuevo, inventores\! Hoy vamos a darle "sentimientos" a nuestra Micro:bit. Aprenderemos a usar los botones físicos **A** y **B** para que la placa reaccione a nuestras pulsaciones con gestos y sonidos.

### 🎯 Objetivo

Programar los botones de la placa para que muestren una **cara feliz** 😀 o una **cara triste** 🙁 al interactuar con ellos.

*(Asegúrate de tener este gif en tu carpeta de imagenes o usa la ruta de MakeCode)*

-----

### 🧠 Conceptos Clave: Eventos de Entrada

En programación, presionar un botón ``|A|`` o ``|B|`` es un **Evento**. La Micro:bit se queda "escuchando" y, cuando detecta la pulsación, ejecuta las instrucciones que hayamos puesto dentro.

-----

## 🚀 Paso 1: Botón A = Cara Alegre

Vamos a programar el botón izquierdo para que nuestra Micro:bit se ponga contenta.

1.  Entra en la categoría **Entrada** y arrastra el bloque `||input:al presionar el botón A||`.
2.  Dentro, coloca el bloque `||basic:mostrar icono||` y selecciona la **cara feliz**.
3.  ¡Añadamos sonido\! Busca en **Música** el bloque `||music:play sound happy||`.

<!-- end list -->

```blocks
input.onButtonPressed(Button.A, function() { 
    basic.showIcon(IconNames.Happy)
    music.play(music.builtinPlayableSoundEffect(soundExpression.happy), music.PlaybackMode.UntilDone)
})
```

**Prueba:** Haz clic en el botón **A** del simulador. ¿Suena y brilla? ⭐ ¡Genial\!

-----

## 🚀 Paso 2: Botón B = Cara Triste

Ahora haremos lo mismo para el botón derecho, pero con una emoción diferente.

1.  Arrastra otro bloque `||input:al presionar el botón A||`.
      * *Nota: El bloque se verá gris al principio. Haz clic en la "A" y cámbiala por una **"B"**.*
2.  Selecciona el icono de la **cara triste** y el sonido **"sad"**.

<!-- end list -->

```blocks
input.onButtonPressed(Button.B, function() {
    basic.showIcon(IconNames.Sad)
    music.play(music.builtinPlayableSoundEffect(soundExpression.sad), music.PlaybackMode.UntilDone)
})
```

-----

## ⚡ Desafío Final: El Emoji Secreto (A+B)

Los programadores expertos saben que Micro:bit tiene un "tercer" botón oculto: **¡Presionar A y B al mismo tiempo\!**

**Tu misión:**

1.  Crea un nuevo evento de entrada.
2.  Configúralo para que sea `||input:A+B||`.
3.  Elige un icono secreto (un corazón, una calavera o un alien) y un sonido de "misterio".

> **Pista:** En el simulador aparecerá un nuevo botón virtual llamado **"A+B"** para que puedas probarlo sin dedos extra.

-----

## 📥 Envía el programa a tu Micro:bit

1.  Conecta tu placa al ordenador con el cable USB.
2.  Haz clic en el botón **Descargar** 💾.
3.  Arrastra el archivo `.hex` a la unidad MICROBIT que aparecerá en tu equipo.

-----
