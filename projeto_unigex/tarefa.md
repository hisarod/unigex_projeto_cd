# 📊 Análise Consolidada de Distribuição e Outliers

---

## 🗂️ DataFrames Analisados

- `df_categorias.z`
- `df_vendas.z`
- `df_produtos.z`
- `df_unidades.z`

##

##  🎯 Objetivo

Realizar a análise exploratória dos Dataframe, avaliando a distribuição das variáveis, 
identificando e tratando outliers, garantindo a integridade e a qualidade dos dados para etapas posteriores de modelagem, 
visualização e tomada de decisão.

##

## 🔍 Análise — DataFrame `df_categorias.z`

### 📓 Descrição

Avaliar a distribuição das variáveis categóricas booleanas e identificar possíveis outliers.

### 📊 Análise de Distribuição

- Todas as variáveis são booleanas (0 ou 1).
- Foi utilizada a frequência de valores `True` por coluna como métrica principal.
- Boxplots não são aplicáveis para dados binários, portanto foram utilizados histogramas de frequência.

### 🔥 Observações

- A maioria das colunas apresenta frequência de `True` menor que 10%.
- Não há caudas longas, assimetrias ou formatos anormais.
- Nenhuma coluna com predominância extrema de `True` (>90%).

### 🚨 Outliers

- Método aplicado: **Z-Score** sobre a frequência de `True`.
- Critério: Z > 2 ou Z < -2.
- **Resultado:** Nenhum outlier estatístico identificado.

### ✅ Decisão

- Todas as colunas foram **mantidas**, pois os dados estão coerentes com o perfil do dataframe.

### 📄 Justificativa

- Frequências consistentes.
- Ausência de valores extremos.
- Distribuição esperada para dados booleanos e esparsos.

### 🖼️ Gráficos Gerados

<sub>⚠️ Todos os gráficos são clicáveis e, ao clicar, você será direcionado para os respectivos códigos utilizados na geração de cada análise.</sub>


