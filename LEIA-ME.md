# José Augusto em Missão — continuação local

Este pacote permite continuar o portfólio no seu computador e no VS Code com o Codex.

## Comece aqui

1. Extraia todo o ZIP na pasta que você criou no computador. Não trabalhe diretamente dentro do ZIP.
2. No VS Code, use **Arquivo > Abrir Pasta** e escolha a pasta que contém este LEIA-ME.md e o arquivo AGENTS.md.
3. Para visualizar o portfólio, abra `index.html` no navegador. Pode dar dois cliques no arquivo pelo Explorador de Arquivos.
4. Para visualizar a página de apoio, abra `apoio.html`. Os arquivos em `previas/` são referências históricas e não são a versão ativa.
5. No chat do Codex dentro do VS Code, cole o texto do arquivo `CONTINUAR-NO-CODEX.txt`.

O projeto é HTML e CSS estático. Não é necessário instalar Node.js, npm ou dependências para abrir ou editar a versão atual. Após salvar alterações, atualize a página no navegador.

## Arquivos

Para entender o desenho da página, as classes CSS, a navegação e como editar o projeto, consulte o [Manual do projeto](MANUAL-DO-PROJETO.md), com esboços para computador e celular.

- `index.html`: página principal do portfólio.
- `apoio.html`: página interna com as formas de apoio à missão.
- `style.css`: estilos compartilhados pelas duas páginas.
- `img/`: retrato e imagens dos projetos usados pelo site.
- `previas/apoio.html` e `previas/apoio-fragmento.html`: materiais anteriores, mantidos apenas como referência.
- `AGENTS.md`: contexto e orientações para o Codex continuar o trabalho.
- `CONTINUAR-NO-CODEX.txt`: mensagem pronta para iniciar a continuação.
- `.openai/hosting.json`: registro legado de uma hospedagem anterior; não é usado para publicar no GitHub.
- `.gitignore`: exclusões do repositório Git.

## O que já está feito

Portfólio responsivo em português, em azul profundo e dourado, contendo apresentação de José Augusto, trajetória, objetivos futuros, vídeo de apresentação pendente e três espaços reservados para registros fotográficos.

Projetos incluídos: Um Ano em Missão em Urucará (2025), Escola de Imersão Transcultural no Instituto de Missões Noroeste (2026) e campanhas de colportagem (2025–2026).

## Página de apoio: estado atual

“Faça parte desta missão” já está disponível em `apoio.html`. Há dois caminhos: contribuir pelo Pix ou pela plataforma de doação e acompanhar/orar/divulgar pelo grupo de WhatsApp. A página não confirma doações nem processa pagamentos diretamente.

Ainda faltam: vídeo de apresentação e, se desejado, fotos para a galeria. O destino missionário internacional também não foi confirmado.

## Repositório e publicação

O repositório remoto integrado é `https://github.com/joseagustobritolinhares/Augusto-em-Miss-o.git`, na ramificação `main`.

Enviar alterações para `main` atualiza o repositório. Caso o GitHub Pages esteja configurado para essa ramificação, a publicação segue a configuração do próprio repositório. Confirme a URL pública e a origem do Pages no GitHub antes de depender dela para divulgação.

O arquivo `.openai/hosting.json` pertence a uma hospedagem anterior e aponta para uma pasta `dist` que não faz parte desta cópia. Não o use para publicar esta versão sem reconfigurar a hospedagem.

O Git já está inicializado e o remoto já está configurado. Use `git status`, faça uma revisão e envie com `git push origin main` quando a publicação estiver autorizada.

## Fotos

O retrato e as imagens da trajetória já estão em `img/`. Os três espaços em “Memórias da missão” são intencionais. Quando for adicionar fotos, mantenha-as em `img/` ou `galeria/` e referencie-as com caminhos relativos, como `galeria/nome-da-foto.jpg`.

## Cópias e histórico

O projeto já é um repositório Git conectado ao GitHub. Revise alterações locais antes de fazer commits para não publicar conteúdo não confirmado.
