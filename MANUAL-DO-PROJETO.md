# Manual do projeto — José Augusto em Missão

Documentação revisada em 14/10/2026.

Este manual explica as páginas, seu desenho, as principais classes usadas no site e como fazer a manutenção. Os esboços representam a organização do código; não são capturas de tela.

## 1. Descrição do projeto

O projeto é um portfólio pessoal de José Augusto, missionário da Igreja Adventista do Sétimo Dia. Apresenta sua história, experiências missionárias, preparação e desejo de servir fora do Brasil.

A narrativa reúne o projeto Um Ano em Missão em Urucará, Amazonas (2025), a Escola de Imersão Transcultural no Instituto de Missões Noroeste (2026) e campanhas de colportagem (2025–2026). O destino internacional ainda não está confirmado.

O site tem uma página principal em português do Brasil, uma página interna de apoio e navegação por seções. Usa HTML para o conteúdo, CSS para a aparência e um pequeno JavaScript local para revelar um convite depois que o vídeo de apresentação terminar. Não há servidor de aplicação, banco de dados, dependências ou etapa de build.

O retrato e as três experiências da trajetória usam imagens em `img/`. A galeria de memórias mantém três espaços reservados até que os registros escolhidos sejam integrados.

## 2. Arquivos e como abrir

| Caminho | Responsabilidade |
| --- | --- |
| [index.html](index.html) | Página principal: conteúdo, vídeo de apresentação, navegação e script local de liberação do convite. |
| [apoio.html](apoio.html) | Página interna de apoio, com caminhos separados para contribuir ou acompanhar a missão. |
| [style.css](style.css) | Estilos compartilhados por `index.html` e `apoio.html`, inclusive regras de celular. |
| [previas/apoio.html](previas/apoio.html) | Prévia exportada anterior; mantida apenas como referência histórica. |
| [previas/apoio-fragmento.html](previas/apoio-fragmento.html) | Fragmento editável da proposta anterior; não é a página de apoio ativa. |
| [LEIA-ME.md](LEIA-ME.md) | Instruções iniciais e estado da entrega. |
| [AGENTS.md](AGENTS.md) | Contexto, conteúdo confirmado e orientações de continuidade. |
| [CONTINUAR-NO-CODEX.txt](CONTINUAR-NO-CODEX.txt) | Texto de orientação para retomar o trabalho. |
| `.openai/hosting.json` | Identidade do Site existente e pasta pública; não contém credenciais. |
| `.gitignore` | Exclusões previstas para uso de Git. |
| [MANUAL-DO-PROJETO.md](MANUAL-DO-PROJETO.md) | Este manual. |

Para consultar este manual no VS Code, abra o arquivo e use **Ctrl+Shift+V** para visualizar o Markdown formatado. Para abrir ao lado do código, use **Ctrl+K V** (Ctrl+K e depois V).

Para visualizar o portfólio, abra `index.html` no navegador. Para abrir diretamente a página interna, use `apoio.html`. Edite no VS Code, salve com **Ctrl+S** e atualize o navegador. Alterações locais não atualizam automaticamente a versão hospedada.

## 3. Esboço da página no computador

Leia de cima para baixo. O conteúdo fica centralizado por `.wrap`, com largura máxima de 1180 px.

