# RESPONSIVIDADE — DESIGN QUE SE ADAPTA
## Roteiro de apresentação · 50 minutos

**Objetivo:** explicar o que é responsividade, mostrar os principais recursos de HTML/CSS usados para construí-la e envolver a turma em demonstrações e quizzes. **Público:** estudantes de desenvolvimento web, do nível introdutório ao intermediário.

**Antes de começar:** abra `index.html` em Chrome, Edge ou Firefox; use a tecla `F` para tela cheia; navegue com `←` e `→`; pressione `N` para exibir as notas curtas de cada cena. O material foi feito para apresentação ao vivo, e não para passar sozinho. **Não há indicador visual de quantidade de slides ou progresso.** Os 50 minutos dependem de realizar a conversa, os exemplos e as atividades nos tempos sugeridos.

**Preparação dos quizzes:** crie um Kahoot e um Wayground (ou use os dois como formatos alternativos, dependendo do tempo). Faça uma captura de tela de cada QR code e use o botão **Adicionar QR** na respectiva cena para selecionar a imagem. O arquivo de imagem é mostrado localmente no navegador; **essa escolha não é salva dentro do HTML**. Se fechar e reabrir o site, selecione as imagens de novo. Para a apresentação funcionar totalmente offline, substitua a importação opcional da fonte do Google por uma fonte instalada (o CSS já contém fontes alternativas). O acesso aos quizzes externos exige internet.

---

## Organização e falas, cena a cena

### 1. Abertura — 2 min (00:00–02:00)
**Fala sugerida:** “Pensa em quantas telas vocês usaram hoje. Celular, notebook, computador da escola... Será que um site precisa ser feito do zero para cada uma delas? Hoje a gente vai descobrir como a mesma interface se transforma sem perder a identidade.”

**Ação:** mostre a composição com o site no desktop e no celular. Peça que a turma pense em uma experiência ruim em sites móveis.

### 2. O problema — 2 min (02:00–04:00)
**Fala sugerida:** “Quem aqui já entrou num site e teve que dar zoom ou arrastar a página para os lados? Isso geralmente não é culpa do celular: o problema é a interface que não foi preparada para aquele espaço.”

**Ação:** peça duas respostas curtas. Mostre os três problemas: texto ilegível, conteúdo cortado e navegação difícil.

### 3. Definição de responsividade — 3 min (04:00–07:00)
**Fala sugerida:** “Responsividade não é apertar o botão de diminuir tudo. Ela muda a organização das peças. Às vezes um menu vira um ícone; às vezes três colunas viram uma. É a mesma experiência, adaptada.”

**Ponto técnico:** diferencie layout fluido de layout simplesmente reduzido. Exemplifique com cards, navegação e tipografia.

### 4. Vários tamanhos de tela — 2 min (07:00–09:00)
**Fala sugerida:** “É comum pensar em celular, tablet e desktop, mas a situação é mais complexa. Um notebook com a janela pela metade pode ter menos espaço do que um tablet. O que importa é o espaço disponível.”

**Ação:** pergunte se alguém usa duas janelas lado a lado.

### 5. Demonstração interativa — 3 min (09:00–12:00)
**Fala sugerida:** “Agora vou fazer exatamente o que o usuário faz: mudar o espaço disponível. Prestem atenção em quando o conteúdo começa a quebrar.”

**Ação:** arraste o controle de largura de 560 para 250 px com **Layout adaptável desmarcado**; mostre o excesso de conteúdo. Marque **Layout adaptável** e repita. Convide um aluno para escolher a largura. **Mensagem central:** organização flexível vale mais que um tamanho fixo.

### 6. Viewport — 3 min (12:00–15:00)
**Fala sugerida:** “Antes de organizar o CSS, precisamos orientar o navegador. A tag viewport informa que a largura do layout deve acompanhar a largura do dispositivo, em vez de simular uma tela grande.”

**Código a explicar:** `<meta name="viewport" content="width=device-width, initial-scale=1">`.

**Atenção:** a tag não torna um layout responsivo sozinha.

### 7. Unidades flexíveis — 3 min (15:00–18:00)
**Fala sugerida:** “Se eu disser que tudo tem que ter 900 pixels, uma tela de 360 pixels vai sofrer. Mas isso não quer dizer que pixels sejam proibidos. O segredo é escolher a medida certa para cada situação.”

