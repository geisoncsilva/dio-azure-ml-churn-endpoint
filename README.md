# Previsao de Churn em Telecom — Entrega DIO

Repositorio criado para a entrega pratica do laboratorio **Trabalhando com Machine Learning na Pratica no Azure ML** na DIO, estruturando o racional de modelagem, o contrato de inferencia em `endpoints.json` e o fluxo de publicacao via Git e VS Code.

## 1. Contexto e objetivo de negocio
- **Cenario:** Empresa ficticia de assinatura de banda larga e TV que busca antecipar o cancelamento (`churn`) de clientes.
- **Variavel alvo (`churn`):** `0` para cliente retido e `1` para cliente com risco de cancelamento no proximo ciclo.
- **Metrica principal:** `AUC_weighted`, escolhida por avaliar o poder de discriminacao entre as classes mesmo quando ha desbalanceamento entre clientes ativos e cancelamentos.

## 2. Variaveis ficticias do conjunto de dados
- `meses_contrato` (numerico): tempo de permanencia do cliente.
- `valor_mensal_brl` (numerico): valor mensal cobrado no plano.
- `uso_dados_gb` (numerico): consumo medio mensal de dados.
- `chamados_suporte_90d` (numerico): quantidade de chamados abertos nos ultimos 90 dias.
- `tipo_contrato` (categorico): modalidade vigente (`Mensal` ou `Anual`).

## 3. Racional do modelo e configuracao do endpoint
- **Abordagem:** Classificacao binaria avaliada no contexto de **Automated ML** no Azure Machine Learning, priorizando o modelo com maior `AUC_weighted` na validacao.
- **Ponto de extremidade (`endpoints.json`):** Documenta um *managed online endpoint* (`churn-telecom-online-endpoint`, implantacao `blue-v1`) com autenticacao por chave (`key`), `scoring_uri` de exemplo e exemplos de `sample_request` e `sample_response`.

## 4. Passo a passo de organizacao e envio no GitHub
1. Criei o repositorio no GitHub e abri o projeto localmente no **VS Code**.
2. Estruturei os arquivos `README.md` e `endpoints.json` com o racional do problema, variaveis e payload de previsao.
3. Versionei e enviei os arquivos para a branch `main` usando **Git** no terminal do VS Code (`git init`, `git add`, `git commit`, `git remote add origin` e `git push`).
4. Registrei o link do repositorio na etapa de entrega do projeto na DIO.

## 5. Arquivos entregues
- `README.md`: documentacao do processo, criterios de modelagem e passos de entrega.
- `endpoints.json`: definicao do ponto de extremidade e exemplos de requisicao/resposta.