```text
┌──────────────────────────────────────────────────────────────────┐
│ CABEÇALHO — header#inicio > .wrap.nav                             │
│ [JA] JOSÉ AUGUSTO     Sobre mim | Projetos | Próximos passos       │
│      Em missão                       Vídeo | Apoie (apoio.html)   │
│      .brand + .brand-mark                  nav > a               │
├──────────────────────────────────────────────────────────────────┤
│ APRESENTAÇÃO — .hero (fundo azul profundo)                        │
│ .hero-grid                                                       │
│ ┌────────────────────────────────┐ ┌───────────────────────────┐ │
│ │ .eyebrow                       │ │ .portrait-frame           │ │
│ │ Uma vida a serviço.        h1   │ │ ┌───────────────────────┐ │ │
│ │ Um chamado para ir.            │ │ │ .placeholder.portrait │ │ │
│ │ Apresentação pessoal   .intro  │ │ │    Retrato em img/    │ │ │
│ │ [Conheça minha trajetória]     │ │ └───────────────────────┘ │ │
│ │ .button → #projetos            │ │ .portrait-label           │ │
│ └────────────────────────────────┘ └───────────────────────────┘ │
│ .hero-foot — Portfólio missionário / Fé / Serviço / Propósito    │
├──────────────────────────────────────────────────────────────────┤
│ 01 / QUEM SOU — section#sobre > .wrap.about                       │
│ ┌────────────────────────────┐ ┌───────────────────────────────┐ │
│ │ .eyebrow + h2              │ │ .lead + parágrafos            │ │
│ │ O chamado começa...        │ │ .tags > .tag .tag .tag        │ │
│ └────────────────────────────┘ └───────────────────────────────┘ │
├──────────────────────────────────────────────────────────────────┤
│ 02 / TRAJETÓRIA — section#projetos.projects                       │
│ .section-head — título e texto de abertura                       │
│ ┌────────────────────────────┐ ┌───────────────────────────────┐ │
│ │ Imagem em img/             │ │ .meta > .year + local         │ │
│ │                            │ │ h3 + p + .detail              │ │
│ └────────────────────────────┘ └───────────────────────────────┘ │
│ .project × 3: Urucará / Formação no IMN / Colportagem             │
├──────────────────────────────────────────────────────────────────┤
│ 03 / FUTURO — section#objetivos.goals (fundo azul profundo)        │
│ .section-head                                                   │
│ .goal-grid                                                      │
│ ┌──────────────────┐ ┌──────────────────┐ ┌──────────────────┐ │
│ │ .goal            │ │ .goal            │ │ .goal            │ │
│ │ .number 01.      │ │ .number 02.      │ │ .number 03.      │ │
│ │ Servir fora      │ │ Continuar o     │ │ Palavra e       │ │
│ │ do Brasil        │ │ preparo         │ │ cuidado          │ │
│ └──────────────────┘ └──────────────────┘ └──────────────────┘ │
│                                                                    │
├──────────────────────────────────────────────────────────────────┤
│ 04 / VÍDEO — section#video.video-section                          │
│ Texto de contexto + caminho alternativo para apoio                 │
│ .video-card: vídeo ou aviso temporário                             │
│ Ao terminar o vídeo: [Eu quero contribuir] → apoio.html            │
├──────────────────────────────────────────────────────────────────┤
│ 05 / MEMÓRIAS — section#registros                                │
│ .section-head — Histórias para guardar.                          │
│ .gallery-grid                                                   │
│ ┌──────────────────┐ ┌──────────────────┐ ┌──────────────────┐ │
│ │ Foto reservada   │ │ Foto reservada   │ │ Foto reservada   │ │
│ │ + legenda        │ │ + legenda        │ │ + legenda        │ │
│ └──────────────────┘ └──────────────────┘ └──────────────────┘ │
│ Cada item: figure > .placeholder + figcaption                    │
├──────────────────────────────────────────────────────────────────┤
│ RODAPÉ — footer > .wrap.footer                                   │
│ Nome               Frase                  Voltar ao início ↑    │
└──────────────────────────────────────────────────────────────────┘
```

## 4. Esboço no celular e adaptação

```text
┌──────────────────────────────┐
│ JA  JOSÉ AUGUSTO / Em missão  │
│ Links do menu em linhas      │
├──────────────────────────────┤
│ Frase de abertura            │
│ Título principal             │
│ Apresentação                 │
│ [Conheça minha trajetória]   │
│ Retrato                      │
│ Identificação                │
│ Faixa .hero-foot             │
├──────────────────────────────┤
│ 01 / Quem sou                │
│ Título, textos e etiquetas   │
├──────────────────────────────┤
│ 02 / Minha trajetória        │
│ Foto → texto do projeto 1    │
│ Foto → texto do projeto 2    │
│ Foto → texto do projeto 3    │
├──────────────────────────────┤
│ 03 / Olhando para o futuro   │
│ Objetivo 01                  │
│ Objetivo 02                  │
│ Objetivo 03                  │
├──────────────────────────────┤
│ 04 / Vídeo de apresentação   │
│ Aviso temporário ou vídeo     │
│ Caminho visível para apoio    │
├──────────────────────────────┤
│ 05 / Memórias da missão      │
│ Foto 1 + legenda             │
│ Foto 2 + legenda             │
│ Foto 3 + legenda             │
├──────────────────────────────┤
│ Nome, frase e link de retorno│
└──────────────────────────────┘
```

