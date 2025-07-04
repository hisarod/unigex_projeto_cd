# 📄 Documentação de Análise Estatística Descritiva

## 📌 Objetivo
Realizar análise descritiva completa dos datasets para entender distribuições, tendências centrais e dispersões dos dados. Para verificar o código trabalhado [clique aqui!](https://github.com/capacitabrasil/e4-6-18-unigex-cr-projeto03/blob/main/data%20science/heloisa/estatistica_descritiva.ipynb)

---

## 🗂️ Bases Analisadas
1. `df_unidades` — Dados das unidades/lojas.
2. `df_vendas` — Registro de vendas transacionais.
3. `df_categorias` — Cadastro de categorias dos produtos.
4. `df_produtos` — Cadastro de produtos.

---

## 🔢 Métricas Calculadas

### Medidas de Tendência Central
- Média aritmética
- Mediana (percentil 50%)
- Moda (valor mais frequente)

### Medidas de Dispersão
- Desvio padrão
- Variância
- Amplitude (máximo - mínimo)
- Intervalo interquartil (Q3 - Q1)

## 📋 Resultados por Dataframe

### 🔹 Dataframe `df_vendas`
**Variáveis numéricas**:
| Métrica       | valor_venda (R$) | quantidade |
|---------------|------------------|------------|
| Média         | 210,34           | 5,46       |
| Mediana       | 80,00            | 2,00       |
| Moda          | 50,00            | 1,00       |
| Desvio Padrão | 570,41           | 19,76      |
| Variância     | 325.365,96       | 390,26     |
| Mínimo        | -2.415,00        | -59,00     |
| Máximo        | 22.100,00        | 600,00     |
| Amplitude     | 24.515,00        | 659,00     |

🧠 **Insights**:
- Alta variabilidade nos valores de venda (CV = 271%)
- Distribuição assimétrica positiva
- 5% dos valores representam 48% do faturamento total

### 🔹 Dataframe `df_produtos`
**Variáveis numéricas**:
| Métrica       | preco_venda (R$) |
|---------------|------------------|
| Média         | 219,25           |
| Mediana       | 70,00            |
| Moda          | 49,99            |
| Desvio Padrão | 442,91           |
| Variância     | 196.170,09       |
| Mínimo        | 0,15             |
| Máximo        | 4.485,82         |
| Amplitude     | 4.485,67         |

🧠 **Insights**:
- Grande dispersão de preços (CV = 202%)
- 75% dos produtos custam menos de R$ 218,35
- Presença de outliers superiores (produtos premium)

### 🔹 Variáveis Categóricas
**Contagens principais**:
| Dataset       | Variável      | Valores Únicos | Valor Mais Frequente |
|---------------|---------------|----------------|-----------------------|
| df_categorias | descricao     | 50             | ACESSORIO (1x)        |
| df_unidades   | nome_fantasia | 3              | L01 - FORTALEZA (1x)  |
| df_produtos   | unidade       | 5              | un (9.102x)           |

🧠 **Insights**:
- Dominância absoluta de vendas por unidade ('un')
- Distribuição uniforme de categorias
- Unidades com distribuição equilibrada

## 📊 Tabelas Resumo

### Estatísticas Consolidadas
| Dataset       | Registros | Variável Analisada | Média   | Mediana | Desvio Padrão |
|---------------|----------|--------------------|---------|---------|---------------|
| df_vendas     | 10.418   | valor_venda        | 210,34  | 80,00   | 570,41        |
| df_produtos   | 9.112    | preco_venda        | 219,25  | 70,00   | 442,91        |
| df_categorias | 50       | id_categoria       | 260,70  | 369,50  | 173,56        |

## 📌 Conclusão

✔️ **Padrões identificados**:
   - Distribuições assimétricas em valores monetários
   - Alta concentração em poucas transações/produtos
   - Dominância categórica esperada ('un' para unidades)

✔️ **Dados Complementares**:
- Todos os datasets apresentam integridade preservada
- Sem valores faltantes críticos
- Relacionamentos entre tabelas estão íntegros


##  

👨‍💻 A análise estatística descritiva realizada identificou padrões consistentes nos dados, com distribuições assimétricas e alta variabilidade nos valores monetários, especialmente em vendas e preços de produtos. As medidas de tendência central e dispersão calculadas confirmam comportamentos esperados para esse tipo de operação comercial, como a concentração de valor em poucas transações e a predominância de vendas por unidade. Os outliers detectados representam casos válidos, como vendas corporativas e produtos premium. Os resultados demonstram a qualidade e integridade dos dados, que refletem adequadamente a realidade do negócio.
