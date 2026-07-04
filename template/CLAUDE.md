# Cerebro: PersonalOS / Second Brain

Este repositorio e um Second Brain em Markdown puro. Ele nao e um app, nao tem motor Node e nao depende de scripts locais. O comportamento do sistema vive em contratos e skills.

## Base teorica

O modelo combina tres ideias:

1. LLM Wiki: a memoria deve ser compilada em paginas claras, pequenas e linkadas, em vez de depender de busca vetorial para tudo.
2. Contrato de 3 Camadas: `raw/` e entrada, `wiki/` e memoria compilada, `.cortex/skills/` e comportamento especializado.
3. Memoria operacional: o agente deve manter continuidade entre sessoes usando arquivos simples, Git e disciplina de contexto.

## Principio central

A pasta `wiki/` nao e um caderno manual comum. Ela e memoria compilada por agente. O humano captura fontes e valida direcao. O agente organiza, linka, resume, cruza contradicoes e mantem o indice.

## Camada 1: Raw

`raw/` e a caixa de entrada imutavel. Ela suporta conhecimento geral e insumos especificos de projetos.

Estrutura recomendada:

- `raw/inbox/`: entrada rapida ainda sem destino claro.
- `raw/clippings/`: conhecimento geral, artigos, referencias e trechos reaproveitaveis.
- `raw/scratchpad/`: rascunhos soltos, ideias incompletas e notas de pensamento.
- `raw/projetos/<nome-projeto>/`: material bruto especifico de um projeto.

Exemplos por projeto:

- `raw/projetos/website-profissional/referencias/`
- `raw/projetos/website-profissional/copy/`
- `raw/projetos/website-profissional/prints/`
- `raw/projetos/website-profissional/notas/`

Regras:

- Nao reescrever arquivos em `raw/`.
- Nao tentar organizar demais a entrada.
- Processar uma fonte por vez sempre que possivel.
- Se uma fonte for grande, primeiro criar uma nota de triagem.
- Quando o material tiver projeto claro, colocar em `raw/projetos/<nome-projeto>/`.
- Quando o material for conhecimento geral, usar `raw/clippings/`.
- Quando nao houver destino claro, usar `raw/inbox/` e classificar depois.

## Camada 2: Wiki

`wiki/` e memoria compilada.

Use para:

- conceitos
- decisoes
- projetos
- perfil do usuario
- licoes aprendidas
- problemas resolvidos
- registros de sessao

Regras:

- A IA pode editar `wiki/` somente quando estiver executando uma tarefa clara de captura, sintese, revisao ou manutencao.
- Toda pagina derivada de uma fonte deve conter `## Fontes`.
- Toda nova pagina relevante deve ser linkada em `wiki/index.md`.
- Mudancas importantes devem ser registradas em `wiki/log.md`.
- Contradicoes nao devem ser apagadas silenciosamente; devem ser registradas e reconciliadas.

## Camada 3: Cortex

`.cortex/skills/` contem manuais operacionais.

Use para:

- definir papeis especializados
- padronizar revisoes
- guiar manutencao semantica
- preservar o modo de pensar do sistema

Regras:

- Antes de uma tarefa especializada, ler a skill correspondente.
- Se nenhuma skill existir, operar pelo contrato deste arquivo.
- Se uma skill conflitar com este contrato, este contrato vence.
- Skills devem ser pequenas, acionaveis e versionadas.

## Fluxos sem scripts

### Captura

Quando o usuario pedir para capturar uma fonte:

1. Ler o arquivo em `raw/`.
2. Extrair ideias duraveis, decisoes, nomes, conceitos e proximas acoes.
3. Criar ou atualizar paginas em `wiki/`.
4. Adicionar wikilinks em `wiki/index.md`.
5. Registrar em `wiki/log.md`.

### Briefing

Quando o usuario pedir contexto:

1. Se estiver trabalhando em um projeto, ler apenas `overview.md`, `pendencias.md` e a sessao mais recente daquele projeto.
2. Se for contexto global, ler `wiki/index.md`, `wiki/log.md` e `wiki/perfil/identidade.md`.
3. Nao carregar a Wiki inteira sem necessidade.
4. Responder com resumo curto, riscos, pendencias e proximo passo.

### Sync de fim de dia

Quando o usuario pedir sync:

1. Identificar projeto ativo.
2. Consolidar licoes aprendidas.
3. Atualizar pendencias.
4. Registrar decisoes e contexto em `wiki/log.md`.
5. Sugerir commit Git, mas nao executar push sem pedido explicito.

### Lint semantico

Quando o usuario pedir lint:

1. Ler `.cortex/skills/lint.md`.
2. Procurar wikilinks quebrados.
3. Procurar paginas grandes demais.
4. Procurar contradicoes entre notas.
5. Gerar relatorio em Markdown ou responder com achados acionaveis.

## Padroes de Markdown

- Titulo unico com `#`.
- Secoes curtas com `##`.
- Wikilinks em `[[nome-da-pagina]]`.
- Paginas pequenas e conectadas.
- Cada pagina compilada deve conter `## Fontes` quando derivar de material bruto.
- Acima de 220 linhas, sugerir fatiamento.

## SQL e engenharia

- Palavras-chave SQL em letras maiusculas.
- Antes de otimizar queries, checar indices e plano de execucao.
- Preferir decisoes tecnicas com evidencias.
- Registrar trade-offs quando mudarem a direcao de um projeto.

## Proibicoes

- Nao adicionar runtime, app, servidor ou scripts ao Cerebro sem decisao explicita.
- Nao transformar este repositorio em ferramenta Node, Python ou webapp por padrao.
- Nao commitar segredos, `.env`, tokens, dumps privados ou dados sensiveis.
- Nao apagar contexto historico sem registrar motivo.
- Nao carregar contexto maximo quando contexto cirurgico resolve.