| Regra CSS | Comportamento previsto pelo código |
| --- | --- |
| Base, acima de 850 px | Layout amplo; `.wrap` usa `calc(100% - 80px)`; apresentação, biografia, projetos e vídeo em duas colunas; objetivos e galeria em três. A página de apoio apresenta dois cartões lado a lado. |
| `@media(max-width:850px)` | Margens laterais de 20 px; espaçamentos menores; cabeçalho e faixa da apresentação podem quebrar linha. |
| `@media(max-width:600px)` | Grids em uma coluna; menu ocupa uma linha própria e pode quebrar; vídeo e cartões de apoio ficam empilhados; rodapé e retorno do apoio se organizam verticalmente; último texto de `.hero-foot` oculto. |
| `@media(prefers-reduced-motion:reduce)` | Desativa a rolagem suave para respeitar a preferência do visitante. |

As regras até 600 px se somam às de 850 px e substituem propriedades quando necessário. O menu permanece visível: não existe menu hambúrguer. O cabeçalho não é fixo.

## 5. Como ler o código

Uma **tag** define o tipo de elemento (`section`, `p`, `a`). Uma **classe** reutiliza um estilo (`class="project"`). Um **ID** identifica um elemento específico (`id="projetos"`).

```html
<section class="projects" id="projetos">
  <div class="wrap">
    <!-- Conteúdo da seção -->
  </div>
</section>
```

Nesse exemplo, `.projects` determina o estilo da seção, `#projetos` é o destino da navegação e `.wrap` limita a largura. O ponto e o `#` são usados nos seletores CSS; não são escritos dentro dos atributos `class` e `id`.

`class="wrap nav"` aplica duas classes ao mesmo elemento. Já `.project .placeholder` seleciona um espaço de foto **dentro** de um projeto. `.section-head > p` seleciona o parágrafo filho direto do cabeçalho da seção.

`index.html` contém, nesta ordem: metadados no `<head>`, referência a `style.css`, símbolo SVG de foto, cabeçalho, conteúdo em `<main>`, rodapé e o pequeno script do vídeo. `apoio.html` referencia o mesmo `style.css`. Procure pelos nomes com **Ctrl+F**, sem depender de números de linha.

## 6. Catálogo das classes atuais

As classes abaixo são usadas em `index.html`, `apoio.html` e `style.css`. Elas são classes CSS, não classes de programação orientada a objetos.

