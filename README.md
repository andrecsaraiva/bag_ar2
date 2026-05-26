# Bag AR Try-On — WebXR

App de AR para a bolsa, refeito em WebXR (sem Scene Viewer).

## Por que foi refeito

O app antigo usava o Scene Viewer do Google. Os testes mostraram que o
Scene Viewer parou de funcionar em 3 aparelhos, em 2 redes, inclusive com
um modelo oficial do Google — ou seja, o Scene Viewer em si quebrou, e
nenhum código alcança esse problema.

Esta versão usa WebXR, que fala direto com o ARCore (que está instalado e
funcionando nos aparelhos) sem passar pelo Scene Viewer. É a mesma base
do app de quadros, que funciona.

## Arquivos (todos juntos na raiz)

    index.html    <- página com QR code
    ar.html       <- experiência de AR (WebXR)
    bag.glb       <- modelo 3D da bolsa (otimizado: 12 MB -> 4,3 MB)
    vercel.json   <- MIME type correto para .glb

## Como funciona

- Posicionamento no CHÃO / MESA (superfície horizontal).
- O usuário mira, a mira verde gruda na superfície, toca para fixar.
- Ao fixar, a bolsa CONGELA no lugar (não voa, não pula).
- A bolsa fica sempre em pé (só o giro horizontal é aplicado).
- Botão Reposition remove e deixa posicionar de novo.

## Deploy

1. Novo repositório no GitHub, os 4 arquivos na raiz.
2. Commit + push. Importe no Vercel (Framework: Other, sem build).
3. Abra a URL no desktop -> QR aparece.
4. Escaneie no Android com Chrome.

## Limitações

- iPhone não roda (Safari não suporta WebXR AR).
- Detecção depende de boa luz e de chão/mesa com alguma textura.
