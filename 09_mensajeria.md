# Mensajería Mágica: Redes 📡

## El reto de hoy @unplugged

¿Te imaginas enviar un dibujo por el aire sin usar cables? Hoy vamos a programar tu Micro:bit para que actúe como una **antena de radio**. Aprenderás cómo las máquinas se comunican de forma invisible y cómo controlar cuánto tiempo se ve la información en pantalla.

### ❓ ¿Cómo viaja la información?
1.  **Emisor:** Tu placa convierte el código **"mensaje1"** en ondas de radio.
2.  **Aire:** Esas ondas viajan por la clase de forma invisible.
3.  **Receptor:** La placa de tu compañero/a recibe el texto y dice: *¿Dice 'mensaje1'? ¡Sí! Entonces dibujo el corazón, espero 2 segundos y borro la pantalla.*

---

### 🎯 Objetivos de la lección
* Configurar un **Grupo de Radio** único.
* Enviar la cadena de texto **"mensaje1"**.
* Usar la lógica para mostrar un icono y luego **borrar la pantalla**.

### 🛠️ Requisitos
* **2 placas Micro:bit**.
* **2 cables USB** o portapilas.

---

## 🚀 Paso 1: ¡Sincroniza tu frecuencia! 📟

Para que vuestros mensajes no se mezclen con los de otros grupos, debéis elegir vuestra propia "matrícula" de red.

1.  En el bloque `||basic:al iniciar||`, busca en la sección de **Radio**: `||radio:radio establecer grupo [1]||`.
2.  Elegid un número entre **1 y 255**. ¡Ambas placas deben tener el mismo!

```blocks
radio.setGroup(42)
```

---

## 🚀 Paso 2: El Emisor (¡Lanza el código!) 🚀

Programaremos el botón A para que envíe nuestra señal secreta.

1.  Saca el bloque `||input:al presionar el botón A||`.
2.  Busca en Radio: `||radio:radio enviar cadena " "||`.
3.  Escribe dentro exactamente: **"mensaje1"**.
4.  Para saber que se ha enviado, añade: `||basic:mostrar cadena "OK"||`.

```blocks
input.onButtonPressed(Button.A, function () {
    radio.sendString("mensaje1")
    basic.showString("OK")
})
```

---

## 🚀 Paso 3: El Receptor (¡Atrapa y limpia!) 🎯

Ahora configuramos la recepción. Queremos que el corazón aparezca, pero que desaparezca solo después de un momento.

1.  Busca el bloque: `||radio:al recibir radio (receivedString)||`.
2.  Usa la lógica: `||logic:si [receivedString] = "mensaje1" entonces||`.
3.  Si es correcto:
    * Muestra el icono `||basic:Corazón||`.
    * Espera con `||basic:pausa (ms) [2000]||`.
    * Limpia todo con `||basic:borrar la pantalla||`.

```blocks
radio.onReceivedString(function (receivedString) {
    if (receivedString == "mensaje1") {
        basic.showIcon(IconNames.Heart)
        basic.pause(2000)
        basic.clearScreen()
    }
})
```

---

## 🧪 Desafío: El Segundo Código Secretos 🕵️‍♂️

**Misión:** ¿Puedes hacer que tu sistema envíe una cara sonriente usando un código distinto?

1.  **En el Emisor:** Haz que al pulsar el **Botón B**, se envíe la cadena **"mensaje2"**.
2.  **En el Receptor:** Añade un bloque `||logic:si no, si||` para que, si la Micro:bit recibe **"mensaje2"**, muestre una **cara sonriente** `||basic:showIcon(Happy)||`.
3.  **¡No olvides!** Asegúrate de que la cara sonriente también se borre después de 2 segundos.

**Pregunta para pensar:** Si escribes "Mensaje1" (con mayúscula) en el emisor y "mensaje1" (minúscula) en el receptor, ¿crees que funcionará? ¡Haz la prueba!

---

## 📥 Envía el programa
¡Listo! Descarga el código en ambas placas y empezad a emitir. ¡Vuestra red inalámbrica ya está operativa!