# Miniguia de Estudos — Machine Learning Engineering

## Ciclo de Vida de um Projeto de Machine Learning

```text
Escopo (Scoping)
        ↓
Coleta e Engenharia de Dados
        ↓
Análise Exploratória (EDA)
        ↓
Feature Engineering
        ↓
Treinamento
        ↓
Validação e Auditoria
        ↓
Avaliação
        ↓
Deploy
        ↓
Monitoramento
        ↓
Retreinamento
```

## Resumo dos Principais Conceitos

### Escopo e Definição
Etapa inicial em que se definem os objetivos técnicos e de negócio, as métricas de sucesso (latência, custo, desempenho) e se avalia se o problema realmente exige Machine Learning ou pode ser resolvido com regras simples.

### Engenharia de Dados
Envolve a construção de pipelines de ingestão, a limpeza e transformação dos dados, o versionamento (ex.: DVC) para garantir reprodutibilidade, e o uso de Feature Stores (ex.: Feast) para reutilizar atributos entre treino e produção.

### Análise Exploratória (EDA)
Compreensão dos dados por meio de estatísticas descritivas e visualizações, identificando padrões, distribuições, correlações e possíveis problemas.

### Feature Engineering
Criação, transformação e seleção das variáveis mais relevantes para aumentar a capacidade preditiva do modelo.

### Treinamento e Rastreamento de Experimentos
Etapa em que o algoritmo aprende os padrões dos dados. O rastreamento de experimentos (parâmetros, métricas, versões de código e artefatos) é feito com ferramentas como MLflow e Weights & Biases.

### Validação e Auditoria
O modelo é testado em dados nunca vistos, para avaliar generalização. Inclui análise de vieses e, para modelos de alto risco, conformidade com regulações como o EU AI Act, que exige documentação técnica e explicabilidade.

### Deploy e Serving
Empacotamento do modelo (geralmente via Docker) e disponibilização em infraestrutura de inferência em tempo real ou processamento em lote, orquestrada por ferramentas como Kubernetes ou Kubeflow.

### Monitoramento e Retreinamento
Acompanhamento contínuo do modelo em produção, com detecção de Data Drift e Model Drift, alertas automáticos e ciclos de Treinamento Contínuo (CT) para manter o desempenho ao longo do tempo.

---

## Explicando MLE em linguagem simples: a analogia do carro de corrida

Imagine que a Inteligência Artificial é o **motor** de um carro de corrida.

- O **Cientista de Dados** é o pesquisador que estuda o combustível e desenha o motor ideal, testando em laboratório (o ambiente experimental) para ver se ele atinge alta velocidade.
- O **Engenheiro de Machine Learning** é quem constrói o carro inteiro ao redor desse motor, coloca-o na pista real e garante que ele não falhe a 300 km/h — criando os sistemas de abastecimento automático, monitorando a temperatura em tempo real e garantindo segurança para o piloto (o usuário final).

Em resumo: **MLE é a disciplina de pegar um modelo matemático e transformá-lo em um produto confiável que milhões de pessoas podem usar ao mesmo tempo.**

### Exemplos do mundo real

- **Netflix/Spotify:** o Cientista de Dados cria a fórmula de recomendação; o Engenheiro de ML garante que a sugestão apareça instantaneamente na tela, mesmo com milhões de acessos simultâneos.
- **Carros autônomos:** o modelo aprende a reconhecer pedestres em fotos; o Engenheiro de ML garante que esse reconhecimento aconteça em milissegundos, com sensores reais, para o carro frear a tempo.
- **Detecção de fraude bancária:** o modelo identifica compras suspeitas; o engenheiro garante que cada transação seja analisada no exato momento em que acontece, bloqueando a fraude antes da confirmação.

### Diferença fundamental

Enquanto o Cientista de Dados foca na estatística e na descoberta (**o "quê" funciona**), o Engenheiro de ML foca nos sistemas e na escala (**o "como" colocar para funcionar com segurança e velocidade**).
