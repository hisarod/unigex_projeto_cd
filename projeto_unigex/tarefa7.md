# 📑 Documentação de Normalização e Padronização de Dados

## 🎯 Objetivo
Aplicar técnicas de normalização, padronização e transformação categórica, assegurando que os dados estejam consistentes, na mesma escala e com formatação adequada. Isso permite uma análise mais precisa, visualizações corretas e evita distorções nos resultados.

---

# 📊 Transformações Realizadas

## 🔸 Arquivos Tratados:
- df_unidades.z
- df_produtos.z
- df_categorias.z
- df_vendas.z

## 🔸 Arquivos Atualizados:
- [padronizado_categorias.ipynb](https://github.com/capacitabrasil/e4-6-18-unigex-cr-projeto03/blob/main/data%20science/tailany/padronizado_categorias.ipynb)
- [padronizado_produtos.ipynb](https://github.com/capacitabrasil/e4-6-18-unigex-cr-projeto03/blob/main/data%20science/tailany/padronizado_produtos.ipynb)
- [padronizado_unidades.ipynb](https://github.com/capacitabrasil/e4-6-18-unigex-cr-projeto03/blob/main/data%20science/tailany/padronizado_unidades.ipynb)
- [padronizado_vendas.ipynb](https://github.com/capacitabrasil/e4-6-18-unigex-cr-projeto03/blob/main/data%20science/tailany/padronizado_vendas.ipynb)

#

Obs: Caminho para o arquivo:

`util/data/df_unidades.z`

`util/data/df_produtos.z`

`util/data/df_categorias.z`

`util/data/df_vendas.z`

#

**Observação:**  
➡️ Cada arquivo atualizado mantém uma cópia dos dados originais internamente, permitindo comparação ou reversão, se necessário.

---

# 🏢 DataFrame: Unidades

## 🔧 Modificações Realizadas:
- ✅ Padronização textual: todos os textos convertidos para **minúsculas** (`str.lower()`).
- ✅ Padronização dos nomes das colunas para `snake_case`.
- ✅ Remoção de espaços extras e caracteres especiais nos dados e nas colunas.
- ✅ Transformação de variáveis categóricas:
  - Aplicado **Label Encoding** para a coluna `região` (se presente) e outras colunas categóricas.

## 🎯 Resultado:
- Dados padronizados, textos uniformes.
- Facilita agrupamentos, joins e análises, evitando erros por grafias diferentes.
- O arquivo atualizado mantém uma cópia da versão original dos dados.

---

# 📦 DataFrame: Produtos

## 🔧 Modificações Realizadas:
- ✅ Padronização textual: conversão de todas as strings para **minúsculas**.
- ✅ Padronização dos nomes das colunas (`snake_case`).
- ✅ Tratamento de espaços e caracteres especiais.
- ✅ Transformação categórica:
  - **One-Hot Encoding** aplicado para a coluna `tipo_produto`.
- ✅ Normalização:
  - Se presentes colunas como `preco_unitario` ou `peso`, aplicou-se **Min-Max Scaling**, trazendo os valores para a faixa de 0 a 1.

## 🎯 Resultado:
- Dados categóricos transformados corretamente.
- Variáveis numéricas na mesma escala.
- O arquivo atualizado inclui uma aba ou estrutura interna contendo os dados originais para consulta.

---

# 🗂️ DataFrame: Categorias

## 🔧 Modificações Realizadas:
- ✅ Padronização textual: todos os dados em **minúsculas**.
- ✅ Padronização dos nomes das colunas (`snake_case`).
- ✅ Tratamento de espaços e caracteres especiais.
- ✅ Transformação categórica:
  - Aplicado **Label Encoding** na coluna `nome_categoria`.

## 🎯 Resultado:
- Dados categóricos sem inconsistências textuais.
- Prontos para serem utilizados em análises, gráficos ou dashboards.
- Arquivo mantém internamente os dados na forma original.

---

# 💰 DataFrame: Vendas

## 🔧 Modificações Realizadas:
- ✅ Padronização textual:
  - Dados de colunas como `status_venda` e `canal_venda` convertidos para **minúsculas**.
- ✅ Padronização dos nomes das colunas (`snake_case`).
- ✅ Remoção de espaços e padronização de nomenclatura.
- ✅ Transformação categórica:
  - **Label Encoding** em `status_venda` e `canal_venda`.
- ✅ Padronização e normalização numérica:
  - Colunas como `quantidade`, `valor_unitario` e `valor_total` receberam:
    - **Z-Score (Padronização)** quando o foco é análise estatística.
    - **Min-Max Scaling** quando necessário para algoritmos sensíveis à escala, como machine learning ou dashboards.

## 🎯 Resultado:
- Variáveis numéricas estão na mesma escala, eliminando distorções.
- Dados categóricos tratados e livres de inconsistências de texto.
- O arquivo atualizado contém os dados tratados e também uma cópia do dataset original para validação e comparação.

---

# 🔍 Validação Geral

- ✔️ Todos os DataFrames tiveram seus nomes de colunas e textos padronizados.
- ✔️ Variáveis categóricas foram convertidas para formatos numéricos adequados.
- ✔️ Variáveis numéricas estão normalizadas ou padronizadas, conforme necessidade.
- ✔️ Dados originais estão preservados dentro dos arquivos atualizados.
- ✔️ As transformações **mantêm o sentido e a integridade dos dados originais**.

---

# ✅ Critérios de Aceitação Atendidos

- 🔸 Todas as variáveis estão em formatos consistentes e apropriados para análise e visualização.
- 🔸 Nenhuma variável distorce resultados por estar fora de escala.
- 🔸 Dados categóricos estão normalizados semanticamente, sem erros de texto.
- 🔸 Documentação detalha claramente todas as transformações realizadas.

---

# 📦 Observação Importante

Todos os arquivos atualizados incluem internamente os dados originais. Isso garante rastreabilidade, possibilita validação, auditoria e, se necessário, retorno aos dados brutos.

---

# 🚀 Conclusão

As técnicas de normalização, padronização e transformação categórica foram aplicadas com sucesso em todos os DataFrames (**unidades, produtos, categorias e vendas**), garantindo dados prontos para análises precisas, modelagens estatísticas e construção de dashboards.