**Exemplos:** `%`, `rem`, `vw`, `min()`, `clamp()`. Em `clamp(2rem, 5vw, 5rem)`, o valor fluido não ultrapassa os limites. `width: min(90%, 1200px)` combina largura relativa com teto.

### 8. Flexbox e Grid — 3 min (18:00–21:00)
**Fala sugerida:** “Se os elementos precisam conversar numa direção, Flexbox resolve muito bem. Se eu quero organizar uma estrutura de linhas e colunas, CSS Grid costuma ser excelente. Não são rivais.”

**Ação:** aponte o menu em Flexbox e a distribuição em Grid. Pergunte: “Qual dos dois vocês usariam para uma galeria de produtos?”

### 9. Grid com auto-fit — 3 min (21:00–24:00)
**Fala sugerida:** “Dá para criar cards que se encaixam praticamente sozinhos. Em vez de decidir que sempre teremos três colunas, eu posso dizer qual é a largura mínima desejada e deixar o navegador encaixar quantas couberem.”

**Código:** `repeat(auto-fit, minmax(min(100%, 220px), 1fr))`.

**Explique:** `auto-fit` ajusta o número de colunas, `minmax()` define limites e `1fr` distribui espaço livre.

### 10. Media queries — 3 min (24:00–27:00)
**Fala sugerida:** “E quando o layout precisa mudar de verdade? Entra a media query. É uma condição: quando a largura atingir certo valor, outras regras passam a valer.”

**Código:** por padrão, `.cards` tem uma coluna; a partir de `min-width: 768px`, ela pode ter três. **Não apresente 768 px como regra universal.**

### 11. Mobile-first — 3 min (27:00–30:00)
**Fala sugerida:** “Mobile-first não é fazer só o celular. É pensar primeiro no espaço mais limitado e depois adicionar recursos quando cabe mais coisa.”

**Ação:** pergunte se mobile-first significa ignorar desktop. Use o botão **Revelar resposta** depois de ouvir a turma.

### 12. Imagens responsivas — 2 min (30:00–32:00)
**Fala sugerida:** “Não adianta todo o texto se ajustar e uma imagem de 1600 pixels empurrar a página para o lado. As mídias também precisam respeitar seus contêineres.”

**Código:** `max-width: 100%`, `height: auto`, `object-fit: cover`. Explique que `object-fit: cover` pode recortar, mas não deforma.

### 13. Desafio de CSS — 3 min (32:00–35:00)
**Fala sugerida:** “Vocês têm um contêiner de conteúdo que precisa caber na tela, mas não pode ultrapassar 1100 pixels. Qual alternativa funciona melhor?”

**Ação:** leia as alternativas sem clicar. Faça votação com dedos ou mãos levantadas e clique na opção escolhida. **Resposta:** C (`width: 100%; max-width: 1100px;`). Explique os erros das outras. Caso queira reutilizar a questão, recarregue o HTML.

### 14. Além da largura — 2 min (35:00–37:00)
**Fala sugerida:** “Um site pode caber na tela e ainda assim ser péssimo de usar. O botão pode ser pequeno para tocar, o contraste pode ser ruim, ou uma imagem pesada pode demorar para carregar.”

**Três dimensões:** usabilidade, acessibilidade e performance. Cite navegação por teclado, zoom e teste de toque.

### 15. Testes com DevTools — 3 min (37:00–40:00)
**Fala sugerida:** “A gente não precisa possuir dez celulares para começar a testar. As ferramentas do navegador simulam larguras e ajudam a encontrar problemas. Mas teste real ainda importa.”

**Ação:** pressione **F12**, abra a visualização de dispositivos e altere a largura da própria apresentação ou de uma página de exemplo. Verifique barra horizontal, menus e imagens. **Observação:** caso as DevTools atrapalhem a projeção, explique o passo a passo usando a tela da apresentação.

### 16. Atividade em duplas — 3 min (40:00–43:00)
**Fala sugerida:** “Escolham um site que vocês conhecem. Em 60 segundos, pensem no que é indispensável no celular. Depois, no que pode mudar de lugar. Por fim, vamos ouvir duas soluções.”

**Dinâmica:** 1 minuto de observação, 1 minuto de proposta, 1 minuto para compartilhar. Pode ser respondida oralmente sem acesso a computadores.