| Classe | Onde aparece e qual sua função |
| --- | --- |
| `.wrap` | Centraliza e limita a largura dos blocos; compartilhada por toda a página. |
| `.nav` | Organiza marca e menu com Flexbox no cabeçalho. Diferente da tag `nav`, que agrupa os links. |
| `.brand` | Link da marca; alinha monograma e nome; aponta para `#inicio`. |
| `.brand-mark` | Quadrado com as iniciais JA, borda e texto dourados. |
| `.hero` | Área de apresentação com fundo azul, texto claro e espaçamento. |
| `.hero-grid` | Grade do texto de abertura e retrato. |
| `.eyebrow` | Pequeno rótulo acima dos títulos; letras espaçadas e traço decorativo antes do texto. |
| `.intro` | Parágrafo de apresentação, com largura e cor próprias. |
| `.button` | Aparência de botão do link para a trajetória; não é um botão JavaScript. |
| `.portrait-frame` | Moldura do retrato; referência de posicionamento para a identificação. |
| `.placeholder` | Bloco genérico de foto reservada, com borda tracejada, ícone e texto centralizados. |
| `.portrait` | Variação do espaço reservado para o retrato, com fundo escuro e proporção própria. Usada com `.placeholder`. |
| `.portrait-label` | Faixa dourada sobreposta à parte inferior da moldura, com nome e identificação. |
| `.hero-foot` | Faixa inferior da apresentação, com linha divisória e frases curtas. |
| `.about` | Grade da biografia: título de um lado, texto do outro. |
| `.lead` | Parágrafo maior e mais destacado na biografia e na apresentação do vídeo. |
| `.tags` | Agrupa etiquetas temáticas e permite quebra de linha. |
| `.tag` | Uma etiqueta com borda, como “Missão e serviço”. |
| `.projects` | Fundo branco e bordas da seção de trajetória. |
| `.section-head` | Alinha título da seção e texto de abertura; reutilizada em trajetória, objetivos e registros. |
| `.project` | Um artigo da trajetória; foto e conteúdo em grade, com separador superior. |
| `.meta` | Linha que agrupa ano e localização/instituição de um projeto. |
| `.year` | Selo azul com o ano ou período. |
| `.detail` | Observação complementar do projeto, com borda dourada à esquerda. |
| `.goals` | Fundo azul e texto claro da seção de objetivos. |
| `.goal-grid` | Grade dos três objetivos. |
| `.goal` | Um objetivo, com borda superior e espaçamento. |
| `.number` | Número dourado de cada objetivo. |
| `.video-section` | Seção clara do vídeo de apresentação, entre os objetivos e os registros. |
| `.video-layout` | Grade que alinha o texto de contexto ao cartão do vídeo. No celular passa a uma coluna. |
| `.video-card` | Área azul que contém o vídeo ou, enquanto ele não existir, o aviso temporário. |
| `.presentation-video` | Elemento `<video>` inicialmente oculto, exibido quando houver uma URL direta configurada em `data-src`. |
| `.video-placeholder` | Aviso visível enquanto não há vídeo configurado. |
| `.video-contribute` | Link “Eu quero contribuir”, oculto até o evento de término do vídeo. |
| `.text-link` | Link textual sublinhado usado no caminho alternativo para apoio e no retorno ao portfólio. |
| `.gallery-grid` | Grade dos três registros; também define aparência das fotos reservadas e legendas internas. |
| `.footer` | Alinha os elementos internos do rodapé; a tag `footer` aplica borda e espaçamento externos. |

### Classes exclusivas da página de apoio

| Classe | Onde aparece e qual sua função |
| --- | --- |
| `.support-hero` | Abertura azul da página `apoio.html`. |
| `.support-options` | Contêiner das duas formas independentes de participação. |
| `.support-grid` | Grade com os cartões de contribuição e acompanhamento; no celular passa a uma coluna. |
| `.support-card` | Cartão de uma opção de apoio, com texto e controle correspondente. |
| `.support-card-dark` | Variação azul do cartão “Acompanhar a missão”. |
| `.support-note` | Aviso de que os dados ou o convite ainda não foram fornecidos. |
| `.button-disabled` | Estado visual e não interativo dos botões pendentes. |
| `.button-outline` | Variante transparente, usada no botão de WhatsApp quando for ativado. |
| `.support-return` e `.return-content` | Faixa de retorno ao vídeo e ao portfólio. |

### Seletores sem classe e estados visuais

| Seletor | Função |
| --- | --- |
| `:root` | Declara as variáveis de cor. |
| `*` | Aplica `box-sizing:border-box`, incluindo borda e preenchimento no cálculo das dimensões. |
| `html` | Define rolagem suave e folga de 90 px no destino das âncoras. |
| `body` | Remove margem padrão, aplica fonte, cor, fundo e altura de linha. |
| `a`, `a:focus-visible` | Cor herdada e contorno dourado de foco para os links. |
| `header`, `nav`, `nav a` | Aparência do cabeçalho e dos links de navegação. |
| `h1`, `h2`, `h3`, `p` | Hierarquia tipográfica e margens; `h1 em` destaca parte do título em dourado. |
| `section`, `footer` | Espaçamento das seções e acabamento do rodapé. |
| `nav a:hover`, `.button:hover` | Mudança de cor ao passar o ponteiro. |
| `.eyebrow:before` | Desenha o pequeno traço anterior ao rótulo, sem imagem externa. |
| `.hero-foot span:first-child` | Destaca o primeiro texto da faixa. |
| `.hero-foot span:last-child` | Oculta o último texto da faixa na regra de celular. |
| `.video-contribute[hidden]` | Mantém o convite de contribuição fora da página até o vídeo terminar. |
| `.button-disabled` | Indica visualmente um controle ainda indisponível; o atributo HTML `disabled` impede o clique. |
| `.placeholder svg`, `span`, `small` dentro dos seletores correspondentes | Dimensionam ícone, texto e observação dos espaços reservados. |
| `.gallery-grid figure`, `.gallery-grid figcaption` | Removem a margem padrão da figura e formatam sua legenda. |

