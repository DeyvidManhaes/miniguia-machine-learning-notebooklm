# Perguntas e Respostas — Machine Learning Engineering

Respostas geradas a partir da curadoria de fontes no NotebookLM, organizadas pelas categorias definidas no [README](./README.md).

---

## Fundamentos

### O que é Machine Learning Engineering e como ele difere de Data Science?

**Machine Learning Engineering (MLE)** é a disciplina focada em operacionalizar, implantar e manter modelos de aprendizado de máquina em sistemas de produção complexos, garantindo que funcionem de forma confiável e escalável. O engenheiro de ML atua como uma ponte entre a ciência de dados experimental e a engenharia de software tradicional.

**Data Science (DS)** foca na exploração e descoberta de insights: o cientista de dados usa métodos estatísticos para analisar dados, formular hipóteses e construir protótipos que respondam a perguntas de negócio.

Resumindo: o cientista de dados foca no *"porquê"* (análise experimental), o engenheiro de ML foca no *"como"* (integrar isso a um produto final, com infraestrutura, latência e automação).

### Qual a diferença entre Inteligência Artificial, Machine Learning e Deep Learning?

- **Inteligência Artificial (IA):** campo amplo de tecnologias que buscam permitir que máquinas executem tarefas que normalmente exigiriam inteligência humana.
- **Machine Learning (ML):** subconjunto da IA focado em extrair informação a partir de dados — o sistema aprende padrões e faz previsões a partir de exemplos, em vez de seguir regras fixas.
- **Deep Learning (DL):** técnica específica de ML que usa múltiplas camadas de redes neurais para processar dados complexos, como fala e imagens.

### Quais são as etapas do ciclo de vida de um projeto de Machine Learning?

1. **Escopo (Scoping):** definição de objetivos técnicos, requisitos e métricas de sucesso (latência aceitável, valor de negócio).
2. **Dados:** coleta, limpeza, organização e rotulagem — a base de qualquer sistema de ML.
3. **Modelagem e Treinamento:** seleção de algoritmos, ajuste de hiperparâmetros e análise de erros.
4. **Implantação (Deployment):** empacotamento do modelo e disponibilização em infraestrutura de produção (tempo real ou batch).
5. **Monitoramento e Manutenção:** detecção de degradação de desempenho (model drift) e retreinamento contínuo.

### Quando utilizar aprendizado supervisionado, não supervisionado e por reforço?

- **Supervisionado:** quando há dados rotulados (exemplos com resposta correta). Ideal para classificação (ex.: detecção de spam) e regressão (ex.: preço de imóveis).
- **Não supervisionado:** para descobrir padrões ocultos em dados sem rótulo. Útil em clustering de clientes e redução de dimensionalidade.
- **Por reforço:** quando um agente precisa aprender decisões em um ambiente dinâmico, por meio de recompensas e punições. Comum em robótica, jogos e sistemas de recomendação complexos.

---

## Pré-processamento

### Como tratar valores ausentes em um conjunto de dados?

Primeiro, avalia-se o padrão de ausência: MCAR (completamente aleatório), MAR (aleatório) ou MNAR (não aleatório). Estratégias comuns:

- **Deleção:** remoção de registros ou pares de observações, quando a ausência é mínima.
- **Imputação estatística:** preenchimento com média, mediana, moda, ou forward-fill em séries temporais.
- **Imputação baseada em modelos:** algoritmos que preveem os valores ausentes.
- **Flag de ausência:** criação de uma feature binária indicando que o dado original faltava — pode gerar sinal útil para o modelo.

### Como identificar e tratar outliers?

Identificação geralmente ocorre via análise exploratória e algoritmos de detecção de novidade/anomalia (Novelty and Outlier Detection). Uma abordagem comum de tratamento é o uso de **regressão robusta**, menos sensível a outliers. Em produção, o monitoramento contínuo ajuda a detectar *data drift*, que pode se manifestar como aumento de valores fora do padrão esperado.

### Quando utilizar normalização ou padronização?

- **Padronização (Standardization):** remove a média e escala a variância (média 0, desvio padrão 1). Recomendada para algoritmos que assumem distribuição normal ou dependem de distância entre pontos (SVMs, redes neurais).
- **Normalização (Normalization):** escala os dados para um intervalo fixo (ex.: 0 a 1). Útil quando os limites dos dados são conhecidos e quando se quer preservar a esparsidade dos dados originais.

### Como selecionar as melhores features para um modelo?

- **Remoção de baixa variância:** elimina features que quase não mudam entre registros.
- **Seleção univariada:** avalia cada feature isoladamente em relação ao alvo, com testes estatísticos.
- **Eliminação Recursiva de Features (RFE):** treina o modelo repetidamente, removendo as features menos importantes.
- **Seleção Sequencial (SFS):** adiciona ou remove features iterativamente, conforme a performance do modelo.
- **Seleção baseada em modelos:** usa a importância de atributos calculada por algoritmos como Random Forest.

