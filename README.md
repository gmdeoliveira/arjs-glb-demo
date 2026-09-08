# ODM Web Viewer Suite

Três páginas para separar os testes de visualização de mapas GLB gerados a partir do ODM.

## 1. `index.html` — AR estável
Carrega sempre `models/stable.glb`. Use aqui apenas um GLB que você já validou.

## 2. `test.html` — AR de teste
Permite selecionar um `.glb` do armazenamento do celular/computador sem fazer upload para o GitHub.
Mostra nome, tamanho, estado de carregamento e permite alterar escala/rotação.

## 3. `viewer.html` — visualizador 3D
Visualizador não-AR com Three.js:
- zoom, rotação e pan;
- upload local e drag-and-drop;
- vistas isométrica/topo/frente/lateral;
- grid, eixos e wireframe;
- enquadramento automático;
- estatísticas de meshes, triângulos, vértices e dimensões;
- suporte a Draco e Meshopt no GLTFLoader.

## Estrutura

```text
odm_web_viewer_suite/
├── index.html
├── test.html
├── viewer.html
├── styles.css
├── .nojekyll
└── models/
    └── stable.glb
```

Copie o modelo já validado para `models/stable.glb`.

## GitHub Pages
Publique a raiz do projeto em `Settings → Pages → Deploy from a branch → main → /(root)`.

As páginas AR usam o marcador Hiro:
https://raw.githubusercontent.com/AR-js-org/AR.js/master/data/images/hiro.png

## Observação
O `viewer.html` é um visualizador de mesh GLB. Para nuvens de pontos muito grandes em LAS/LAZ/COPC, uma futura página baseada em Potree seria mais próxima do CloudCompare.