## 7. Identidade visual e funções CSS

| Variável | Valor | Uso |
| --- | --- | --- |
| `--navy` | `#0c2836` | Azul principal: cabeçalho, apresentação, objetivos e selos. |
| `--navy2` | `#153c4c` | Fundo do retrato reservado. |
| `--gold` | `#e7bc71` | Destaques, botão, identificação, números e foco. |
| `--ink` | `#163440` | Texto escuro principal. |
| `--muted` | `#526873` | Texto secundário. |
| `--paper` | `#f8fafb` | Fundo claro da página. |
| `--line` | `#dce4e8` | Bordas e divisórias claras. |

Os títulos `h1` e `h2` usam Georgia, com alternativas Times New Roman e serif. O corpo usa Arial, Helvetica e sans-serif. Outros elementos, como títulos dos objetivos, o aviso do vídeo e o retorno da página de apoio, também recebem Georgia explicitamente. Nem toda cor está em variável: há valores diretos para tons auxiliares e transparências.

Além do pequeno script do vídeo descrito na seção 8, estas são as **funções nativas de CSS** usadas no visual:

| Função | Exemplo real | O que faz |
| --- | --- | --- |
| `var()` | `var(--navy)` | Lê uma variável CSS. |
| `calc()` | `calc(100% - 80px)` | Calcula a largura disponível descontando as margens laterais. |
| `clamp()` | `clamp(48px,5.8vw,78px)` | Faz o título variar com a tela, entre mínimo e máximo; regras menores sobrescrevem o tamanho do `h1`. |
| `repeat()` | `repeat(3,1fr)` | Cria três colunas de largura igual na grade de objetivos. |

## 8. IDs, links e funcionalidades

| ID | Elemento | Quem o utiliza |
| --- | --- | --- |
| `inicio` | Cabeçalho | Marca e link “Voltar ao início”. |
| `sobre` | Seção de biografia | Link “Sobre mim”. |
| `projetos` | Seção de trajetória | Link “Projetos” e botão “Conheça minha trajetória”. |
| `objetivos` | Seção de objetivos | Link “Próximos passos”. |
| `video` | Seção de apresentação em vídeo | Link “Vídeo” e retorno a partir de `apoio.html`. |
| `video-apresentacao` | Elemento `<video>` | Script local que escuta o fim da reprodução. |
| `video-contribute` | Link para `apoio.html` | Fica oculto até o vídeo terminar. |
| `registros` | Seção de galeria | Link “Registros”. |
| `photo` | `<symbol>` SVG oculto | Elementos `<use href="#photo">`; é um desenho reutilizado, não uma seção de navegação. |

O navegador faz a navegação por âncoras sozinho: `<a href="#projetos">` encontra `id="projetos"` e rola até ele. O link `href="apoio.html"` abre a página interna de apoio.

O único script do site procura o vídeo e o link de contribuição. Quando o navegador emite o evento `ended` — isto é, quando a reprodução chega realmente ao fim — ele remove o estado `hidden` do convite “Eu quero contribuir”. Não há contagem de doações, pagamentos, integração com banco ou comunicação automática.

O ícone da aba é um SVG embutido no atributo `href` do `<link rel="icon">`. O ícone dos espaços de foto também é SVG embutido. Nenhum dos dois depende de um arquivo de imagem externo.

Há `lang="pt-BR"`, estrutura semântica, rótulo acessível no menu, foco visível e respeito à preferência de movimento reduzido. Os ícones decorativos usam `aria-hidden="true"`. Isso descreve recursos presentes; não equivale a uma auditoria completa de acessibilidade.

