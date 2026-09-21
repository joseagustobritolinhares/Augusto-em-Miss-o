# José Augusto em Missão — continuação local

Este pacote permite continuar o portfólio no seu computador e no VS Code com o Codex.

## Comece aqui

1. Extraia todo o ZIP na pasta que você criou no computador. Não trabalhe diretamente dentro do ZIP.
2. No VS Code, use **Arquivo > Abrir Pasta** e escolha a pasta que contém este LEIA-ME.md e o arquivo AGENTS.md.
3. Para visualizar o site, abra `dist/index.html` no navegador. Pode dar dois cliques no arquivo pelo Explorador de Arquivos.
4. Para ver a proposta de patrocinadores e divulgação, abra `previas/apoio.html` no navegador.
5. No chat do Codex dentro do VS Code, cole o texto do arquivo `CONTINUAR-NO-CODEX.txt`.

O projeto é HTML e CSS estático. Não é necessário instalar Node.js, npm ou dependências para abrir ou editar a versão atual. Após salvar alterações, atualize a página no navegador.

## Arquivos

Para entender o desenho da página, as classes CSS, a navegação e como editar o projeto, consulte o [Manual do projeto](MANUAL-DO-PROJETO.md), com esboços para computador e celular.

- `dist/index.html`: código completo da versão publicada, com conteúdo, estilos, navegação e ícone do site no mesmo arquivo.
- `previas/apoio.html`: prévia independente da seção de apoio, pronta para abrir no navegador.
- `previas/apoio-fragmento.html`: fonte editável da prévia, útil como referência para integrar a seção ao site.
- `AGENTS.md`: contexto e orientações para o Codex continuar o trabalho.
- `CONTINUAR-NO-CODEX.txt`: mensagem pronta para iniciar a continuação.
- `.openai/hosting.json`: identidade do Site existente e indicação da pasta pública `dist`.
- `.gitignore`: exclusões para um eventual repositório Git local.

## O que já está feito

Portfólio responsivo em português, em azul profundo e dourado, contendo apresentação de José Augusto, trajetória, objetivos futuros e sete espaços reservados para fotos.

Projetos incluídos: Um Ano em Missão em Urucará (2025), Escola de Imersão Transcultural no Instituto de Missões Noroeste (2026) e campanhas de colportagem (2025–2026).

## O que está somente na prévia

A seção “Faça parte desta missão” e as opções de divulgação ainda NÃO foram integradas à versão publicada. Na prévia, os controles apenas mostram explicações. Não enviam mensagens, não copiam links, não recebem doações e não baixam uma arte final.

Local proposto: depois de “Próximos passos” e antes de “Memórias da missão”.

Falta definir o WhatsApp de contato, dados de contribuição, fotos e arte final de divulgação. Não existem esses dados no pacote. O destino missionário internacional também não foi confirmado.

## Site existente e publicação

Endereço existente: https://jose-augusto-em-missao.joseaugustobritolinh.chatgpt.site

Última publicação confirmada nesta conversa: versão 1, privada. Revisão de origem: 5c7a659b7690d66ad7c98f123526bcc4897af1c3.

A transferência deste pacote NÃO modifica a página hospedada e NÃO sincroniza automaticamente suas alterações locais. O histórico Git e as credenciais da hospedagem não foram incluídos.

Para atualizar o mesmo endereço no futuro, será necessário usar Sites com acesso ao Site existente e à sua publicação. O arquivo `.openai/hosting.json` identifica esse Site; não é uma credencial. Se Sites não estiver disponível no Codex local, continue a edição local e escolha depois como publicar. Não crie automaticamente outro Site nem altere a privacidade.

## Fotos

Os espaços para imagens são intencionais: nenhuma fotografia pessoal foi incorporada. Quando for adicionar as suas, uma organização simples é criar `dist/imagens/` e referenciá-las no HTML com caminhos relativos, como `imagens/retrato.jpg`.

## Cópias e histórico

O ZIP é uma cópia de transferência. Você pode iniciar um repositório Git próprio na pasta local para registrar alterações. Não há repositório remoto pessoal configurado neste pacote.
