# Trade Manual: Wiki Lint

Use este manual para auditar saude, consistencia e navegabilidade da Wiki.

## Objetivo

Encontrar problemas que impedem a memoria de acumular:

- Contradicoes semanticas entre notas antigas e novas.
- Wikilinks quebrados.
- Paginas grandes demais.
- Paginas orfas.
- Fontes ausentes.
- Duplicacao conceitual.

## Regras de wikilink

- Todo link semantico deve usar `[[nome-da-pagina]]`.
- Um wikilink e valido quando existe `wiki/nome-da-pagina.md` ou pagina com titulo equivalente.
- Links para projetos podem apontar para `wiki/projetos/<nome>/overview.md`.
- Links quebrados devem ser reportados, nao corrigidos silenciosamente.

## Contradicoes semanticas

Procure conflitos como:

- Uma nota diz que uma tecnologia foi escolhida; outra diz que foi abandonada.
- Uma decisao antiga contradiz o estado atual sem registro.
- Uma pendencia aparece concluida em sessao, mas segue aberta.
- Duas paginas descrevem a mesma entidade com nomes diferentes.

## Tamanho de paginas

- Acima de 220 linhas: sugerir fatiamento.
- Acima de 350 linhas: marcar como alta prioridade.
