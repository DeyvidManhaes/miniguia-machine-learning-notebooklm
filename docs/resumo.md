# Resumo – Machine Learning Engineering (MLE)

## O que é Machine Learning Engineering?

**Machine Learning Engineering (MLE)** é a disciplina responsável por operacionalizar modelos de aprendizado de máquina em ambientes de produção, garantindo que eles sejam **confiáveis**, **escaláveis** e **adaptáveis**.

O engenheiro de Machine Learning atua como uma ponte entre:

- **Data Science**, focada em descoberta de padrões, experimentação e análise estatística;
- **Engenharia de Software**, voltada para o desenvolvimento de sistemas robustos, escaláveis e de alta disponibilidade.

Seu principal objetivo é transformar modelos experimentais em soluções capazes de gerar valor em ambientes reais de produção.

---

# Ciclo de Vida de um Projeto de Machine Learning

## 1️⃣ Escopo e Definição (Scoping)

### Objetivo

Definir claramente o problema de negócio, estabelecer métricas de sucesso e avaliar se a utilização de Machine Learning é realmente necessária.

### Principais atividades

- Definir objetivos técnicos e de negócio.
- Estabelecer métricas de desempenho (precisão, latência, custo etc.).
- Avaliar se o problema pode ser resolvido por regras simples antes de utilizar ML.

---

## 2️⃣ Tratamento e Engenharia de Dados (Data Engineering)

Esta etapa é responsável por preparar os dados que serão utilizados durante o treinamento do modelo.

### Coleta e Ingestão

- Construção de pipelines para ingestão de dados.
- Integração com bancos de dados, APIs e sistemas transacionais.

### Preparação dos Dados

- Limpeza de inconsistências.
- Tratamento de valores ausentes.
- Transformação dos dados.
- Rotulagem (Labeling).

### Versionamento

O versionamento dos dados garante a reprodutibilidade dos experimentos, permitindo identificar exatamente qual conjunto de dados foi utilizado em determinado treinamento.

**Ferramenta de destaque**

- DVC (Data Version Control)

### Feature Store

Repositórios centralizados permitem reutilizar atributos (features) de forma consistente entre treinamento e produção.

**Ferramenta de destaque**

- Feast

---

## 3️⃣ Desenvolvimento e Treinamento do Modelo

Nesta fase ocorre a construção e evolução do modelo de Machine Learning.

### Experimentação

- Escolha de algoritmos.
- Ajuste de hiperparâmetros.
- Comparação entre modelos.

### Rastreamento de Experimentos

Registro de:

- parâmetros utilizados;
- métricas obtidas;
- versões do código;
- artefatos do treinamento.

**Ferramentas**

- MLflow
- Weights & Biases (W&B)

### Versionamento do Modelo

Permite manter histórico do código, pesos do modelo e ambiente de treinamento, facilitando auditorias e rollback.

---

## 4️⃣ Validação e Auditoria

Após o treinamento, o modelo deve ser validado utilizando dados nunca vistos durante o processo de aprendizagem.

### Teste Independente

Avaliação da capacidade de generalização do modelo.

### Análise de Erros

Investigação de:

- vieses (bias);
- falhas específicas;
- desempenho em subconjuntos dos dados.

### Conformidade

Modelos considerados de alto risco devem atender requisitos de qualidade, integridade e explicabilidade antes de serem utilizados em produção.

---

## 5️⃣ Implantação e Servindo o Modelo (Deployment & Serving)

Após a validação, o modelo é disponibilizado para utilização em aplicações reais.

### Empacotamento

Containerização utilizando Docker para garantir ambientes consistentes.

### Infraestrutura

Execução do modelo em serviços capazes de atender:

- inferência em tempo real;
- processamento em lote (Batch).

### Orquestração

Gerenciamento automático de disponibilidade e escalabilidade.

**Ferramentas**

- Kubernetes
- Kubeflow

---

## 6️⃣ Monitoramento e Retreinamento

O ciclo de Machine Learning não termina após o deploy.

Os modelos devem ser monitorados continuamente para garantir que continuem apresentando bom desempenho.

### Detecção de Drift

Monitoramento para identificar:

- **Model Drift:** degradação do desempenho do modelo.
- **Concept Drift:** mudanças na distribuição dos dados do mundo real.

### Alertas

Configuração de notificações automáticas quando métricas de desempenho ficam abaixo do esperado.

### Retreinamento Contínuo (Continuous Training)

Novos dados coletados em produção podem ser utilizados para atualizar automaticamente o modelo, mantendo sua capacidade preditiva ao longo do tempo.

---

# Principais Ferramentas Utilizadas em Machine Learning Engineering

| Categoria | Ferramentas |
|-----------|-------------|
| Orquestração e Pipelines | Kubeflow, Metaflow, Airflow, Prefect |
| Rastreamento de Experimentos | MLflow, Weights & Biases (W&B) |
| Versionamento de Dados | DVC |
| Feature Store | Feast |
| Deploy e Serving | BentoML, KServe, Docker, Kubernetes |
| Monitoramento | Evidently AI, Prometheus, Grafana |
| Plataformas de ML | AWS SageMaker, Google Vertex AI |

---

# Conclusão

Machine Learning Engineering vai muito além da construção de modelos preditivos. Seu foco está em garantir que esses modelos possam ser desenvolvidos, implantados, monitorados e evoluídos de forma confiável em ambientes de produção.

A adoção de práticas de **MLOps**, versionamento, monitoramento contínuo e automação do ciclo de vida permite que modelos de Machine Learning permaneçam reproduzíveis, escaláveis e alinhados às necessidades do negócio.