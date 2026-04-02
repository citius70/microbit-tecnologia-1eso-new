# Mensajería Mágica: Redes  📡

## El reto de hoy @unplugged

¿Te imaginas enviar un dibujo por el aire sin usar cables? Hoy vamos a programar tu Micro:bit para que actúe como una **antena de radio**. Aprenderás cómo las máquinas se comunican de forma invisible usando ondas electromagnéticas.

### ❓ ¿Cómo viaja la información?
Antes de programar, imagina que cuando pulsas el **Botón A**:
1.  **Emisor:** Tu placa convierte la palabra **"mensaje"** en ondas de radio invisibles (como el Wi-Fi o la radio del coche).
2.  **Aire:** Esas ondas viajan por la clase a la velocidad de la luz.
3.  **Receptor:** La placa de tu compañero/a "atrapa" esas ondas.
4.  **Cerebro (Procesador):** El procesador lee el texto y dice: *¿Dice 'mensaje'? ¡Sí! Entonces dibujo el corazón.*

**Misión por parejas:** Uno será el Emisor y otro el Receptor.

---

### 🎯 Objetivos de la lección
* Configurar un **Grupo de Radio** (ID de red única).
* Enviar y recibir una **Cadena** (la palabra "mensaje").
* Usar la lógica para reaccionar al texto recibido.

### 🛠️ Requisitos
* **2 placas Micro:bit**.
* **2 cables USB** o portapilas.

---

## 🚀 Paso 1: ¡Sincroniza tu frecuencia! 📟

Para que vuestros mensajes no se mezclen con los de otros grupos, debéis elegir vuestra propia "matrícula" de red.

1.  En el bloque `||basic:al iniciar||`, busca en la sección de **Radio**: `||radio:radio establecer grupo [1]||`.
2.  Elegid un número entre **1 y 255**. ¡Vuestras dos placas deben tener el mismo!

```blocks
radio.setGroup(42)
```

---

## 🚀 Paso 2: El Emisor (¡Lanza el mensaje!) 🚀

Vamos a programar el botón para que envíe nuestra palabra clave por el aire.

1.  Saca el bloque `||input:al presionar el botón A||`.
2.  Busca en Radio: `||radio:radio enviar cadena " "||`.
3.  Escribe dentro la palabra: **"mensaje"**.
4.  Para confirmar que ha salido, añade: `||basic:mostrar cadena "OK"||`.

```blocks
input.onButtonPressed(Button.A, function () {
    radio.sendString("mensaje")
    basic.showString("OK")
})
```

---

## 🚀 Paso 3: El Receptor (¡Atrapa el corazón!) 🎯

Ahora configuramos la otra placa para que "escuche" y verifique si el mensaje es el correcto.

1.  Busca el bloque: `||radio:al recibir radio (receivedString)||`.
2.  Dentro, usa un bloque de **Lógica**: `||logic:si [receivedString] = "mensaje" entonces||`.
3.  Si es cierto, pon: `||basic:mostrar icono (Corazón)||` y un sonido de aviso.

```blocks
radio.onReceivedString(function (receivedString) {
    if (receivedString == "mensaje") {
        basic.showIcon(IconNames.Heart)
        music.play(music.builtinPlayableSoundEffect(soundExpression.giggle), music.PlaybackMode.InBackground)
    }
})
```

---

## 🧪 Desafío: El Código Secreto

**Misión:** ¿Puedes hacer que tu sistema envíe un mensaje diferente?

1.  Al pulsar el **Botón B**, envía la palabra **"feliz"**.
2.  Modifica el receptor (añadiendo un `||logic:si no, si||`) para que, si recibe "feliz", muestre una **cara sonriente** `||basic:showIcon(Happy)||`.

**Pregunta para pensar:** Si cambias tu número de grupo al **7**, ¿podrás seguir leyendo los mensajes de tus compañeros que se quedaron en el grupo **42**?

---

## 📥 Envía el programa

¡Listo! Dale a **Descargar** en ambas placas. ¡Vuestra red inalámbrica ya es oficial!

---

/**
* Utilice este archivo para definir funciones y bloques personalizados.
* Lea más en https://makecode.microbit.org/blocks/custom
*/

enum MyEnum {
    //% block="one"
    One,
    //% block="two"
    Two
}

/**
 * Custom blocks
 */
//% weight=100 color=#0fbc11 icon=""
namespace custom {
    /**
     * TODO: describe your function here
     * @param n describe parameter here, eg: 5
     * @param s describe parameter here, eg: "Hello"
     * @param e describe parameter here
     */
    //% block
    export function foo(n: number, s: string, e: MyEnum): void {
        // Add code here
    }

    /**
     * TODO: describe your function here
     * @param value describe value here, eg: 5
     */
    //% block
    export function fib(value: number): number {
        return value <= 1 ? value : fib(value -1) + fib(value - 2);
    }
}
