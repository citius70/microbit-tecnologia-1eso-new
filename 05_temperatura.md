# 🌡️ Estación Meteorológica: LEDs y Gráficas en tiempo real

## El reto de hoy @unplugged

¡Hola, científicos/as\! Hoy vamos a convertir nuestra Micro:bit en una **estación meteorológica inteligente**. Primero haremos que nos diga la temperatura constantemente en su pantalla y luego aprenderemos a enviar esos datos al ordenador para ver una **gráfica en tiempo real**.

### 🎯 Objetivos de la lección

  * Usar el bloque **"Para siempre"** para lecturas constantes.
  * Visualizar datos numéricos en la matriz LED.
  * Aprender a usar la **Consola Serial** para crear gráficas automáticas.

### 🛠️ Requisitos

  * Una tarjeta **Micro:bit**.
  * Un cable **Micro-USB** (¡imprescindible para la parte del ordenador\!).

-----

### 🧠 Concepto Clave: El Sensor de Temperatura

Tu Micro:bit mide el calor que siente su procesador principal. Es muy sensible y puede detectar cambios de grado en grado.


-----

## 🚀 Paso 1: El termómetro automático

Queremos que la placa nos diga la temperatura todo el tiempo, sin tener que tocar ningún botón.

1.  Ve a la categoría **Básico** y asegúrate de tener el bloque `||basic:para siempre||`.
2.  Dentro, coloca el bloque `||basic:mostrar número 0||`.
3.  Busca en **Entrada** el bloque redondo `||input:temperatura (ºC)||` y encájalo sobre el `0`.

<!-- end list -->

```blocks
basic.forever(() => {
    basic.showNumber(input.temperature())
    basic.pause(2000)
})
```

-----

## 🚀 Paso 2: ¡Conexión con el ordenador\! (Serial)

Ver los números pasar por la placa está bien, pero los científicos prefieren **gráficas**. Vamos a enviar la temperatura por el cable USB al ordenador.

1.  Haz clic en **Avanzado** y entra en la categoría **Serial**.
2.  Arrastra el bloque `||serial:serial escribir valor "x" = 0||` dentro de tu bucle.
3.  Cambia la `"x"` por la palabra "**Temperatura**".
4.  En el lugar del `0`, duplica y coloca otro bloque de `||input:temperatura (ºC)||`.

<!-- end list -->

```blocks
basic.forever(() => {
    basic.showNumber(input.temperature())
    serial.writeValue("Calor", input.temperature())
    basic.pause(2000)
})
```

-----

## 📊 Visualizando tu gráfica científica

Una vez que descargues el programa en tu Micro:bit física, ocurrirá algo "mágico" en tu pantalla:

1.  Conecta la Micro:bit por USB.
2.  En el editor de MakeCode, aparecerá un botón debajo del simulador llamado **"Mostrar consola Dispositivo"**.
3.  ¡Haz clic en él\! Verás cómo se dibuja una línea azul que representa la temperatura de tu clase.


-----

## 🧪 Desafío: El experimento del frío

**Misión:** ¿Puedes hacer que la gráfica caiga en picado?

1.  Abre la consola serial y observa la línea estable.
2.  Acerca con cuidado algo frío a la parte trasera de la placa (¡sin mojarla\!).
3.  Observa cómo la gráfica baja en tiempo real en tu ordenador.

**Pregunta para pensar:** ¿Cuánto tiempo tarda la Micro:bit en recuperar la temperatura normal de la habitación después de quitar el frío?

-----

## 📥 Envía el programa

No olvides darle a **Descargar** para que tu Micro:bit empiece a enviar datos. ¡Tu estación meteorológica ya está funcionando\!
