# 💡 Lámpara Inteligente: El Sensor de Luz Automático

## El reto de hoy @unplugged

¡Hola, inventores/as! Hoy vamos a convertir nuestra Micro:bit en un **dispositivo inteligente para el hogar**. Vamos a programar una **lámpara automática** que detecte por sí sola cuándo se hace de noche para encenderse, y cuándo sale el sol para apagarse y ahorrar energía.

### 🎯 Objetivos de la lección

* Usar la matriz de LEDs como un **sensor de entrada**.
* Entender cómo funcionan los **bloques lógicos** (Si... entonces).
* Aprender a gestionar **umbrales de luz** (de 0 a 255).

### 🛠️ Requisitos

* Una tarjeta **Micro:bit**.
* Un cable **Micro-USB** o portapilas.

---

### 🧠 Concepto Clave: El Nivel de Luz

¿Sabías que los LEDs de tu Micro:bit también pueden "ver"? Funcionan al revés: captan la claridad de la habitación y nos dan un número.
* **0** significa oscuridad total (¡noche cerrada!).
* **255** significa muchísima luz (¡un foco dándole de cerca!).

---

## 🚀 Paso 1: Midiendo la oscuridad

Queremos que la placa esté vigilando el nivel de luz constantemente para decidir qué hacer.

1.  Ve a la categoría **Lógica** y busca el bloque `||logic:si < verdadero > entonces / si no||`. Encájalo dentro del bloque `||basic:para siempre||`.
2.  Para la comparación, busca en **Lógica** el bloque de comparación `||logic:0 < 0||`. Ponlo donde dice "verdadero".
3.  En el primer hueco del `0`, coloca desde **Entrada** el bloque `||input:nivel de luz||`.
4.  En el segundo hueco, escribe el número **50**. ¡Este será nuestro "umbral de oscuridad"!

---

## 🚀 Paso 2: ¡Hágase la luz!

Ahora le diremos a la Micro:bit qué dibujo mostrar cuando detecte que hay poca luz (menos de 50).

1.  En el hueco de **entonces**, añade un bloque de **Básico** llamado `||basic:mostrar leds||`.
2.  Dibuja un cuadrado grande o un sol lleno de puntos para que brille mucho.
3.  En el hueco de **si no** (que significa que hay luz suficiente), añade el bloque `||basic:borrar pantalla||`.

```blocks
basic.forever(function () {
    if (input.lightLevel() < 50) {
        basic.showLeds(`
            # # # # #
            # # # # #
            # # # # #
            # # # # #
            # # # # #
            `)
    } else {
        basic.clearScreen()
    }
})
```

---

## 🕵️ Prueba de funcionamiento

Para probar tu invento antes de descargarlo, fíjate en el **simulador** de la izquierda:

1.  Verás que arriba a la izquierda de la Micro:bit virtual aparece un icono de un **sol con un número**.
2.  Mueve el ratón para bajar ese número por debajo de **50**. ¡Mira cómo se enciende tu lámpara!
3.  Súbelo por encima de **50** y verás cómo se apaga automáticamente.

---

## 🧪 Desafío: El modo "Ahorro de Energía"

**Misión:** ¿Puedes hacer que la lámpara no se apague de golpe?

1.  Añade una `||basic:pausa (ms) 2000||` (2 segundos) justo después de que se enciendan los LEDs.
2.  Cambia el dibujo de los LEDs por uno más pequeño (un cuadrado más chico) antes de que se apague del todo.

**Pregunta para pensar:** Si tu clase está muy iluminada, ¿deberías subir o bajar el número **50** para que la lámpara funcione bien?

---

## 📥 Envía el programa

¡Listo! Dale a **Descargar** y copia el archivo a tu Micro:bit. Tapa la placa con tu mano para simular la noche y... ¡mira cómo se ilumina!

---