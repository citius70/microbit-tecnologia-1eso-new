# 🚀 ¡Personaliza tu Micro:bit!

## Introducción @unplugged
¡Bienvenido al mundo de la programación! Hoy vas a darle voz a tu placa Micro:bit. Aprenderás a mostrar mensajes y emociones usando su matriz de 25 LEDs.

### 🛠️ Requisitos
* **1 Micro:bit** (v1 o v2).
* **1 Cable USB**.
* **Un ordenador** con acceso a MakeCode.

---

## Paso 1: El saludo inicial
Para empezar, queremos que la placa diga "Hola" en cuanto se encienda.

1. Haz clic en la categoría ``||basic:Básico||``.
2. Arrastra el bloque ``||basic:mostrar cadena||`` y encájalo dentro de ``||basic:al iniciar||``.
3. Cambia el texto "Hello!" por **"HOLA"**.

### ~ tutorialhint
```blocks
basic.showString("HOLA")
```

## Paso 2: Añade una emoción
Después del saludo, vamos a mostrar un icono para que la placa se vea amigable.

1. Busca el bloque ``||basic:mostrar icono||`` en la categoría Básico.
2. Colócalo justo debajo de tu nombre.
3. Haz clic en el corazón y elige la **cara feliz**.

### ~ tutorialhint
```blocks
basic.showString("HOLA")
basic.showIcon(IconNames.Happy)
```

## Paso 3: ¡Crea un bucle! @unplugged
¿Te has fijado en el bloque ``||basic:para siempre||``? Todo lo que pongas ahí se repetirá una y otra vez, como un dibujo animado infinito.

## Paso 4: Animación infinita
Vamos a hacer que un corazón palpite sin parar.

1. Arrastra un bloque ``||basic:mostrar icono||`` (corazón grande) dentro de ``||basic:para siempre||``.
2. Debajo, coloca otro bloque ``||basic:mostrar icono||``, pero esta vez elige el **corazón pequeño**.

### ~ tutorialhint
```blocks
basic.forever(function() {
    basic.showIcon(IconNames.Heart)
    basic.showIcon(IconNames.SmallHeart)
})
```

## Paso 5: ¡A la placa! 📥
¡Ya lo tienes! Ahora:
1. Conecta tu Micro:bit al USB.
2. Haz clic en el botón **Descargar**.
3. ¡Mira cómo cobra vida tu creación!

---

## 🏆 El Desafío Final
¿Eres capaz de hacer que, además del corazón, aparezca una **flecha** apuntando hacia arriba después de cada latido? ¡Inténtalo!
