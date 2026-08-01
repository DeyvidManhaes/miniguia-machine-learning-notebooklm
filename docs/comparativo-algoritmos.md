# Comparativo de Algoritmos de Machine Learning

Tabela comparativa dos principais algoritmos, considerando funcionamento, vantagens, desvantagens, complexidade, tempo de treino, interpretabilidade e casos de uso.

| Algoritmo | Funcionamento | Vantagens | Desvantagens | Complexidade | Tempo de Treino | Interpretabilidade | Casos de Uso |
|---|---|---|---|---|---|---|---|
| **Regressão Linear** | Ajusta uma linha reta aos dados, minimizando a soma dos quadrados dos erros. | Simples de implementar e muito rápida para treinar. | Assume relações lineares; sensível a outliers. | Baixa | Muito rápido | Alta | Previsão de valores contínuos (ex.: preço de casas). |
| **Regressão Logística** | Projeta a probabilidade de um resultado binário usando uma função logística. | Excelente baseline; robusta contra ruído. | Não captura relações não lineares complexas sem engenharia de atributos. | Baixa | Rápido | Alta | Classificação binária (spam, aprovação de crédito). |
| **Random Forest** | Ensemble de múltiplas árvores de decisão treinadas em subconjuntos dos dados. | Lida bem com dados ruidosos e valores ausentes; reduz overfitting. | Pode ser lento para inferência em tempo real se o conjunto for muito grande. | Média | Médio (paralelizável) | Média | Dados tabulares e problemas onde a generalização é vital. |
| **XGBoost / Gradient Boosting** | Boosting sequencial: cada árvore corrige os erros das anteriores. | Performance de estado da arte em dados estruturados; alta eficiência em larga escala. | Requer ajuste cuidadoso de hiperparâmetros para evitar overfitting. | Alta | Médio | Média / Baixa | Competições de dados e aplicações de alta performance com dados tabulares. |
| **Redes Neurais (Deep Learning)** | Camadas de neurônios que processam dados via propagação e ajuste de pesos (backpropagation). | Aprendem padrões profundos em dados não estruturados automaticamente. | Exigem grandes volumes de dados e alto poder computacional (GPUs). | Muito alta | Lento (exige hardware) | Baixa ("caixa preta") | Visão computacional, reconhecimento de voz, bioinformática. |
| **Transformers** | Arquitetura baseada exclusivamente em mecanismos de atenção, sem recorrência ou convolução. | Altamente paralelizáveis; qualidade superior em tarefas de sequência. | Consumo massivo de memória e hardware extremo para treinamento. | Extremamente alta | Lento (mas paralelizável) | Muito baixa | Modelos de linguagem (LLMs), tradução automática, processamento de texto. |

## Considerações para o Engenheiro de ML

- **Seleção de algoritmo:** processo iterativo — comece por modelos simples e interpretáveis (Regressão Logística/Linear) para estabelecer uma baseline antes de evoluir para modelos complexos.
- **Interpretabilidade vs. Performance:** trade-off constante. Deep Learning oferece maior precisão em dados complexos, mas atua como "caixa preta", o que pode dificultar a conformidade com regulações que exigem explicabilidade em sistemas de alto risco (ex.: EU AI Act).
- **Eficiência operacional:** em produção com restrições de latência, algoritmos mais leves ou modelos comprimidos (via quantização) são preferíveis para inferência em milissegundos.
