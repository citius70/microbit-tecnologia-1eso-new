#  El Dado Electrónico: Azar y Movimiento 🎲

## El reto de hoy @unplugged

¡Hola, desarrolladores/as! Hoy vamos a sustituir los dados de plástico por tecnología. Vamos a programar un **dado digital** que detecte cuando lo agitamos. Aprenderás cómo la Micro:bit usa su **acelerómetro** para sentir el movimiento y cómo generar **números aleatorios** (al azar).

### 🎯 Objetivos de la lección

* Utilizar el **Acelerómetro** para detectar el gesto de agitar.
* Crear y usar **Variables** para guardar información.
* Programar una **lógica condicional múltiple** (Si... si no, si... si no...).

### 🛠️ Requisitos

* Una tarjeta **Micro:bit**.
* Portapilas (para que sea un dado portátil de verdad).

---

### 🧠 Concepto Clave: El Azar y las Variables

En programación, cuando queremos que algo cambie cada vez, usamos **números aleatorios**. Para que la Micro:bit no "olvide" qué número ha salido, lo guardamos en una **Variable**, que es como una cajita con un nombre donde guardamos un dato.

---

## 🚀 Paso 1: ¡Detectando el movimiento!

En lugar de usar botones, usaremos el sensor de movimiento.

1.  Busca en la categoría **Entrada** el bloque `||input:si agitado||`.
2.  Todo lo que pongamos dentro se ejecutará solo cuando movamos la placa con energía.

```blocks
input.onGesture(Gesture.Shake, () => {
})
```

---

## 🚀 Paso 2: La variable "puntos"

Ahora necesitamos generar el número y guardarlo.

1.  Ve a **Variables** y crea una llamada `||variables:puntos||`.
2.  Pon el bloque `||variables:fijar puntos a 0||` dentro del gesto de agitar.
3.  En lugar del `0`, busca en **Matemáticas** el bloque `||math:escoger al azar de 1 a 6||`.

```blocks
input.onGesture(Gesture.Shake, () => {
    let puntos = randint(1, 6)
})
```

---

## 🚀 Paso 3: Dibujando las caras del dado

Aquí viene la parte lógica. Dependiendo de lo que valga la variable `puntos`, mostraremos un dibujo u otro.

1.  Usa el bloque de **Lógica** `||logic:si < verdadero > entonces / si no||`. 
2.  Haz clic en el icono de **(+)** del bloque para añadir más condiciones (necesitamos 6 en total).
3.  Compara: `||logic:si puntos = 6||`, entonces `||basic:mostrar LEDs||` con el dibujo del 6.
4.  ¡Añade sonidos! Si sale un 6, usa `||music:reproducir sonido alegre||`.

```blocks
input.onGesture(Gesture.Shake, () => {
    let puntos = randint(1, 6)
    if (puntos == 6) {
        basic.showLeds(`
            # . . . #
            . . . . .
            # . . . #
            . . . . .
            # . . . #
            `)
        music.play(music.builtinPlayableSoundEffect(soundExpression.giggle), music.PlaybackMode.UntilDone)
    } else if (puntos == 5) {
        basic.showLeds(`
            # . . . #
            . . . . .
            . . # . .
            . . . . .
            # . . . #
            `)
    }
    // ... repetir para 4, 3, 2 y 1
})
```

---

## 🚀 Paso 4: Completando el resto de caras

Repite el proceso para los números 4, 3, 2 y el 1. Recuerda que el último número (el 1) puede ir simplemente en el hueco del `||logic:si no||` final, porque si no es 6, 5, 4, 3 ni 2... ¡tiene que ser 1!

---

## 📊 ¿Cómo funciona por dentro?

Cuando agitas la placa, ocurre esto a toda velocidad:
1. El **acelerómetro** avisa al procesador.
2. Se elige un número (ej. el **4**) y se mete en la "caja" llamada `puntos`.
3. El programa pregunta: "¿Es un 6? No. ¿Es un 5? No. ¿Es un 4? **¡SÍ!**".
4. Se dibujan los 4 LEDs en pantalla.

---

## 🧪 Desafío: El Dado Cargado (Trucado)

**Misión:** Los científicos a veces necesitan "trucar" sus experimentos. ¿Podrías hacer que, si pulsamos el **Botón A**, el dado siempre saque un 6?

*Pista: No necesitas azar, solo fijar la variable directamente al pulsar el botón.*

**Pregunta para pensar:** ¿Qué pasaría si cambiamos el azar de (1 a 6) por (1 a 10)? ¿Seguiría funcionando nuestro código de LEDs?

---

## 📥 Envía el programa

¡Tu dado electrónico está listo! Dale a **Descargar**, desconecta el cable y usa las pilas. ¡Ya puedes jugar a cualquier juego de mesa con tu Micro:bit!

---