# 🥚 Roube um Ovo: Cyber Lógico

Jogo educativo de invasão, lógica de programação e gerenciamento de recursos. Feito inteiramente no navegador, com React, Tailwind CSS e HTML5 Canvas. É uma experiência individual com robôs controlados pelo próprio jogo (não é multiplayer).

## Como jogar no computador

1. Extraia o ZIP.
2. Abra `index.html` no navegador. Também é possível abrir a pasta no VS Code e usar a extensão Live Server.
3. Clique em **JOGAR**.

Não é necessário instalar dependências, criar uma conta ou configurar uma chave de API. As bibliotecas já estão incluídas e os visuais são desenhados em Canvas e CSS.

## Publicação no GitHub Pages

1. Crie um repositório no GitHub (público para publicação gratuita pelo Pages).
2. Envie **o conteúdo da pasta** `cyber-logico` para a raiz do repositório, incluindo `index.html`, as pastas `css`, `js` e `vendor`, e o arquivo `.nojekyll` (se disponível). Faça o commit na branch `main`.
3. No repositório, vá em **Settings → Pages**.
4. Em **Build and deployment**, selecione **Deploy from a branch**.
5. Escolha a branch `main`, a pasta `/ (root)` e clique em **Save**.
6. Abra o endereço que o GitHub Pages mostrar quando concluir a publicação.

O projeto é estático, não precisa de build nem de GitHub Actions. Os caminhos são relativos e funcionam em repositórios com qualquer nome.

## Controles

- **WASD ou setas:** mover.
- **E ou Espaço:** roubar um ovo próximo / interagir.
- **Esc:** abrir a pausa ou fechar loja/coleção.
- **Celular:** direcional e botão E / AÇÃO abaixo do mapa.
- Entre na sua base para depositar ovos automaticamente, se houver espaço.

## Mecânicas

- Três bases rivais com robôs patrulhando, cones de visão e regeneração de ovos.
- Ovos comuns não têm escudo. Os outros exigem responder um desafio aleatório, com explicação da resposta.
- Se for detectado por tempo suficiente ou tocar um guarda, perca os ovos carregados e retorne ao ninho.
- Ovos depositados geram renda e amadurecem em tempo de jogo. Na coleção, é possível chocá-los quando estiverem prontos, ganhar pontos e moedas e descobrir criaturas com dicas de programação. Chocar encerra a renda daquele ovo.
- Na loja há Botas Turbo, Capa Stealth, Mochila Extra e Novo Pedestal, com níveis e preços progressivos.
- Progresso salvo localmente no navegador, sem renda offline. O jogo pausa nos menus. A mochila é temporária e não é restaurada ao recarregar.

| Raridade | Moedas/s | Tempo de incubação |
|---|---:|---:|
| Comum | 2 | 12 s |
| Raro | 6 | 18 s |
| Épico | 15 | 25 s |
| Lendário | 36 | 35 s |
| Mítico | 85 | 45 s |

## Organização dos arquivos

```text
index.html          Entrada do jogo
css/tailwind.css    Tailwind CSS 4.1.10 compilado
css/game.css        Visual, animações e responsividade
js/data.js          Raridades, desafios, bases e upgrades
js/world.js         Desenho do mapa e personagens no Canvas
js/game.js          Regras, controles, colisões, economia e salvamento
js/app.js           Interface e componentes React
vendor/             React e ReactDOM locais e licenças
```

Para editar os desafios, basta abrir `js/data.js`. As cores e os preços também estão nesse arquivo. Não há APIs externas, Gemini, servidores de jogo ou dependência de CDN.

As bibliotecas React 16 e Tailwind CSS são licenciadas sob MIT; consulte `vendor/`.
