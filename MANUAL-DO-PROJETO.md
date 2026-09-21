# Manual do projeto — José Augusto em Missão

Documentação da cópia local, revisada em 21/09/2026.

Este manual explica a página, seu desenho, todas as classes usadas no site principal e como fazer a manutenção. A prévia de apoio tem um catálogo separado. Os esboços representam a organização do código; não são capturas de tela.

## 1. Descrição do projeto

O projeto é um portfólio pessoal de José Augusto, missionário da Igreja Adventista do Sétimo Dia. Apresenta sua história, experiências missionárias, preparação e desejo de servir fora do Brasil.

A narrativa reúne o projeto Um Ano em Missão em Urucará, Amazonas (2025), a Escola de Imersão Transcultural no Instituto de Missões Noroeste (2026) e campanhas de colportagem (2025–2026). O destino internacional ainda não está confirmado.

O site é uma única página em português do Brasil, com navegação por seções. Usa HTML para o conteúdo e CSS para a aparência. **Não há JavaScript, funções de programação, servidor de aplicação ou banco de dados em `dist/index.html`.** Não é necessário instalar dependências nem executar um build.

Há sete espaços intencionais para fotografias: um retrato, três fotos de projetos e três registros. Eles ainda não contêm fotos pessoais.

## 2. Arquivos e como abrir

| Caminho | Responsabilidade |
| --- | --- |
| [dist/index.html](dist/index.html) | Página principal: conteúdo, CSS e ícones SVG no mesmo arquivo. |
| [previas/apoio.html](previas/apoio.html) | Prévia independente, com estrutura de visualização exportada. |
| [previas/apoio-fragmento.html](previas/apoio-fragmento.html) | HTML e CSS editáveis da proposta de apoio. |
| [LEIA-ME.md](LEIA-ME.md) | Instruções iniciais e estado da entrega. |
| [AGENTS.md](AGENTS.md) | Contexto, conteúdo confirmado e orientações de continuidade. |
| [CONTINUAR-NO-CODEX.txt](CONTINUAR-NO-CODEX.txt) | Texto de orientação para retomar o trabalho. |
| `.openai/hosting.json` | Identidade do Site existente e pasta pública; não contém credenciais. |
| `.gitignore` | Exclusões previstas para uso de Git. |
| [MANUAL-DO-PROJETO.md](MANUAL-DO-PROJETO.md) | Este manual. |

Para consultar este manual no VS Code, abra o arquivo e use **Ctrl+Shift+V** para visualizar o Markdown formatado. Para abrir ao lado do código, use **Ctrl+K V** (Ctrl+K e depois V).

Para visualizar o site, abra `dist/index.html` no navegador. Edite no VS Code, salve com **Ctrl+S** e atualize o navegador. Alterações locais não atualizam automaticamente a versão hospedada.

## 3. Esboço da página no computador

Leia de cima para baixo. O conteúdo fica centralizado por `.wrap`, com largura máxima de 1180 px.

```text
┌──────────────────────────────────────────────────────────────────┐
│ CABEÇALHO — header#inicio > .wrap.nav                             │
│ [JA] JOSÉ AUGUSTO     Sobre mim | Projetos | Próximos passos       │
│      Em missão                                     | Registros   │
│      .brand + .brand-mark                  nav > a               │
├──────────────────────────────────────────────────────────────────┤
│ APRESENTAÇÃO — .hero (fundo azul profundo)                        │
│ .hero-grid                                                       │
│ ┌────────────────────────────────┐ ┌───────────────────────────┐ │
│ │ .eyebrow                       │ │ .portrait-frame           │ │
│ │ Uma vida a serviço.        h1   │ │ ┌───────────────────────┐ │ │
│ │ Um chamado para ir.            │ │ │ .placeholder.portrait │ │ │
│ │ Apresentação pessoal   .intro  │ │ │    Retrato reservado  │ │ │
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
│ │ Foto: .placeholder         │ │ .meta > .year + local         │ │
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
│ .closing — Disponível para ir. Disposto a servir.                │
├──────────────────────────────────────────────────────────────────┤
│ 04 / MEMÓRIAS — section#registros                                │
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
│ Retrato reservado            │
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
│ Frase de encerramento        │
├──────────────────────────────┤
│ 04 / Memórias da missão      │
│ Foto 1 + legenda             │
│ Foto 2 + legenda             │
│ Foto 3 + legenda             │
├──────────────────────────────┤
│ Nome, frase e link de retorno│
└──────────────────────────────┘
```

