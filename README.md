# Bag AR Try-On — WebXR com sombra e gestos

Versão simples, sem 8th Wall e sem build.

## Estrutura

Coloque tudo na raiz:

    bag-webxr/
    ├── index.html
    ├── ar.html
    ├── bag.glb
    └── vercel.json

## Melhorias adicionadas

- Sombra simples usando ShadowMaterial.
- Iluminação menos flat:
  - Hemisphere light mais suave
  - Key light direcional com sombra
  - Fill light leve
  - ACES tone mapping
- Depois de posicionar:
  - 1 dedo arrasta a bolsa pela superfície
  - 2 dedos rotaciona e ajusta escala
  - Botões ↺, ↻, −, + continuam disponíveis

## Configuração

No topo do ar.html:

- MODEL_URL = './bag.glb'
- MODEL_SCALE = 1.0
- HORIZONTAL_DOT_MIN = 0.72
- SHADOW_OPACITY = 0.32
- DRAG_SENSITIVITY = 1.0

Se a sombra ficar forte/fraca, ajuste SHADOW_OPACITY.
Se o arraste estiver rápido/lento, ajuste DRAG_SENSITIVITY.
