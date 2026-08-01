# Glossário — Machine Learning Engineering

| Conceito | Definição |
|-----------|-----------|
| **Machine Learning** | Área da Inteligência Artificial que permite aos computadores aprenderem padrões a partir dos dados. |
| **Feature Engineering** | Processo de criação e transformação de atributos utilizados pelos modelos. |
| **Overfitting** | Quando o modelo aprende excessivamente os dados de treinamento e perde capacidade de generalização. |
| **Underfitting** | Quando o modelo não consegue aprender padrões suficientes dos dados. |
| **Cross Validation** | Técnica utilizada para avaliar a capacidade de generalização de um modelo. |
| **Precision** | Proporção de previsões positivas corretas entre todas as previsões positivas realizadas. |
| **Recall** | Capacidade do modelo em identificar corretamente todos os casos positivos. |
| **F1-Score** | Média harmônica entre Precision e Recall. |
| **ROC AUC** | Métrica que avalia a capacidade do modelo em distinguir corretamente diferentes classes. |
| **Pipeline** | Sequência organizada das etapas de preparação dos dados, treinamento e avaliação. |
| **Data Drift** | Mudança na distribuição dos dados utilizados pelo modelo ao longo do tempo. |
| **Model Drift (Concept Drift)** | Redução do desempenho do modelo devido às mudanças no comportamento dos dados ou do problema. |
| **Feature Store** | Repositório centralizado (ex.: Feast) para armazenar e reutilizar atributos de forma consistente entre treino e inferência. |
| **Versionamento de Dados** | Prática (ex.: com DVC) que garante a reprodutibilidade dos experimentos, rastreando qual conjunto de dados foi usado em cada treinamento. |
| **MLOps** | Conjunto de práticas para operacionalizar, versionar, monitorar e automatizar o ciclo de vida de modelos de Machine Learning. |
| **Treinamento Contínuo (CT)** | Loop automatizado em que novos dados coletados em produção são usados para atualizar e reimplantar o modelo periodicamente. |
| **Batch Scoring** | Processamento de previsões em lote, para grandes volumes de dados offline (em oposição à inferência em tempo real). |