## 9. Vídeo e página interna de apoio

### Vídeo de apresentação

`index.html` inclui a seção `#video`, entre os objetivos e os registros. Enquanto o vídeo não foi fornecido, o visitante vê um aviso temporário e um caminho sempre visível para `apoio.html`; assim, o acesso ao apoio não depende de assistir ao vídeo.

O elemento `<video id="video-apresentacao">` tem `data-src=""`. Para ativá-lo, informe um arquivo de vídeo local ou uma URL direta de mídia compatível, normalmente `.mp4`. O valor será colocado em `data-src`; o script atribui esse valor a `video.src`, exibe o reprodutor e oculta o aviso. Links de páginas de plataformas de vídeo não são necessariamente URLs diretas de mídia.

Ao fim da reprodução, o script mostra o link “Eu quero contribuir”. Esse link apenas abre `apoio.html`; não registra interesse, contato nem recebimento de valor.

### Página `apoio.html`

Esta página tem duas opções independentes, para que uma pessoa possa acompanhar a missão sem fazer uma contribuição financeira:

| Opção | Conteúdo atual | Estado |
| --- | --- | --- |
| **Contribuir com a missão** | Explica que o apoio pode cobrir passagens, passaporte, visto e seguro. | O controle está desativado enquanto não há meios reais de contribuição. |
| **Acompanhar a missão** | Convida a acompanhar, orar e divulgar. | O botão “Entrar no grupo do WhatsApp” está desativado enquanto não há convite real. |

O apoio financeiro pode ser feito pela chave Pix exibida ou pelo link da plataforma de doação. O QR Code abre a mesma página da plataforma. O botão “Copiar chave Pix” usa a área de transferência do navegador; se ela não estiver disponível, o visitante ainda pode copiar a chave exibida. O grupo de WhatsApp também está ativo. A página não confirma recebimento de doações.

### Dados necessários para ativação

Antes de transformar os controles pendentes em links ou apresentar informações reais, obtenha somente:

1. Arquivo ou URL direta do vídeo de apresentação.
2. Fotos e legendas para os três espaços da galeria, quando desejado.

Após receber os dados, teste os destinos em uma janela privada, confira a leitura no celular e mantenha as duas opções separadas. Não publique nem altere a audiência do Site sem confirmação explícita.

### Prévia anterior

Os arquivos em `previas/` permanecem no pacote apenas como referência da proposta anterior. `previas/apoio.html` contém um invólucro de visualização exportado; `previas/apoio-fragmento.html` contém o fragmento editável correspondente. Eles não têm sincronização automática com a página `apoio.html` atual e não devem ser usados para presumir funcionalidades de pagamento, WhatsApp, compartilhamento ou download.

## 10. Guia de manutenção

### Alterar textos

1. Abra `index.html` ou `apoio.html` e procure uma frase com **Ctrl+F**.
2. Altere apenas o conteúdo entre as tags, preservando a estrutura.
3. Salve e atualize o navegador.

O título da aba fica em `<title>`. A descrição para mecanismos de busca fica em `<meta name="description">`. O título visível de abertura fica em `<h1>`.

### Alterar cores e espaçamentos

Procure `:root` em `style.css` para as cores principais. Procure a classe do bloco no catálogo para ajustar sua aparência. Preserve a identidade azul e dourada. Ao alterar uma regra, verifique se ela é sobrescrita nos blocos `@media` de 850 e 600 px.

Classes compartilhadas têm efeito em vários lugares: mudar `.placeholder` afeta os sete espaços de foto; mudar `.section-head` afeta três seções. Um ajuste exclusivo de projeto deve usar um seletor como `.project .placeholder`.

### Inserir fotografias futuramente

As imagens atualmente usadas pela página estão em `img/`; os registros adicionais estão em `galeria/`. Ao adicionar uma foto nova, mantenha-a em uma dessas pastas ou crie uma pasta clara no mesmo nível de `index.html`. Os caminhos partem de `index.html`: por exemplo, use `img/nome-do-arquivo.jpg`.

