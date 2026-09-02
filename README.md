# AR.js + GLB + marcador Hiro

Estrutura esperada:

arjs_glb_marker_demo/
├── index.html
└── models/
    └── model.glb

## 1. Coloque seu arquivo GLB

Copie o seu arquivo para:

    models/model.glb

O nome precisa ser exatamente `model.glb` neste primeiro teste.

## 2. Teste no computador

Dentro da pasta do projeto:

    python3 -m http.server 8000

Abra no próprio computador:

    http://localhost:8000

Em localhost a câmera pode funcionar porque localhost é tratado como origem confiável.

## 3. Para abrir no celular, use HTTPS

Abrir diretamente algo como:

    http://192.168.0.10:8000

normalmente NÃO libera a câmera no navegador do celular.

Uma opção simples para teste é Cloudflare Quick Tunnel.

Com o servidor Python ainda rodando:

    cloudflared tunnel --url http://localhost:8000

Ele imprimirá uma URL parecida com:

    https://alguma-coisa.trycloudflare.com

Abra essa URL no celular.

## 4. Marcador

Use o marcador Hiro oficial do AR.js:

https://raw.githubusercontent.com/AR-js-org/AR.js/master/data/images/hiro.png

Você pode abrir o marcador em outro monitor ou imprimi-lo.

## 5. Se o modelo não aparecer

O exemplo mostra também um pequeno cubo verde.

- Cubo verde aparece, GLB não aparece:
  tracking está funcionando; problema provável é modelo, escala ou caminho.
- Nem o cubo aparece:
  problema provável é câmera/HTTPS/detecção do marcador.
- Mensagem "ERRO ao carregar models/model.glb":
  revise o nome e o arquivo.
- GLB carregado mas parece invisível:
  altere `scale="0.05 0.05 0.05"` no index.html.

Experimente, por exemplo:

    scale="0.001 0.001 0.001"
    scale="0.01 0.01 0.01"
    scale="0.1 0.1 0.1"
    scale="1 1 1"

Modelos de fotogrametria podem ter escalas muito diferentes.

## 6. Diagnóstico no navegador

O topo da tela mostra:

- se a página está em HTTPS;
- se o GLB carregou;
- se o marcador foi detectado.

Também vale abrir o console remoto do Chrome/Android se necessário.
