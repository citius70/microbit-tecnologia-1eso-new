# 💡 Luces en Acción: Dominando la Matriz LED

## El reto de hoy @unplugged

¡Bienvenidos, inventores! 

En este tutorial vamos a aprender a controlar el "rostro" de nuestra Micro:bit: la **matriz de 25 LEDs**. Aprenderemos cómo hacer que un punto de luz cobre vida mediante el parpadeo y cómo usar coordenadas para dibujar expresiones.

### 🎯 Objetivos de Aprendizaje
* Entender el sistema de **coordenadas (X, Y)** de la Micro:bit.
* Aprender la importancia de los **tiempos de espera (pausas)** en la programación.
* Crear animaciones básicas usando el bucle **"para siempre"**.

### 🛠️ Requisitos
1. Una tarjeta **BBC Micro:bit**.
2. Un cable **Micro-USB** para conectar al ordenador.
3. Acceso al editor **MakeCode** (online o app).

### 🧠 Conceptos Clave

Para que nuestra Micro:bit haga lo que queremos, debemos entender cómo se organiza su pantalla:
* **La Matriz LED:** Es una cuadrícula de **5x5**.
* **Coordenadas:** Cada LED tiene una "dirección". El LED de arriba a la izquierda es el **(0, 0)**. 
    * El eje **X** se mueve de izquierda a derecha (0 a 4).
    * El eje **Y** se mueve de arriba abajo (0 a 4).
* **El Bucle "Para siempre":** Es un ciclo que no termina. Todo lo que pongas dentro se repetirá hasta que apagues la placa.

---

## 🚀 Paso 1: Encender el primer LED

Vamos a encender el LED de la esquina superior izquierda.

1. Busca el bloque `||led:graficar x 0 y 0||` dentro de la categoría **LED**.
2. Arrástralo dentro del bloque `||basic:para siempre||`.

```blocks
basic.forever(() => {
    led.plot(0, 0)
})
```
*¿Ves ese punto rojo en el simulador? ¡Ya has tomado el control del hardware!*

---

## ⏱️ Paso 2: Crear el efecto de parpadeo

Si solo encendemos el LED, se quedará prendido para siempre. Para que parpadee, necesitamos una secuencia: **Encender -> Esperar -> Apagar -> Esperar**.

1. Añade un bloque `||basic:pausa (ms) 1000||` (1000 ms es igual a 1 segundo).
2. Añade el bloque `||led:ocultar x 0 y 0||` justo debajo.
3. ¡Importante! Añade otra **pausa** al final. Si no lo haces, el código volverá al principio tan rápido que no verás el LED apagado.

```blocks
basic.forever(() => {
    led.plot(0, 0)
    basic.pause(1000)
    led.unplot(0, 0)
    basic.pause(1000)
})
```

---

## 🎭 Desafío 1: El "Guiño" Robótico

Ahora que sabes cómo encender puntos específicos, vamos a dibujar algo más complejo.

**Tu misión:** Haz que la Micro:bit muestre dos "ojos" parpadeando.
1. Los ojos estarán en las coordenadas `(1, 1)` y `(3, 1)`.
2. Haz que ambos se enciendan a la vez, esperen 1 segundo, y se apaguen a la vez.

```blocks
basic.forever(() => {
    led.plot(1, 1)
    led.plot(3, 1)
    basic.pause(1000)
    led.unplot(1, 1)
    led.unplot(3, 1)
    basic.pause(1000)
})
```

---

## 🔥 Desafío Final: La Cara Sonriente Animada

¿Podrías hacer que una cara sonriente completa aparezca y desaparezca?

**Instrucciones:**
1. Mantén los ojos en `(1, 1)` y `(3, 1)`.
2. Añade la nariz en `(2, 2)`.
3. Dibuja la boca usando los puntos: `(0, 3)`, `(4, 3)`, `(1, 4)`, `(2, 4)` y `(3, 4)`.
4. ¡Haz que toda la cara parpadee al unísono!

> **Pista de experto:** Si quieres que la cara parpadee más rápido, cambia los `1000 ms` por `200 ms`. ¡Parecerá una animación de videojuego antiguo!

---
