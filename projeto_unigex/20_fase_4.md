# 📚 Avaliar os modelos otimizados com dados de teste

---

## 🎯 Objetivo  
Aplicar Grid Search para otimização dos modelos de regressão (Árvore de Decisão e Random Forest), visando melhorar a previsão da demanda de estoque.

---

## 🧪 Modelos e Parâmetros Otimizados  
- Árvore de Decisão  
- Random Forest  

Foi realizada validação cruzada (5 folds) para garantir robustez na escolha dos hiperparâmetros.

---

## 📊 Resultados Antes da Otimização  

| Modelo                | MAE  | RMSE | R²   |
|-----------------------|------|------|------|
| Regressão Linear      | 4.85 | 18.58| 0.15 |
| Árvore de Decisão     | 2.41 | 8.15 | 0.84 |
| Random Forest         | 2.27 | 8.91 | 0.81 |

### Gráfico de Desempenho Antes da Otimização

![antes](https://github.com/user-attachments/assets/bc78a4be-2ed2-4425-a7c6-3bfee41a7789)


---

## 📊 Resultados Após a Otimização  

| Modelo                | MAE  | RMSE | R²   |
|-----------------------|------|------|------|
| Árvore de Decisão     | 0.66 | 4.86 | 0.94 |
| Random Forest         | 0.57 | 4.20 | 0.96 |

### Gráfico de Desempenho Depois da Otimização

![comparacao_otimizados](https://github.com/user-attachments/assets/c43d5118-270e-467b-a899-f18d939a274d)

---

## 📈 Gráficos de Dispersão dos Modelos Otimizados

![dispersao_otimizados](https://github.com/user-attachments/assets/9f24fb8b-97a7-466c-bc61-d825a1bd2b9c)



## 🧠 Análise Comparativa  

- A otimização com Grid Search melhorou significativamente as métricas dos modelos.  
- O R² aumentou em mais de 10 pontos percentuais para ambos os modelos, mostrando maior capacidade preditiva.  
- O erro absoluto (MAE) e quadrático (RMSE) reduziram drasticamente.  
- Os gráficos de dispersão confirmam boa aderência entre valores previstos e reais, com pouca dispersão.  

---

## 💡 Conclusão  

- A otimização é fundamental para extrair o máximo desempenho dos modelos.  
- Apesar da Random Forest ter resultado ligeiramente superior, a Árvore de Decisão otimizada oferece um melhor equilíbrio entre precisão e interpretabilidade.  
- Recomenda-se a utilização da Árvore de Decisão otimizada para previsão de demanda de estoque, especialmente em contextos que demandem explicação clara das previsões.
- Para mais detalhe sobre a otimização dos modelos com Grid Search [clique aqui!](https://github.com/capacitabrasil/e4-6-18-unigex-cr-projeto03/blob/main/data%20science/tailany/19_fase_4.md)

---
