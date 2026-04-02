# Piano de Aluminio: ¡Música Táctil! 🎹

## El reto de hoy @unplugged

¡Hola, músicos/as tecnológicos! Hoy vamos a sacar la Micro:bit de la pantalla y conectarla al mundo real. Vamos a construir un **piano táctil** usando simples trozos de papel de aluminio. 

### ❓ ¿Cómo funciona un circuito táctil?
Para que suene una nota, la electricidad debe viajar en un círculo cerrado (circuito). 
1. La Micro:bit envía una señal diminuta por el pin **GND** (Tierra).
2. Esa señal viaja por un cable hasta **tu cuerpo**.
3. Cuando tocas el papel de aluminio conectado al **Pin 0**, la electricidad pasa de tu dedo al papel y vuelve a la placa.
4. La Micro:bit detecta que el círculo se ha cerrado y... **¡BOOM! Suena la música.**

---

### 🎯 Objetivos de la lección
* Aprender a usar los **Pines de entrada** (0, 1 y 2).
* Entender el concepto de **conductividad** y circuito cerrado.
* Programar eventos sonoros basados en el tacto.

### 🛠️ Requisitos
* Una tarjeta **Micro:bit**.
* 3 o 4 trozos de **papel de aluminio**.
* 4 cables de **pinzas de cocodrilo** (si no tienes, ¡puedes usar celo y cable normal!).

---

## 🚀 Paso 1: Configurando las teclas musicales

No usaremos botones esta vez, sino los "pines" (las patas doradas de abajo).

1.  Busca en la categoría **Entrada** el bloque `||input:al presionar el pin P0||`.
2.  Dentro, ve a **Música** y elige `||music:reproducir tono [Do central] por [1 pulso]||`.
3.  Repite lo mismo para los pines **P1** y **P2**, pero asigna notas diferentes (como Re y Mi).

```blocks
input.onPinPressed(TouchPin.P0, function () {
    music.playTone(262, music.beat(BeatFraction.Whole))
})
input.onPinPressed(TouchPin.P1, function () {
    music.playTone(294, music.beat(BeatFraction.Whole))
})
input.onPinPressed(TouchPin.P2, function () {
    music.playTone(330, music.beat(BeatFraction.Whole))
})
```

---

## 🚀 Paso 2: ¡Construye tu piano! 🛠️

Ahora viene la parte de hardware. Sigue estos pasos con cuidado:

1.  **Las Teclas:** Corta 3 cuadrados de papel de aluminio y ponlos sobre la mesa.
2.  **Conexión de Notas:** Conecta un cable desde el **Pin 0** al primer papel, otro desde el **Pin 1** al segundo, y otro desde el **Pin 2** al tercero.
3.  **El "Cable de Tierra":** Conecta un cuarto cable al **Pin GND**. 
4.  **¡Importante!:** Para que suene, debes **sujetar el extremo metálico del cable GND con una mano** y, con la otra, tocar los papeles de aluminio.

---

## 🚀 Paso 3: Un toque visual

Para que nuestro piano sea más profesional, haremos que la pantalla reaccione a cada nota.

1.  Añade un bloque `||basic:mostrar icono||` dentro de cada evento de Pin. 
2.  Por ejemplo: una nota musical para el P0, un corazón para el P1 y una cara feliz para el P2.

---

## 🕵️ ¿Por qué no suena? (Solución de problemas)

Si al tocar el papel no suena nada, revisa esto:
* ¿Estás tocando la parte metálica del cable conectado a **GND**? Tu cuerpo es el puente que lleva la electricidad.
* Si usas **Micro:bit V1**, recuerda que necesitas conectar unos auriculares o un altavoz a los pines (Pin 0 y GND) para oír algo. ¡La **V2** tiene altavoz incorporado!

---

## 🧪 Desafío: El Piano Frutal o Humano

**Misión 1:** Sustituye el papel de aluminio por **frutas** (plátanos, manzanas...). ¿Sigue funcionando? ¿Por qué crees que ocurre?

**Misión 2: El Piano Humano.** Haz que tus compañeros se den la mano. El primero sujeta el cable GND y el último toca el papel de aluminio. ¡La electricidad viajará a través de todos vosotros!

**Pregunta para pensar:** ¿Funcionaría este piano si llevas puestos unos guantes de lana muy gruesos? ¡Pruébalo!

---

## 📥 Envía el programa

¡Tu instrumento está listo para el concierto! Dale a **Descargar** y empieza a componer tus primeras melodías tecnológicas.

---