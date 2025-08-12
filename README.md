
# 📊 TELECOM_X_BR_P2 | Previsão de Evasão de Clientes (Churn)

## 📌 Descrição do Projeto

Este projeto representa a **segunda etapa do desafio proposto pela Alura em parceria com a Oracle Next Education (ONE)**, dentro da formação em **Data Science**. Tem como objetivo a aplicação de conhecimentos avançados de estatística, regressão e machine learning em um cenário de negócios real, utilizando a abordagem de **Challenge Based Learning**.

A proposta central é analisar os dados da empresa fictícia **Telecom X**, identificar os principais fatores que levam à evasão de clientes (churn) e, mais crucialmente, desenvolver um **modelo preditivo robusto** capaz de antecipar quais clientes estão mais propensos a cancelar seus serviços. Visando  habilitar a Telecom X a implementar estratégias de retenção proativas e data-driven, fomentando o impacto direto da saúde financeira da empresa.

## 🔗 Fontes de Dados
*   📦 [Dados dos Clientes - `df_cleaned.csv`](https://github.com/JULIANNEBBORGES/TELECOM_X_BR_P2/blob/main/df_cleaned.csv)
*   �� [Dicionário de Dados](https://github.com/ingridcristh/challenge2-data-science/tree/main)

## 🔗 Desafio Anterior

Este projeto é a continuação do desafio anterior:

**📊 Análise de Evasão de Clientes (Churn) - Telecom X | Parte 1**
🔗 [Repositório Parte 1](https://github.com/JULIANNEBBORGES/CHALLENGE_TELECOM_X_BR-)

##📝 Estrutura do Projeto

O notebook (TelecomX_|_Previsão_Evasão_Clientes_(Churn)_P2_.ipynb`) está cuidadosamente estruturado em etapas que refletem o fluxo completo de um projeto de ciência de dados, garantindo clareza e reprodutibilidade:

1.  **Preparação do Ambiente e Importação de Bibliotecas**Configuração inicial e carregamento de todas as bibliotecas necessárias para manipulação de dados, visualização, pré-processamento e modelagem.
2.  **Extração e Análise Preliminar do Dataset**Carregamento dos dados e uma primeira inspeção para entender a estrutura, tipos de dados e identificar valores ausentes.
3.  **Tratamento de Dados Iniciais**Limpeza e estruturação do DataFrame, incluindo remoção de `customerID`, agrupamento de categorias (`'No internet service'` com `'No'`), tratamento de valores nulos em colunas numéricas e remoção de espaços em branco.
4.  **Engenharia de Features**: Criação de novas variáveis a partir das existentes (`HasMultipleServices`, `HasPremiumSecurity`, `HasStreaming`, `TotalExtraServices`) para enriquecer o dataset com informações mais preditivas e capturar padrões de engajamento e uso de serviços.
5.  **Análise Exploratória de Dados (EDA)**Exploração profunda das características dos dados, distribuição da variável alvo (`Churn`), e visualização das relações entre features (numéricas e categóricas) e o churn. Esta etapa incluiu análise de interações entre variáveis e identificação de outliers, fornecendo insights cruciais para a compreensão do fenômeno de evasão.
6.  **Codificação Categórica (Encoding)**: Transformação das variáveis categóricas em um formato numérico (`One-Hot Encoding`) e mapeamento da variável alvo (`Churn`) para valores binários (0 para 'No', 1 para 'Yes'), tornando-as compatíveis com os algoritmos de Machine Learning.
7.  **Análise de Correlação e Multicolinearidade (VIF)**: Investigação das relações lineares entre as features, identificação e tratamento da multicolinearidade (utilizando Heatmap e Variance Inflation Factor - VIF). Este foi um passo crucial para refinar o conjunto de features, removendo redundâncias e garantindo a estabilidade e interpretabilidade dos modelos lineares.
8.  **Balanceamento de Classes (SMOTE)**: Aplicação da técnica Synthetic Minority Over-sampling Technique (SMOTE) para tratar o desbalanceamento inerente da variável alvo. Gerando amostras sintéticas da classe minoritária (`Yes Churn`), garantimos que o modelo possa aprender padrões de ambas as classes sem vieses.
9.  **Normalização/Padronização**: Escalonamento das features numéricas para uma mesma faixa de valores (`StandardScaler`), essencial para algoritmos que são sensíveis à escala dos dados (ex: Regressão Logística, SVM) e para a consistência do pipeline.
10. **Divisão de Dados (Train-Test Split)**: Separação do dataset processado em conjuntos de treino e teste (75%/25% respectivamente) de forma estratificada, assegurando que a proporção das classes de churn seja mantida em ambos os conjuntos para uma avaliação justa do modelo em dados não vistos.
11. **Seleção e Treinamento de Modelos**: Treinamento de diferentes algoritmos de classificação: Regressão Logística (modelo linear e interpretável), Árvore de Decisão (modelo não linear e intuitivo) e Random Forest (ensemble robusto e de alto desempenho), para comparar suas capacidades preditivas.
12. **Avaliação dos Modelos**: Análise detalhada do desempenho de cada modelo utilizando um conjunto abrangente de métricas de classificação, incluindo Acurácia, Precisão, Recall, F1-score, Matriz de Confusão e ROC AUC. Além disso, foi realizada a interpretação da importância das variáveis para cada modelo, fornecendo insights sobre quais fatores mais influenciam as previsões.
13. **Conclusão Estratégica e Próximos Passos**: Síntese dos principais achados do projeto, com recomendações estratégicas acionáveis para a Telecom X e sugestões de direções futuras para o desenvolvimento e aplicação do modelo.

## 📊 Análise e Resultados Chave

O projeto revelou insights críticos sobre os fatores de evasão e o desempenho do modelo preditivo:

*   **Impacto do Tempo de Contrato (`customer.tenure`):** A variável com maior impacto no churn foi o tempo de serviço. Clientes com **pouco tempo de contrato** (`tenure` baixo) tendem a evadir significativamente mais, especialmente nos primeiros meses.
*   **Contratos e Pagamentos:** Clientes com contratos do tipo **Month-to-month** (mês a mês) têm uma probabilidade muito maior de churn, assim como aqueles que utilizam **Electronic Check** (cheque eletrônico) como método de pagamento.
*   **Serviços de Internet:** Clientes com **serviço de Fibra Ótica** apresentaram uma propensão consideravelmente maior ao churn, enquanto a ausência de serviços premium como **OnlineSecurity** e **TechSupport** (segurança online e suporte técnico) também contribui para a evasão.
*   **Cobrança Mensal:** Clientes com `account.Charges.Monthly` mais elevadas tendem a churnar mais, sugerindo sensibilidade ao preço ou percepção de valor inadequada.
*   **Performance do Modelo:** O modelo com melhor desempenho geral para prever o churn foi a **Floresta Aleatória (Random Forest)**, demonstrando robustez e alta capacidade preditiva, com as seguintes métricas no conjunto de teste (após balanceamento com SMOTE e padronização):
    *   **Acurácia:** **0.85** (85%)
    *   **F1-score:** **0.85**
    *   **ROC AUC:** **0.92**

## 🧭 Estratégias Recomendadas para Retenção

Com base nos insights obtidos e na capacidade preditiva do modelo, propomos as seguintes ações estratégicas para a Telecom X reduzir a evasão de clientes:

*   🎁 **Programa de Onboarding e Fidelização para Novos Clientes:** Implementar acompanhamento proativo e ofertas diferenciadas nos primeiros meses, pois é o período mais crítico para a retenção.
*   �� **Promoção de Serviços Premium:** Incentivar a adesão a serviços de valor agregado (segurança online, suporte técnico) que demonstraram ser importantes fatores de fidelização.
*   📄 **Incentivo à Migração para Contratos Anuais/Bienais:** Oferecer benefícios claros (descontos, serviços adicionais) para clientes que optarem por contratos de maior duração, reduzindo significativamente o risco de churn.
*   📞 **Intervenção Proativa e Personalizada:** Utilizar o modelo preditivo para identificar clientes com alta probabilidade de churn em tempo real e realizar abordagens direcionadas (contato proativo, ofertas personalizadas, resolução de problemas específicos).
*   💳 **Análise e Campanhas para Métodos de Pagamento:** Investigar a alta taxa de churn de clientes que pagam via cheque eletrônico. Desenvolver campanhas de educação ou oferecer alternativas mais convenientes de pagamento.
*   ⚡ **Melhoria do Serviço de Fibra Ótica:** Realizar uma análise aprofundada da satisfação e experiência dos clientes de fibra ótica para identificar e corrigir problemas que levam à alta taxa de evasão neste segmento.
*   👨‍🦳 **Atenção ao Cliente Sênior:** Desenvolver programas de atendimento e suporte específicos para clientes seniores, considerando suas necessidades e preferências.

## ▶️ Como Executar o Notebook

Para explorar a análise completa e o modelo preditivo, siga estes passos:

1.  Acesse o notebook diretamente no [GitHub](https://github.com/JULIANNEBBORGES/TELECOM_X_BR_P2/blob/main/TelecomX_%7C_Previs%C3%A3o_Evas%C3%A3o_Clientes_(Churn)_P2_.ipynb) 
2.  Abra-o no [Google Colab](https://colab.research.google.com/) clicando no ícone "Open in Colab" (geralmente no topo do GitHub) ou importando o arquivo `.ipynb` diretamente para o ambiente Colab.
3.  Certifique-se de que o arquivo de dados `df_cleaned.csv` esteja disponível no ambiente Colab. O notebook já contém o código para carregá-lo a partir do ambiente do Colab ou do GitHub se ele for referenciado corretamente.
4.  Execute as células sequencialmente para reproduzir toda a análise e o treinamento do modelo.

## 📘 Visualização Interativa

Você pode acessar e executar este projeto diretamente no Google Colab, garantindo uma experiência interativa com o código e os resultados:

🔗 [Abrir notebook no Google Colab][(https://colab.research.google.com/drive/1ik9Wi3pBDTdviQqbLMC46aD047F7m-0l?usp=sharing)

## ✅ Conclusão

Este projeto demonstrou o poder transformador das técnicas de ciência de dados para resolver problemas de negócios complexos, como a previsão e mitigação de churn. Através de uma análise exploratória aprofundada, engenharia de features inteligentes, e modelagem preditiva avançada (com destaque para o Random Forest), foi possível não apenas identificar os perfis de clientes em risco, mas também propor estratégias de retenção com potencial de **reduzir o churn em até 20%**, gerando um impacto financeiro significativo para a Telecom X. Esta abordagem baseada em dados permite transformar a evasão de clientes de um problema reativo para uma oportunidade de intervenção proativa e estratégica.

## 🚀 Próximos Passos Sugeridos

Para aprimorar ainda mais este projeto e sua aplicabilidade prática, sugerimos os seguintes próximos passos:

1.  **Otimização de Hiperparâmetros**: Realizar um ajuste fino dos hiperparâmetros do modelo Random Forest (e de outros, se aplicável) utilizando técnicas avançadas como `GridSearchCV` ou `RandomizedSearchCV` para maximizar o desempenho.
2.  **Validação Cruzada (Cross-Validation)**: Implementar validação cruzada robusta para garantir a estabilidade do modelo e sua capacidade de generalização em diferentes subconjuntos de dados.
3.  **Análise de Erros Qualitativa**: Aprofundar a análise dos Falsos Positivos e Falsos Negativos da matriz de confusão para entender as implicações de negócio dos erros do modelo e refinar as estratégias de intervenção de forma mais precisa.
4.  **Implantação (Deployment)**: Desenvolver uma solução para integrar o modelo em um ambiente de produção (por exemplo, via API), permitindo que as previsões sejam usadas em tempo real ou em lotes para ações proativas de retenção.
5.  **Monitoramento Contínuo**: Estabelecer um sistema para monitorar o desempenho do modelo ao longo do tempo (drift de dados, performance de predição), garantindo que ele permaneça relevante à medida que o comportamento do cliente e as condições de mercado evoluem.
6.  **Análise de Custo-Benefício**: Quantificar o impacto financeiro potencial das ações de retenção baseadas nas previsões do modelo, demonstrando o ROI (Retorno sobre Investimento) da iniciativa de forma clara para a gestão.
7.  **Exploração de Outros Modelos**: Considerar modelos mais avançados ou específicos, como LightGBM, XGBoost, ou redes neurais, se o desempenho e os requisitos do negócio justificarem a complexidade adicional.

## ♀️ Autor

**Juliane Borges**
Aluna do projeto **ONE - Oracle Next Education**
💼 [GitHub](http://github.com/JULIANNEBBORGES)
📎 [LinkedIn](https://www.linkedin.com/in/julianebb)