| Regra CSS | Comportamento previsto pelo código |
| --- | --- |
| Base, acima de 850 px | Layout amplo; `.wrap` usa `calc(100% - 80px)`; apresentação, biografia e projetos em duas colunas; objetivos e galeria em três. |
| `@media(max-width:850px)` | Margens laterais de 20 px; espaçamentos menores; cabeçalho e faixa da apresentação podem quebrar linha. |
| `@media(max-width:600px)` | Grids em uma coluna; menu ocupa uma linha própria e pode quebrar; rodapé e encerramento empilhados; último texto de `.hero-foot` oculto. |
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

O arquivo principal contém, nesta ordem: metadados no `<head>`, estilos em `<style>`, símbolo SVG de foto, cabeçalho, conteúdo em `<main>` e rodapé. O CSS está compactado em poucas linhas; procure pelos nomes com **Ctrl+F**, sem depender de números de linha.

## 6. Catálogo completo das classes da página principal

As classes abaixo estão em `dist/index.html`. Elas são classes CSS, não classes de programação orientada a objetos.

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
| `.lead` | Primeiro parágrafo da biografia, maior e mais destacado. Estilizado por `.about .lead`. |
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
| `.closing` | Encerramento dos objetivos, com frase e assinatura. |
| `.gallery-grid` | Grade dos três registros; também define aparência das fotos reservadas e legendas internas. |
| `.footer` | Alinha os elementos internos do rodapé; a tag `footer` aplica borda e espaçamento externos. |

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

Os títulos `h1` e `h2` usam Georgia, com alternativas Times New Roman e serif. O corpo usa Arial, Helvetica e sans-serif. Alguns outros elementos, como títulos dos objetivos e frase de encerramento, também recebem Georgia explicitamente. Nem toda cor está em variável: há valores diretos para tons auxiliares e transparências.

Não existem funções JavaScript no site principal. Estas são as **funções nativas de CSS** usadas nele:

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
| `registros` | Seção de galeria | Link “Registros”. |
| `photo` | `<symbol>` SVG oculto | Elementos `<use href="#photo">`; é um desenho reutilizado, não uma seção de navegação. |

O navegador faz a navegação sozinho: `<a href="#projetos">` encontra `id="projetos"` e rola até ele. Não há função `scrollToSection()` ou equivalente no código.

O ícone da aba é um SVG embutido no atributo `href` do `<link rel="icon">`. O ícone dos espaços de foto também é SVG embutido. Nenhum dos dois depende de um arquivo de imagem externo.

Há `lang="pt-BR"`, estrutura semântica, rótulo acessível no menu, foco visível e respeito à preferência de movimento reduzido. Os ícones decorativos usam `aria-hidden="true"`. Isso descreve recursos presentes; não equivale a uma auditoria completa de acessibilidade.

## 9. Prévia de apoio — proposta separada

A seção “Faça parte desta missão” ainda não está em `dist/index.html`. O local proposto é entre objetivos e registros. Nessa proposta, apoio recebe o número 04 e memórias passa a 05; a página principal continua com memórias em 04.

```text
┌────────────────────────────────────────────────────────┐
│ .topo — resumo do chamado                              │
├────────────────────────────────────────────────────────┤
│ .corpo                                                 │
│ .rotulo + h2 — Faça parte desta missão                  │
│ .texto — explicação do apoio                           │
│ .custos — Passagens | Passaporte e visto | Seguro       │
│ .acoes — [Patrocinar ▸] [Contribuir ▸]                  │
│ .oracao                                                │
│ ┌────────────────────────────┐ ┌─────────────────────┐ │
│ │ .divulgacao: texto e ações │ │ .arte               │ │
│ │ [WhatsApp ▸]               │ │ .foto reservada     │ │
│ │ [Copiar link ▸]            │ │ Frase de divulgação │ │
│ │ [Baixar imagem ▸]          │ │                     │ │
│ └────────────────────────────┘ └─────────────────────┘ │
├────────────────────────────────────────────────────────┤
│ .rodape — indicação da próxima seção de memórias        │
└────────────────────────────────────────────────────────┘
```

### Classes do conteúdo editável da prévia

O contêiner tem `id="missao-corrigida"`. Os estilos específicos são prefixados por `#missao-corrigida` para limitar sua aplicação a esse conteúdo.

| Classe | Função em `previas/apoio-fragmento.html` |
| --- | --- |
| `.topo` | Faixa azul de contexto acima da proposta. |
| `.marca` | Identificação em dourado no topo. |
| `.corpo` | Área principal da seção de apoio. |
| `.rotulo` | Numeração e nome curto da seção. |
| `.texto` | Parágrafo em cor secundária. |
| `.custos` | Agrupa etiquetas dos custos previstos. |
| `.acoes` | Organiza os controles expansíveis. |
| `.principal` | Destaca em dourado o `summary` da opção de patrocínio. |
| `.cursor-interaction` | Classe nos `summary`; o invólucro exportado define o cursor. Não há regra para ela no fragmento isolado. |
| `.oracao` | Texto sobre participação por oração e divulgação. |
| `.divulgacao` | Grade da explicação de compartilhamento e modelo de arte. |
| `.arte` | Cartão azul que representa a futura arte de divulgação. |
| `.foto` | Espaço de foto dentro do modelo de arte. |
| `.rodape` | Indicação da próxima seção, “Memórias da missão”. |

