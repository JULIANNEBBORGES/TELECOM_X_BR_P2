# 📊 TELECOM_X_BR_P2 | Previsão de Evasão de Clientes (Churn)

## 📌 Descrição do Projeto

Este projeto compõe a **segunda etapa do desafio proposto pela Alura em parceria com a Oracle Next Education (ONE)**, na formação em **Data Science**. O objetivo é aplicar conhecimentos de estatística, regressão e machine learning em um cenário de negócios real, utilizando a abordagem de **Challenge Based Learning**.

A proposta consiste em analisar os dados da empresa fictícia **Telecom X**, identificar os principais fatores que levam à evasão de clientes (churn) e desenvolver um modelo preditivo capaz de antecipar quais clientes estão propensos a cancelar seus serviços.

## 🔗 Fontes de Dados

- 📦 [[Dados dos Clientes]](https://github.com/JULIANNEBBORGES/TELECOM_X_BR_P2/blob/main/df_cleaned.csv)
- 📘 [Dicionário de Dados](https://github.com/ingridcristh/challenge2-data-science/tree/main)

## 🔗 Desafio Anterior

Este projeto é a continuação do desafio anterior:

**📊 Análise de Evasão de Clientes (Churn) - Telecom X | Parte 1**  
🔗 [Repositório Parte 1](https://github.com/JULIANNEBBORGES/CHALLENGE_TELECOM_X_BR-)- 

## 🧠 Estrutura do Projeto

O notebook está dividido em etapas que refletem o fluxo completo de um projeto de ciência de dados:

1. **Preparação do Ambiente:** Importação de bibliotecas e configuração inicial.
2. **Extração dos Dados:** Leitura do arquivo df_cleaned.csv
3. **ETL - Desaninhamento e Limpeza:** Transformação dos dados aninhados em estrutura tabular.
4. **Verificação e Conversão de Tipos:** Ajuste de tipos, remoção de espaços e tratamento de valores nulos.
5. **Análise Exploratória (EDA):** Estatísticas descritivas, visualizações e correlações.
6. **Engenharia de Features:** Criação de variáveis como `HasMultipleServices`, `HasPremiumSecurity`, `HasStreaming`, `TotalExtraServices`.
7. **Pré-processamento:** Codificação de variáveis categóricas, balanceamento de classes e normalização.
8. **Modelagem Preditiva:** Treinamento com Regressão Logística, Árvore de Decisão e Floresta Aleatória.
9. **Avaliação de Modelos:** Métricas como Acurácia, Precisão, Recall, F1-score, Matriz de Confusão e ROC AUC.
10. **Interpretação com SHAP:** Análise do impacto das variáveis nas previsões.
11. **Relatório Estratégico:** Propostas de ações para retenção de clientes com base nos insights obtidos.

## 📊 Análise e Resultados

- A variável com maior impacto no churn foi **tenure**: clientes com pouco tempo de contrato tendem a evadir.
- Contratos do tipo **Month-to-month** e pagamentos via **Electronic Check** estão fortemente associados à evasão.
- A ausência de serviços como **OnlineSecurity** e **TechSupport** também contribui para o churn.
- O modelo com melhor desempenho foi a **Floresta Aleatória**, com:
  - **Acurácia:** 85%
  - **F1-score:** 0.85
  - **ROC AUC:** 0.87

## 🧭 Estratégias Recomendadas

Com base nos insights, foram propostas ações para redução da evasão:

- 🎁 Programa de fidelização para novos clientes
- 🔐 Promoção de serviços premium (segurança e suporte)
- 📄 Incentivo à migração para contratos anuais
- 📞 Intervenção proativa com clientes em risco
- 💳 Campanha de educação financeira para métodos de pagamento

## ▶️ Como Executar o Notebook

1. Acesse o notebook no [GitHub](https://github.com/JULIANNEBBORGES/TELECOM_X_BR_P2/blob/main/Telecom_X_%7C_Previs%C3%A3o_de_Evas%C3%A3o_de_Clientes_(Churn)_Parte_2_.ipynb)
2. Abra no [Google Colab](https://colab.research.google.com/) ou ambiente Jupyter
3. Certifique-se de importar os dados dos cliente - df_cleaned.csv disponéveis em (https://github.com/JULIANNEBBORGES/TELECOM_X_BR_P2/blob/main/df_cleaned.csv)
4. Execute as células sequencialmente. 

## 📘 Visualização Interativa

Você pode acessar e executar este projeto diretamente no Google Colab:

🔗 [Abrir notebook no Google Colab](https://colab.research.google.com/drive/1IqsisYIbGYNtBo07WPEDIz0lVorff7gL?usp=sharing)

## ✅ Conclusão

O projeto demonstrou como técnicas de ciência de dados podem ser aplicadas para resolver problemas reais de negócios. Através da análise exploratória, engenharia de features e modelagem preditiva, foi possível identificar perfis de risco e propor estratégias de retenção com potencial de reduzir o churn em até **20%**.

## 👩‍💻 Autor

**Juliane Borges**  
Aluna do projeto **ONE - Oracle Next Education**  
💼 [GitHub](http://github.com/JULIANNEBBORGES)  
📎 [LinkedIn](https://www.linkedin.com/in/julianebb)





