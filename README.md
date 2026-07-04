# Cerebro Layout: PersonalOS / Second Brain

Um layout aberto para criar um PersonalOS / Second Brain em Markdown puro, baseado em LLM Wiki, contrato de 3 camadas e skills de comportamento.

Este repositorio nao e um app. Nao tem Node, nao tem scripts, nao tem servidor e nao tem runtime. A proposta e mais simples e mais forte: uma estrutura de contexto para agentes de IA trabalharem sobre a sua memoria.

## A ideia central

A maioria dos second brains falha porque exige que o humano faca manutencao manual: classificar, resumir, cruzar links, atualizar notas antigas e lembrar contradicoes. A abordagem LLM Wiki muda essa responsabilidade.

O humano captura material bruto. O agente compila conhecimento. O Git preserva historia. As skills preservam comportamento.

Em vez de colocar tudo em um banco vetorial e esperar que a busca resolva, este modelo incentiva memoria escrita, pequena, linkada e revisavel.

## Inspiracao

Este layout foi inspirado por:

- Andrej Karpathy e a ideia de Wikis mantidas por LLMs.
- Aakash Gupta e o contrato de camadas para Second Brain agentico.
- Fabio Akita e a ideia pragmatica de memoria operacional no terminal.

Referencia principal: https://www.aibyaakash.com/p/karpathy-second-brain

## O que este projeto e

- Um contrato de trabalho para agentes.
- Um layout de pastas para memoria pessoal.
- Um conjunto de skills em Markdown.
- Um template publico para qualquer pessoa adaptar.

## O que este projeto nao e

- Nao e um app.
- Nao e um CLI.
- Nao e um RAG pronto.
- Nao e uma ferramenta de anotacao.
- Nao depende de JavaScript, Python, banco de dados ou servidor.

## Contrato de 3 Camadas

### 1. Raw

`raw/` e a caixa de entrada.

Coloque aqui:

- artigos
- clippings
- transcricoes
- logs
- rascunhos
- ideias soltas
- notas de reuniao

Regra: o humano captura; o agente compila.

### 2. Wiki

`wiki/` e memoria compilada.

O agente cria e mantem:

- paginas de conceito
- paginas de projeto
- decisoes tecnicas
- problemas resolvidos
- links semanticos
- indice global
- log historico

Regra: a Wiki nao e um deposito bruto. Ela e conhecimento processado.

### 3. Cortex

`.cortex/skills/` contem os manuais de comportamento.

Exemplos:

- `dba.md`: como agir como DBA Senior.
- `refactor.md`: como conduzir refatoracao segura.
- `lint.md`: como auditar saude semantica da Wiki.

Regra: comportamento do agente tambem e conhecimento versionado.

## Estrutura

```text
cerebro/
|-- CLAUDE.md
|-- .cortex/
|   `-- skills/
|       |-- dba.md
|       |-- refactor.md
|       `-- lint.md
|-- raw/
|   |-- clippings/
|   `-- scratchpad/
`-- wiki/
    |-- index.md
    |-- log.md
    |-- perfil/
    |   `-- identidade.md
    `-- projetos/
        `-- .gitkeep
```

## Como usar

1. Copie a pasta `template/` para um repositorio privado.
2. Personalize `CLAUDE.md`.
3. Ajuste `wiki/perfil/identidade.md`.
4. Adicione ou edite skills em `.cortex/skills/`.
5. Coloque fontes brutas em `raw/`.
6. Peca ao agente para capturar, sintetizar, linkar ou auditar usando o contrato.

## Fluxos recomendados

### Captura

Peca ao agente:

> Leia `raw/clippings/arquivo.md`, extraia conhecimento duravel, crie paginas pequenas em `wiki/`, atualize `wiki/index.md` e registre em `wiki/log.md`.

### Briefing

Peca ao agente:

> Me de um briefing do projeto atual lendo apenas `overview.md`, `pendencias.md` e a ultima sessao.

### Lint semantico

Peca ao agente:

> Use `.cortex/skills/lint.md` para encontrar links quebrados, contradicoes e paginas grandes demais.

### Sync de fim de dia

Peca ao agente:

> Consolide a sessao de hoje, registre licoes aprendidas, atualize pendencias e sugira um commit.

## Principios

- Markdown puro.
- Skills antes de scripts.
- Uma fonte por vez.
- Contexto cirurgico.
- Wikilinks explicitos.
- Git como trilha historica.
- Contradicoes sao registradas, nao apagadas.
- Automacao, se existir, deve ser externa e opcional.

## Privacidade

Este repositorio publico deve conter apenas o layout. Sua Wiki real, fontes privadas, logs de trabalho e projetos pessoais devem ficar em um repositorio privado.

## Licenca

MIT.
