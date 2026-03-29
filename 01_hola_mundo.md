¡Excelente! Vamos a estrenar ese nuevo repositorio con un tutorial de **"Hola Mundo"** profesional, diseñado específicamente para que el motor de MakeCode lo renderice con éxito y tus alumnos de 1º de ESO lo sigan sin perderse.

Copia y pega el siguiente bloque de texto en un nuevo archivo llamado **`01_hola_mundo.md`** dentro de tu repo `microbit-tecnologia-1eso-new`:

---

```markdown
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
```

---

### 🔗 Tu enlace para compartir con la clase:
Una vez guardes el archivo en GitHub (botón "Commit changes"), dales este enlace a tus alumnos:

👉 [**Abrir Tutorial: 01 Hola Mundo**](https://makecode.microbit.org/#tutorial:https://github.com/citius70/microbit-tecnologia-1eso-new/01_hola_mundo)

**¿Te gustaría que preparemos ahora el archivo `02_termometro.md` para que tengan una segunda práctica lista?**
