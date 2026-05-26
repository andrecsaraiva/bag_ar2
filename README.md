# Bag AR Try-On — WebXR

Versão simples, sem 8th Wall e sem build, baseada no mesmo padrão WebXR do protótipo de quadro/poster.

## Estrutura

Coloque tudo na raiz do repositório:

    bag-webxr/
    ├── index.html
    ├── ar.html
    ├── bag.glb
    └── vercel.json

## Como funciona

- `index.html` gera o QR Code para `ar.html`.
- `ar.html` abre uma sessão WebXR `immersive-ar`.
- O tracking usa WebXR hit-test direto do ARCore.
- O app filtra superfícies horizontais, como chão, mesa e bancada.
- Toque para posicionar a bolsa.
- Depois de posicionar, use:
  - `Reposicionar`
  - `↺` e `↻` para girar
  - `−` e `+` para ajustar escala

## Deploy

No Vercel:

- Framework Preset: Other
- Sem build
- Sem output directory

Basta subir os arquivos na raiz. O `vercel.json` garante o MIME type correto do `.glb`.

## Ajustes principais no topo do `ar.html`

- `MODEL_URL = './bag.glb'`
- `MODEL_SCALE = 1.0`
- `MODEL_REAL_SIZE = null`
- `HORIZONTAL_DOT_MIN = 0.72`

Se a bolsa vier muito grande/pequena, ajuste `MODEL_SCALE` ou use `MODEL_REAL_SIZE`.