Até 540 px, `.divulgacao` passa a uma coluna. A função CSS `minmax(0, ...)` define as colunas na versão ampla, permitindo que encolham sem um mínimo automático de conteúdo.

### Comportamento dos controles e scripts da exportação

O fragmento não possui JavaScript. Cada controle usa `<details>` e `<summary>`: ao clicar, o navegador expande ou recolhe uma explicação. Isso **não envia mensagens, recebe pagamentos, copia links ou baixa uma imagem**.

`previas/apoio.html` é diferente: contém um `iframe` e código genérico gerado pela ferramenta de visualização, incluindo scripts de inicialização, comunicação, dimensionamento e persistência local de estado. Por exemplo, `parseState(serializedState)` valida o estado serializado antes de restaurá-lo ou salvá-lo. Esse código é infraestrutura da prévia, não uma funcionalidade missionária nem parte do site principal.

O catálogo desta seção cobre todas as classes do **fragmento editável**, não as classes e funções genéricas do invólucro exportado. Para manter textos e layout da proposta, a referência é `apoio-fragmento.html`; não há sincronização automática entre ele, a prévia exportada e o site principal.

Antes de implementar contato e contribuição, faltam os dados escolhidos pelo usuário. Para uma arte com retrato real, falta a fotografia. Publicação e audiência devem ser definidas antes de ativar divulgação pública.

## 10. Guia de manutenção

### Alterar textos

1. Abra `dist/index.html` e procure uma frase com **Ctrl+F**.
2. Altere apenas o conteúdo entre as tags, preservando a estrutura.
3. Salve e atualize o navegador.

O título da aba fica em `<title>`. A descrição para mecanismos de busca fica em `<meta name="description">`. O título visível de abertura fica em `<h1>`.

### Alterar cores e espaçamentos

Procure `:root` para as cores principais. Procure a classe do bloco no catálogo para ajustar sua aparência. Preserve a identidade azul e dourada. Ao alterar uma regra, verifique se ela é sobrescrita nos blocos `@media` de 850 e 600 px.

Classes compartilhadas têm efeito em vários lugares: mudar `.placeholder` afeta os sete espaços de foto; mudar `.section-head` afeta três seções. Um ajuste exclusivo de projeto deve usar um seletor como `.project .placeholder`.

### Inserir fotografias futuramente

A pasta sugerida é `dist/imagens/`, a criar quando houver fotos. Os caminhos partem de `dist/index.html`: use `imagens/nome-do-arquivo.jpg`, não `dist/imagens/nome-do-arquivo.jpg`.

Ao substituir um bloco reservado por `<img>`, será necessário definir o estilo da imagem: as regras atuais de `.placeholder` foram feitas para contêineres de ícone e texto. Exemplo didático para **uma foto de projeto**, ainda não implementado:

```html
<!-- Substituir o div.placeholder do projeto por esta imagem.
     O arquivo e a descrição devem corresponder à foto real. -->
<img class="project-photo" src="imagens/foto-do-projeto.jpg"
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

Crie um ID único e use o mesmo valor no link, como `href="#nova-secao"` e `id="nova-secao"`. Ajuste a numeração editorial das seções quando necessário. No caso de apoio, use o fragmento como referência e adapte as classes ao site antes de integrar.

## 11. Verificação após futuras alterações

1. Abra a página no navegador e confira leitura, acentos e ordem das seções.
2. Teste os quatro links do menu, o botão da trajetória, a marca e o retorno ao início.
3. Confira telas amplas e estreitas, incluindo proximidades de 850 e 600 px; procure cortes e rolagem horizontal indesejada.
4. Use Tab para percorrer os links e confirme o foco visível.
5. Se houver novas fotos, confira caminhos, enquadramento e textos alternativos.
6. Se editar a proposta de apoio, verifique também o limite de 540 px e os controles expansíveis.

Não há suíte de testes ou etapa de compilação exigida para a página estática. Este manual documenta o código existente; a lista acima orienta a validação quando o site for alterado.

## 12. Estado de publicação

Segundo o `LEIA-ME.md`, a última publicação registrada no pacote é a versão 1, privada. Este manual não verifica o estado atual da hospedagem. Editar ou salvar arquivos locais não publica mudanças.

Preserve `.openai/hosting.json` ao continuar pela hospedagem Sites. Uma publicação futura exige confirmar destino e audiência. A proposta de apoio não deve ser descrita como um sistema de doações pronto.
