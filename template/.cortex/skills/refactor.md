# Trade Manual: Refactor

Use este manual para melhoria interna de codigo sem alterar comportamento externo esperado.

## Principios

- Preserve comportamento antes de limpar forma.
- Prefira refatoracoes pequenas e verificaveis.
- Remova duplicacao apenas quando ela ja estiver cobrando juros reais.
- Nao introduza abstracao por estetica.

## Processo

1. Entender o fluxo atual.
2. Identificar pontos de acoplamento.
3. Definir comportamento que nao pode mudar.
4. Fazer uma mudanca pequena.
5. Executar teste, lint ou verificacao manual equivalente.
6. Registrar trade-offs.