Ao substituir um bloco reservado por `<img>`, será necessário definir o estilo da imagem: as regras atuais de `.placeholder` foram feitas para contêineres de ícone e texto. Exemplo didático para **uma foto de projeto**, ainda não implementado:

```html
<!-- Substituir o div.placeholder do projeto por esta imagem.
     O arquivo e a descrição devem corresponder à foto real. -->
<img class="project-photo" src="img/foto-do-projeto.jpg"
     alt="Descrição objetiva da fotografia escolhida" loading="lazy">
```

```css
/* Classe nova sugerida; não existe na versão atual. */
.project-photo {
  display: block;
  width: 100%;
  aspect-ratio: 1.55;
  object-fit: cover;
}
```

`object-fit:cover` pode recortar a foto; confira o enquadramento. O retrato e a galeria têm proporções diferentes e devem receber ajustes próprios. Escreva o `alt` a partir da imagem real, sem inventar pessoas, locais ou acontecimentos.

### Adicionar uma experiência

Duplique um `<article class="project">` dentro de `#projetos`. Atualize ano, local, título, descrição, detalhe e imagem com conteúdo confirmado. A classe `.project` pode ser repetida; IDs devem continuar únicos.

### Adicionar uma seção ou mudar a navegação

Crie um ID único e use o mesmo valor no link, como `href="#nova-secao"` e `id="nova-secao"`. Ajuste a numeração editorial das seções quando necessário. Para uma página interna, use um caminho relativo, como `href="apoio.html"`.

### Ativar o vídeo e os controles de apoio

Não preencha valores fictícios. Quando os dados reais forem fornecidos, faça as alterações abaixo e teste localmente:

1. Em `index.html`, preencha `data-src` do elemento `#video-apresentacao` com um arquivo ou URL direta de vídeo compatível. Não remova o link alternativo para `apoio.html`.
2. Em `apoio.html`, mantenha a chave Pix, o link da plataforma e o convite de WhatsApp atualizados. Não escreva que uma doação foi recebida sem confirmação real.
3. Se for trocar qualquer URL, teste o destino em uma janela privada. A opção de acompanhar deve continuar disponível também para quem não contribuiu.
4. Confira os links, o final do vídeo e o comportamento em tela estreita antes de qualquer publicação.

## 11. Verificação após futuras alterações

1. Abra a página no navegador e confira leitura, acentos e ordem das seções.
2. Teste os links do menu, o botão da trajetória, a marca, o retorno ao início e os caminhos entre `index.html` e `apoio.html`.
3. Confira telas amplas e estreitas, incluindo proximidades de 850 e 600 px; procure cortes e rolagem horizontal indesejada.
4. Use Tab para percorrer os links e confirme o foco visível.
5. Se houver novas fotos, confira caminhos, enquadramento e textos alternativos.
6. Confira que o caminho alternativo para apoio aparece mesmo sem vídeo e que “Eu quero contribuir” começa oculto. Com um vídeo real configurado, confirme que ele só aparece depois do término.
7. Em `apoio.html`, teste o botão de copiar Pix, o link da plataforma, o QR Code e o convite do WhatsApp separadamente.

Não há suíte de testes ou etapa de compilação exigida para a página estática. Este manual documenta o código existente; a lista acima orienta a validação quando o site for alterado.

## 12. Repositório e publicação

O repositório Git ativo usa a ramificação `main` e o remoto `origin` aponta para `https://github.com/joseagustobritolinhares/Augusto-em-Miss-o.git`. Um `git push origin main` envia as alterações revisadas para esse repositório.

O repositório pode estar integrado ao GitHub Pages, mas a URL pública e a origem configurada no Pages devem ser confirmadas no GitHub. Um push atualiza o repositório, não garante por si só outra hospedagem. O arquivo `.openai/hosting.json` é um registro legado que aponta para `dist/`, pasta ausente nesta cópia; não o use para publicar sem uma reconfiguração explícita.

Editar ou salvar arquivos locais não publica mudanças. A página de apoio não deve ser descrita como um sistema de doações pronto até que os dados reais e os meios de contribuição tenham sido configurados e testados.
