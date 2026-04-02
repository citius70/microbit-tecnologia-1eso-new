# Podómetro Digital: ¡Tu Reto de 10.000 Pasos! 🏃‍♂️

## El reto de hoy @unplugged

¡Hola, atletas tecnológicos! Hoy vamos a convertir nuestra Micro:bit en un **dispositivo "wearable"** (tecnología que se lleva puesta). Vamos a programar un contador de pasos que detecte cada vez que caminamos o corremos. 

### ❓ ¿Cómo sabe la Micro:bit que estoy caminando?
Dentro de tu placa hay un sensor llamado **Acelerómetro**. Este sensor mide las fuerzas de movimiento. 
1.  Cuando caminas, tu cuerpo da un pequeño "salto" o impacto en cada paso.
2.  El acelerómetro detecta ese impacto como un gesto de **agitado** o una sacudida.
3.  Cada vez que el sensor siente ese impacto, le dice al programa: "¡Suma 1 paso más a la cuenta!".

**Misión:** Crear un contador que no pierda la cuenta y que podamos reiniciar al final del día.

---

### 🎯 Objetivos de la lección
* Usar una **Variable como acumulador** (sumar sobre un valor anterior).
* Utilizar el sensor de **Acelerómetro** para detectar impactos.
* Aprender a mostrar y reiniciar datos guardados.

### 🛠️ Requisitos
* Una tarjeta **Micro:bit**.
* Un portapilas (para poder andar con ella).
* Una cinta o goma elástica para sujetarla a tu zapatilla o muñeca.

---

## 🚀 Paso 1: Preparando el marcador

Antes de empezar a caminar, nuestro marcador debe estar a cero.

1.  Crea una variable llamada `||variables:pasos||`.
2.  En el bloque `||basic:al iniciar||`, pon el bloque `||variables:fijar pasos a 0||`.
3.  Añade un bloque para mostrar el número `0` al principio.

```blocks
let pasos = 0
basic.showNumber(pasos)
```

---

## 🚀 Paso 2: ¡Contando el movimiento!

Ahora configuraremos el sensor para que detecte cada zancada.

1.  Busca en **Entrada** el bloque `||input:si agitado||`.
2.  Dentro, usa el bloque de **Variables** `||variables:cambiar pasos por 1||`.
3.  Para que sea divertido, añade un sonido corto o un destello de luz cada vez que cuente un paso.

```blocks
input.onGesture(Gesture.Shake, function () {
    pasos += 1
    basic.showNumber(pasos)
})
```

---

## 🚀 Paso 3: Reiniciar el día

Si queremos empezar una nueva ruta, necesitamos poner el contador a cero sin tener que apagar la placa.

1.  Usa el bloque `||input:al presionar el botón A + B||`.
2.  Vuelve a poner la variable `||variables:pasos||` a **0**.
3.  Muestra un icono de "check" o una flecha para saber que se ha reiniciado.

```blocks
input.onButtonPressed(Button.AB, function () {
    pasos = 0
    basic.showNumber(pasos)
})
```

---

## 🕵️ Truco de precisión: ¿Cuenta demasiado?

A veces, el gesto `||input:agitado||` es muy sensible y cuenta dos pasos cuando solo has dado uno.
* **Solución:** Añade una pequeña `||basic:pausa (ms) 100||` después de sumar el paso. Esto le da tiempo al sensor a "estabilizarse" antes de volver a contar.

---

## 🧪 Desafío: El Entrenador Personal

**Misión 1: Meta de pasos.** Haz que cuando el contador llegue a **10 pasos**, la Micro:bit toque una melodía de victoria y muestre una corona. ¡Has cumplido tu objetivo!

**Misión 2: Modo Ahorro.** Mostrar el número todo el tiempo gasta mucha pila. Modifica el programa para que la pantalla esté **apagada** y solo muestre el número de pasos cuando pulses el **Botón A**.

**Pregunta para pensar:** ¿Contará pasos si llevas la Micro:bit en la mano o solo si va en el pie? ¡Haz la prueba!

---

## 📥 Envía el programa

¡Tu podómetro está listo! Dale a **Descargar**, ponle las pilas y... ¡a caminar! ¿Cuántos pasos eres capaz de dar antes de que termine el recreo?

---