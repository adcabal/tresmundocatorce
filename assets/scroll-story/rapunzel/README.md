# Scroll Story — Assets de escenas

Assets de las escenas Scroll Story (capa visual opcional activada con
`"scrollStory": { "active": true, "type": "rapunzel" }` en el JSON).

Mientras un asset no exista, la capa muestra su **placeholder CSS**
automáticamente (fallback, la invitación nunca se rompe). Al colocar el
archivo `.webp` aquí, la escena lo usa sin tocar código.

## Rapunzel (`assets/scroll-story/rapunzel/`)

| Archivo          | Capa (z-index) | Contenido                                       | fit      |
| ---------------- | -------------- | ----------------------------------------------- | -------- |
| `background.webp` | background (1) | Cielo nocturno, luna, estrellas, bosque lejano  | cover    |
| `tower.webp`      | tower (2)      | Torre completa, fondo transparente              | contain  |
| `character.webp`  | character (3)  | Princesa sola, cuerpo completo, transparencia   | contain  |
| `hair.webp`       | hair (4)       | Solo cabello dorado largo, transparencia        | contain  |
| `particles.webp`  | particles (5)  | Partículas/destellos sueltos, transparencia     | cover    |
| `foreground.webp` | foreground (6) | Ramas/hojas/niebla del marco, transparencia     | cover    |

Recomendado: **webp** (o png) **con transparencia** salvo background.
Vertical (retrato) para tower/character/hair.

## Sobrescribir assets por invitación (opcional)

```json
"scrollStory": {
  "active": true,
  "type": "rapunzel",
  "assets": {
    "background": "assets/scroll-story/rapunzel/background.webp",
    "tower": "assets/scroll-story/rapunzel/tower.webp",
    "character": "assets/scroll-story/rapunzel/character.webp",
    "hair": "assets/scroll-story/rapunzel/hair.webp",
    "particles": "assets/scroll-story/rapunzel/particles.webp",
    "foreground": "assets/scroll-story/rapunzel/foreground.webp"
  }
}
```

Sin `assets` se usan las rutas por defecto de arriba (definidas en
`scenes/rapunzel/rapunzel.scene.ts`).

## Prompts para generar los assets (IA)

### background.webp
Ilustración de cuento de hadas cinematográfica, formato vertical, cielo
nocturno azul y violeta, luna grande, estrellas suaves, bosque mágico al
fondo, atmósfera elegante y romántica, iluminación de fantasía,
profundidad cinematográfica, sin personajes, sin torre en primer plano,
sin texto, sin bordes ni marco.

### tower.webp
Torre de cuento de hadas alta y elegante, arquitectura romántica, piedra
clara, ventanas iluminadas, detalles mágicos, vista vertical, torre
completa, fondo completamente transparente, sin personaje, sin luna, sin
bosque, sin texto.

### character.webp
Princesa de cuento de hadas ORIGINAL (no copia de una representación
cinematográfica específica) de cabello dorado extremadamente largo,
vestido elegante de fantasía, pose vertical, expresión amable, estética
cinematográfica de ilustración premium, cuerpo completo, iluminación
suave, personaje aislado, fondo completamente transparente, sin torre,
sin bosque, sin objetos adicionales, sin texto.

### hair.webp
Exclusivamente cabello dorado extremadamente largo y ondulado, flotando
suavemente, movimiento natural, iluminación mágica, volumen elegante,
múltiples mechones visibles, fondo completamente transparente, sin
rostro, sin cuerpo, sin torre, sin otros objetos, sin texto.

### particles.webp
Partículas mágicas doradas y azuladas, pequeñas estrellas, polvo
luminoso, destellos suaves, distribución irregular, fondo completamente
transparente, sin personajes, sin edificios, sin texto.

### foreground.webp
Elementos de bosque mágico en primer plano: ramas, hojas, pequeñas
flores, vegetación elegante, partículas de niebla. Composición para
colocarse delante de una escena de cuento de hadas, fondo completamente
transparente, sin personajes, sin torre, sin texto.

## Notas

- Nuevas escenas (`luxury`, `fairytale`): archivo data-only en
  `components/s/scroll-story/scenes/<nombre>/` + registro en `scenes/index.ts`.
- Los keyframes de cada capa viven junto a la definición de la escena
  (no aquí): posiciones/escala/opacidad por progreso de scroll 0→1.