### 17. Kahoot — 3 min (43:00–46:00)
**Fala sugerida:** “Vamos testar o que ficou. Escaneiem o QR code e entrem no jogo. O foco não é só acertar, é conseguir justificar a resposta.”

**Ação:** adicione o QR de uma rodada curta e abra o quiz externo no dispositivo do apresentador. Sugestão: use **3 ou 4 perguntas rápidas**. O site da apresentação apenas exibe a imagem do QR; não cria ou hospeda o jogo.

### 18. Wayground — 2 min (46:00–48:00)
**Fala sugerida:** “Último desafio: agora vocês vão responder situações práticas, pensando como desenvolvedores.”

**Ação:** mostre o QR do Wayground com 2 questões rápidas. Se a conexão estiver ruim, transforme em perguntas orais. **Alternativa de tempo:** se preferir um único quiz, use esta parte para revisar o erro mais comum do Kahoot.

### 19. Encerramento — 2 min (48:00–50:00)
**Fala sugerida:** “O mais importante é lembrar que responsividade não se resume a escrever `@media`. É construir uma interface que continue clara, utilizável e bonita quando o espaço muda. Na próxima página que vocês criarem, pensem: o que acontece se eu diminuir a janela?”

**Ação:** retome viewport, unidades flexíveis, Grid/Flexbox, media queries e testes. Uma pergunta curta para encerrar: “Qual mudança vocês fariam no próximo site?”

---

## Banco de questões para criar o Kahoot

1. **Qual a finalidade principal da tag viewport?** A) Criar um menu móvel; **B) Ajudar o navegador a usar a largura do dispositivo**; C) Instalar uma fonte; D) Substituir o CSS.
2. **Qual ferramenta CSS é especialmente útil para organizar linhas e colunas?** A) `position: fixed`; **B) CSS Grid**; C) `opacity`; D) `z-index`.
3. **O que faz uma media query?** A) Carrega JavaScript; B) Cria um banco de dados; **C) Aplica regras CSS sob condições**; D) Reduz a internet usada.
4. **Mobile-first significa...** A) Criar só um app; **B) Começar pelo layout para telas menores e expandir**; C) Proibir o desktop; D) Usar somente pixels.

## Banco de questões para criar o Wayground

1. **Uma imagem ultrapassa a largura do cartão. Qual combinação normalmente ajuda a manter sua proporção e respeitar o espaço disponível?** A) `min-width: 1000px`; **B) `max-width: 100%; height: auto;`**; C) `width: 200vw`; D) `position: absolute`.
2. **Um layout de três cards deve permitir uma única coluna em larguras menores. Qual é uma solução adequada?** A) Fixar `width: 1200px`; **B) Usar Grid com colunas flexíveis ou media queries**; C) Esconder todos os cards; D) Desabilitar o zoom.
3. **Qual afirmação sobre breakpoints é a melhor?** A) Sempre usar um valor para cada modelo de celular; **B) Escolher os pontos em que o conteúdo precisa mudar de organização**; C) Nunca usar media queries; D) Usar somente 1920px.
4. **O site cabe na tela, mas os botões são minúsculos e difíceis de tocar. Ele está totalmente adequado?** A) Sim, basta caber; **B) Não, usabilidade e acessibilidade também importam**; C) Sim, se o CSS não tiver erros; D) Sim, se tiver mais animações.

## Dicas para apresentação ao vivo

- **Treine com um cronômetro**: as explicações e participação da turma fazem parte dos 50 minutos.
- **Interação de verdade**: a cena da largura possui slider, a questão de CSS reage a cliques e a resposta de mobile-first é revelada sob demanda.
- **Sem conexão**: o HTML e as interações funcionam localmente, exceto o carregamento online das fontes opcionais e os serviços externos Kahoot/Wayground.
- **Acessibilidade**: use as setas para navegar e prefira o modo de tela cheia para projetar. O material respeita a preferência por redução de movimento do navegador.
- **Personalização**: as principais cores estão em variáveis no início do CSS: `--violet`, `--coral`, `--mint`, `--ink`.


## Orientação visual da edição Aranhaverso

Use a abertura “Grandes interfaces vêm com grandes responsabilidades”. Relacione a capacidade do herói de se adaptar a situações à necessidade de interfaces se ajustarem a telas diferentes. Mantenha as demonstrações, o desafio e os tempos originais. Os QR codes devem ser inseridos na hora com os botões das duas cenas de quiz.