---

## Modelagem

### Como escolher o algoritmo mais adequado?

É um processo iterativo que começa no escopo, definindo as variáveis de entrada (X) e saída (Y), e avaliando se o problema exige ML ou pode ser resolvido com regras simples. A escolha depende do tamanho dos dados, do tipo de tarefa (classificação, regressão, agrupamento) e da natureza dos atributos.

### Quando utilizar Regressão Logística, Random Forest ou XGBoost?

- **Regressão Logística:** classificação binária; ótimo modelo de linha de base (baseline), simples e robusto a ruído.
- **Random Forest:** ensemble de árvores de decisão; lida bem com dados ruidosos e valores ausentes, boa generalização em dados tabulares.
- **XGBoost:** boosting sequencial que corrige erros de modelos anteriores; performance de ponta em dados tabulares e larga escala, mas exige ajuste cuidadoso de hiperparâmetros.

### Quando redes neurais são uma alternativa melhor?

Quando os dados são complexos e não estruturados (imagem, áudio, texto), onde algoritmos tradicionais não capturam padrões profundos. São a melhor escolha em visão computacional, NLP, robótica/jogos e bioinformática — preferíveis quando há grande volume de dados e poder computacional disponível.

---

## Avaliação

### Qual métrica utilizar em bases de dados desbalanceadas?

Acurácia costuma ser enganosa (ex.: detecção de fraude, onde 99,9% de acurácia pode significar que o modelo nunca detecta o evento raro). Recomenda-se usar métricas como **Precision** e **Recall**, avaliando o desempenho nos subconjuntos críticos dos dados.

### Quando priorizar Precision, Recall ou F1-Score?

- **Recall:** mede a capacidade de encontrar todos os casos positivos reais — essencial quando falsos negativos são inaceitáveis.
- **Precision:** mede a qualidade das previsões positivas — importante para evitar falsos positivos.
- Existe um trade-off entre as duas; a escolha depende do impacto de negócio de cada tipo de erro.

### Como interpretar a métrica ROC AUC?

Avalia a capacidade do modelo de distinguir entre classes em diferentes limites de decisão (thresholds). É útil para comparar diferentes iterações de um algoritmo durante experimentação.

### Como identificar Overfitting e Underfitting?

**Overfitting:** o modelo aprende o ruído dos dados de treino em vez dos padrões reais — desempenho ótimo no treino, mas fraco em dados novos. Diagnóstico: erro de treino muito baixo e erro de validação alto. Prevenção: regularização (L1/L2), aumento de dados e simplificação da arquitetura.

**Underfitting:** o modelo não aprende padrões suficientes dos dados, apresentando desempenho ruim tanto no treino quanto na validação.

---

## Produção

### Como funciona o deploy de um modelo?

1. **Empacotamento:** modelo, pesos e código de inferência salvos em um formato padrão.
2. **Estratégias de serviço:** batch scoring (processamento offline em lote) ou serviço em tempo real (APIs REST/gRPC).
3. **Infraestrutura:** implantação em servidores, nuvem (AWS SageMaker, Google Vertex AI) ou edge.
4. **Escalabilidade:** ferramentas como Kubernetes ou KServe gerenciam conexões simultâneas e escalam conforme a demanda.

### Qual é o papel do MLflow?

Plataforma padrão de mercado para o ciclo de vida do ML, com quatro funções principais: rastreamento de experimentos (parâmetros, código, métricas), registro de modelos (versões e estágios como "Staging"/"Produção"), empacotamento para reprodutibilidade, e — em versões recentes — suporte a rastreamento de prompts e avaliação de LLMs.

### Como monitorar modelos em produção?

Inclui monitoramento de desempenho (precisão, latência, throughput), monitoramento de dados (mudanças na distribuição de entrada) e alertas automáticos quando as métricas caem abaixo do esperado. Ferramentas comuns: Evidently AI para detecção de desvios, Prometheus e Grafana para dashboards.

### O que são Data Drift e Model Drift?

- **Data Drift:** mudança na distribuição dos dados de entrada em produção, em relação aos dados de treino (ex.: mudança no perfil demográfico dos usuários).
- **Model Drift (ou concept drift):** mudança na relação estatística entre entrada e alvo ao longo do tempo, tornando os padrões aprendidos obsoletos e reduzindo a precisão das previsões.

### Quando devo realizar o retreinamento do modelo?

Principais gatilhos: detecção de drift significativo, disponibilidade de novos dados rotulados, intervalos agendados (Treinamento Contínuo diário/semanal/mensal) e mudança nos requisitos de negócio. Em organizações com alta maturidade de MLOps, esses loops podem ser totalmente automatizados via pipelines agênticos.