> [![Gráfico de Frequência das Categorias](https://github.com/user-attachments/assets/9fb5a432-5618-4ab8-abd6-bb871a34a4ff)](https://github.com/capacitabrasil/e4-6-18-unigex-cr-projeto03/blob/main/data%20science/tailany/analise_categorias.ipynb)

---

## 🔍 Análise — DataFrame `df_vendas.z`

### 📓 Descrição

Avaliar distribuições numéricas, identificar outliers e definir ações de tratamento.

### 📊 Variáveis Analisadas

- `quantidade`
- `total`
- `custo_medio`
- `valor_desconto`
- `media_movel_3meses`

### 🔥 Distribuição e Outliers

| Variável              | Distribuição                          | Outliers                     | Decisão / Tratamento                                                     |
|-----------------------|----------------------------------------|-------------------------------|--------------------------------------------------------------------------|
| **quantidade**        | Assimetria à direita                 | Acima de ~60 unidades         | **Mantido** (vendas por atacado)                                        |
| **total**             | Assimetria à direita                 | Acima de ~5000                | **Mantido**, categorizado (`MEGA_VENDA`, `GRANDE_VENDA`, `NORMAL`)     |
| **custo_medio**       | Multimodal, extremos e negativos     | Negativos e acima de ~2000    | **Clipagem inferior = 0 + Flag para revisão se >500**                   |
| **valor_desconto**    | Cauda longa à direita                | Acima de ~1000 e > total      | **Limite aplicado:** máx. 50% do total da venda                         |
| **media_movel_3meses**| Sazonal, picos                       | Acima de ~30                  | **Suavização com janela móvel + clipagem inferior = 0**                 |

### ⚙️ Métodos Aplicados

- **IQR (Intervalo Interquartil)**
- **Z-Score** (|Z| > 3)

### 🖥️ Impactos Observados

- Sem tratamento, a média e o desvio padrão são distorcidos fortemente, especialmente em `total`, `custo_medio` e `valor_desconto`.

### 🧠 Justificativas

- **Manutenção de outliers legítimos:** vendas grandes, descontos pontuais, sazonalidade.
- **Correção de erros operacionais:** custo negativo, desconto maior que a venda.

### 🖼️ Gráficos Gerados

<sub>⚠️ Todos os gráficos são clicáveis e, ao clicar, você será direcionado para os respectivos códigos utilizados na geração de cada análise.</sub>

> [![valor_desconto_comparativo](https://github.com/user-attachments/assets/037c5614-e076-4433-b5b8-b1c079abfda4)](https://github.com/capacitabrasil/e4-6-18-unigex-cr-projeto03/blob/main/data%20science/tailany/analise_vendas.ipynb)
> [![total_comparativo](https://github.com/user-attachments/assets/13001f6e-2421-44dc-ab9c-b26e382de8d9)](https://github.com/capacitabrasil/e4-6-18-unigex-cr-projeto03/blob/main/data%20science/tailany/analise_vendas.ipynb)
> [![custo_medio_comparativo](https://github.com/user-attachments/assets/b8f2532e-687f-4022-bca8-3649b856ce6f)](https://github.com/capacitabrasil/e4-6-18-unigex-cr-projeto03/blob/main/data%20science/tailany/analise_vendas.ipynb)
> [![media_movel_3meses_comparativo](https://github.com/user-attachments/assets/77aa7bf2-a2e4-4bd3-bc45-30200d7e5a7e)](https://github.com/capacitabrasil/e4-6-18-unigex-cr-projeto03/blob/main/data%20science/tailany/analise_vendas.ipynb)

---

## 🔍 Análise — DataFrame `df_produtos.z`

### 📓 Descrição

Avaliar a distribuição de preços, identificar outliers e definir ações de tratamento.

### 📊 Variável Analisada

- `preco_venda`

### 🔥 Distribuição

- Alta assimetria à direita.
- Cauda longa com valores extremos.

### 🚨 Outliers

- **Método:** Z-Score (média + 3 * desvio padrão).
- **Limite superior:** ~4500.26.
- Registros com `preco_venda` acima desse valor foram classificados como outliers.

### 🖥️ Impacto

|                          | Original | Sem Outliers |
|--------------------------|----------|--------------|
| **Registros**            | 9199     | 9112         |
| **Média (preco_venda)**  | 317.00   | 219.25       |
| **Desvio Padrão**        | 1394.42  | 442.91       |

- Outliers aumentavam a média em +97,75 e o desvio padrão em +951,51%.

### ✅ Decisão

- **Remoção dos outliers de preco_venda.**
- **Manutenção de código_categoria**, pois a baixa frequência de alguns códigos reflete granularidade, não erro.

### 🖼️ Gráficos Gerados

<sub>⚠️ Todos os gráficos são clicáveis e, ao clicar, você será direcionado para os respectivos códigos utilizados na geração de cada análise.</sub>

> [![produtos_distribuicao_preco_venda](https://github.com/user-attachments/assets/80858bb7-950d-47d7-91ec-84541e8e7e34)](https://github.com/capacitabrasil/e4-6-18-unigex-cr-projeto03/blob/main/data%20science/tailany/analise_produtos.ipynb)

---

## 🔍 Análise — DataFrame `df_unidades.z`

### 📓 Descrição

Validar consistência e possíveis outliers no cadastro de unidades.

### 📊 Distribuição

- **Variáveis categóricas:**
  - `unidade_nome`, `nome_fantasia` e `status_completo` têm distribuição **100% uniforme e consistente**.

- **Variáveis numéricas:**
  - `id` apresenta sequência correta (10001 a 10003), sem dispersão anormal.

### 🚨 Outliers

- **Nenhum outlier identificado.**
- Nomes seguem padrão `l<dígitos> - <cidade>`.

### ✅ Decisão

- Dados mantidos sem alteração.
- Padronização aplicada no `status` (de "sim" para "ativo") e inclusão de `nome_fantasia`.

### 🖼️ Gráficos Gerados

<sub>⚠️ Todos os gráficos são clicáveis e, ao clicar, você será direcionado para os respectivos códigos utilizados na geração de cada análise.</sub>

> [![grafico_unidades](https://github.com/user-attachments/assets/4bfb2832-10ed-44ec-b880-1ffbe86b52a1)](https://github.com/capacitabrasil/e4-6-18-unigex-cr-projeto03/blob/main/data%20science/tailany/analise_unidades.ipynb)

---

## 🏁 Resumo Geral

| Dataset         | Outliers? | Ações Realizadas                                     |
|-----------------|------------|------------------------------------------------------|
| **df_categorias.z** | ❌        | Nenhuma. Frequência dentro do esperado.              |
| **df_vendas.z**     | ✅        | Correções pontuais (`custo_medio`, `valor_desconto`). Categorização (`total`). Suavização (`media_movel_3meses`). |
| **df_produtos.z**   | ✅        | **Remoção de outliers em `preco_venda`.**           |
| **df_unidades.z**   | ❌        | Nenhuma. Dados íntegros e consistentes.              |

---

## 🚀 Conclusão

A análise dos dataframes foi conduzida de forma criteriosa, aplicando métodos estatísticos robustos (Z-Score, IQR e análise de distribuição)
para identificação e tratamento de outliers. As decisões foram tomadas com base na coerência estatística e no alinhamento com a lógica 
de negócio, preservando informações relevantes e corrigindo inconsistências críticas, como custos negativos e descontos operacionais 
inválidos.

O resultado final é um conjunto de dados consistente, confiável e preparado para suportar análises avançadas, desenvolvimento de modelos preditivos e geração de insights estratégicos. A documentação detalhada dos critérios aplicados, bem como os registros visuais gerados, asseguram rastreabilidade, transparência e reprodutibilidade do processo de higienização e validação dos dados.
