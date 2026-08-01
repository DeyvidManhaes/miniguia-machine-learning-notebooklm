# miniguia-machine-learning-notebooklm
Guia prático de Machine Learning com NotebookLM, incluindo engenharia de prompts, resumos e referências técnicas.

---
# Contexto

Este projeto foi desenvolvido como parte de um desafio da DIO com o objetivo de explorar o NotebookLM como ferramenta de apoio aos estudos e à organização do conhecimento.

O tema escolhido foi Machine Learning Engineering, por ser uma das áreas mais relevantes da Inteligência Artificial e essencial para o desenvolvimento de soluções capazes de transformar dados em modelos preditivos utilizados em aplicações reais.

O caderno temático foi construído a partir de uma curadoria de materiais técnicos confiáveis, incluindo documentações oficiais, cursos e artigos de referência. Com o auxílio do NotebookLM, foi possível sintetizar conteúdos, elaborar perguntas estratégicas, revisar conceitos e organizar um guia de estudos reutilizável para futuras consultas.

---
# Objetivos de Estudo

Este material tem como finalidade consolidar os principais conhecimentos sobre o ciclo de vida de um projeto de Machine Learning Engineering, abrangendo desde a preparação dos dados até o monitoramento de modelos em produção.

## Os principais objetivos deste caderno são:

- Compreender as etapas do desenvolvimento de modelos de Machine Learning.
- Estudar técnicas de pré-processamento e engenharia de atributos (Feature Engineering).
- Entender os principais algoritmos de aprendizado supervisionado e não supervisionado.
- Conhecer métricas de avaliação e validação de modelos.
- Explorar ferramentas utilizadas na indústria, como Scikit-Learn, PyTorch e MLflow.
- Desenvolver habilidades de engenharia de prompts para potencializar o uso do NotebookLM como ferramenta de aprendizagem.
- Produzir um material organizado para revisões futuras e consultas rápidas.
---
# Curadoria de Fontes

Para garantir a qualidade das informações utilizadas neste caderno temático, foram selecionadas fontes abertas e amplamente reconhecidas pela comunidade de Machine Learning.

| Fonte	| Descrição| Link |
|:-----|:------|:------|
|Google Machine Learning Crash Course	| Curso introdutório desenvolvido pelo Google com conceitos fundamentais, exercícios e exemplos práticos sobre Machine Learning.|https://developers.google.com/machine-learning/crash-course
|Scikit-Learn User Guide	|Documentação oficial da biblioteca Scikit-Learn, referência para algoritmos clássicos de Machine Learning e construção de pipelines.|https://scikit-learn.org/stable/user_guide.html
|PyTorch Documentation	|Documentação oficial do framework PyTorch, amplamente utilizado para Deep Learning e desenvolvimento de redes neurais.| https://pytorch.org/docs/stable/index.html
|MLflow Documentation	|Documentação oficial da plataforma MLflow para rastreamento de experimentos, gerenciamento de modelos e implantação em produção.|https://mlflow.org/docs/latest/index.html
|Attention Is All You Need	|Artigo científico que introduziu a arquitetura Transformer, base para os atuais Grandes Modelos de Linguagem (LLMs).|https://arxiv.org/abs/1706.03762

### Observação: Todos os materiais acima foram selecionados por serem fontes oficiais ou amplamente reconhecidas pela comunidade científica e utilizados como base para consultas, resumos e geração de conteúdos no NotebookLM.
---
# Engenharia de Prompts e "Cicatrizes"

Durante a utilização do NotebookLM foram realizados diversos testes para compreender como pequenas alterações na forma de elaborar um prompt influenciam diretamente a qualidade das respostas geradas.

## Perguntas Estratégicas
### Fundamentos
- O que é Machine Learning Engineering e como ele difere de Data Science?
- Qual a diferença entre Inteligência Artificial, Machine Learning e Deep Learning?
- Quais são as etapas do ciclo de vida de um projeto de Machine Learning?
- Quando utilizar aprendizado supervisionado, não supervisionado e por reforço?
### Pré-processamento
- Como tratar valores ausentes em um conjunto de dados?
- Como identificar e tratar outliers?
- Quando utilizar normalização ou padronização?
- Como selecionar as melhores features para um modelo?

### Modelagem

- Como escolher o algoritmo mais adequado para um problema?
- Quais são as diferenças entre Regressão Logística, Random Forest e XGBoost?
- Quando redes neurais são uma melhor alternativa?

### Avaliação

- Qual métrica utilizar em bases de dados desbalanceadas?
- Quando priorizar Precision, Recall ou F1-Score?
- Como interpretar a métrica ROC AUC?
- Como identificar Overfitting e Underfitting?

### Produção

- Como realizar o deploy de um modelo?
- Qual é o papel do MLflow?
- Como monitorar modelos em produção?
- O que são Data Drift e Model Drift?

---
# Engenharia de Prompts

| Objetivo | Prompt Inicial | Prompt Refinado | Aprendizado |
|----------|----------------|-----------------|-------------|
| Entender um conceito | Explique o que é Overfitting. | Explique o que é Overfitting como se eu fosse um desenvolvedor Java iniciando em Machine Learning. | Contextualizar o público gera respostas mais didáticas e objetivas. |
| Comparar algoritmos | Compare Random Forest e XGBoost. | Compare Random Forest e XGBoost considerando desempenho, interpretabilidade, custo computacional, tempo de treinamento e casos de uso. | Definir critérios específicos produz comparações mais completas. |
| Aprender um processo | Como funciona um projeto de Machine Learning? | Explique todas as etapas de um projeto de Machine Learning, desde a coleta dos dados até o monitoramento em produção, utilizando exemplos práticos. | Solicitar o fluxo completo evita respostas fragmentadas. |
| Revisar conteúdo | Faça perguntas sobre Machine Learning. | Crie 10 perguntas de nível intermediário sobre Machine Learning com respostas comentadas ao final. | Definir quantidade e nível melhora a qualidade da revisão. |
| Resumir conteúdo | Faça um resumo sobre Feature Engineering. | Resuma Feature Engineering em no máximo 10 tópicos destacando boas práticas e erros comuns. | Restrições de formato tornam o resumo mais objetivo. |

---

##  Cicatrizes (Troubleshooting)

Durante os testes foram identificadas algumas dificuldades e estratégias para melhorar os resultados obtidos.

| Dificuldade Encontrada | Solução Aplicada |
|------------------------|------------------|
| Respostas muito genéricas | Adicionar contexto ao prompt e informar o objetivo da resposta. |
| Explicações excessivamente técnicas | Solicitar linguagem simples e exemplos práticos. |
| Comparações superficiais entre algoritmos | Definir critérios específicos para comparação. |
| Resumos muito extensos | Limitar a quantidade de tópicos ou palavras. |
| Pouca relação com aplicações reais | Solicitar estudos de caso e exemplos utilizados na indústria. |

**Principal aprendizado:** a qualidade das respostas do NotebookLM depende diretamente da clareza, contexto e especificidade dos prompts utilizados.

---

#  Miniguia de Estudos

##  Ciclo de Vida de um Projeto de Machine Learning

```text
Coleta dos Dados
        ↓
Limpeza dos Dados
        ↓
Análise Exploratória (EDA)
        ↓
Feature Engineering
        ↓
Treinamento
        ↓
Validação
        ↓
Avaliação
        ↓
Deploy
        ↓
Monitoramento
        ↓
Retreinamento
```

---

##  Resumo dos Principais Conceitos

###  Coleta e Preparação dos Dados

A primeira etapa consiste na obtenção e preparação dos dados que serão utilizados pelo modelo. Nela são tratados valores ausentes, inconsistências, duplicidades e transformações necessárias para garantir a qualidade das informações.

###  Análise Exploratória dos Dados (EDA)

Tem como objetivo compreender os dados por meio de estatísticas descritivas e visualizações, identificando padrões, distribuições, correlações e possíveis problemas.

###  Feature Engineering

Processo responsável pela criação, transformação e seleção das variáveis mais relevantes para aumentar a capacidade preditiva do modelo.

###  Treinamento

Etapa em que o algoritmo aprende padrões presentes nos dados de treinamento para realizar previsões futuras.

###  Avaliação

Após o treinamento, o modelo é avaliado utilizando métricas adequadas ao problema, como Accuracy, Precision, Recall, F1-Score e ROC AUC.

###  Deploy

Consiste na disponibilização do modelo para utilização em aplicações reais, APIs ou pipelines automatizados.

###  Monitoramento

Mesmo após entrar em produção, o modelo deve ser acompanhado continuamente para identificar degradação de desempenho, Data Drift e Model Drift, permitindo ações de manutenção e retreinamento quando necessário.

---

#  Glossário

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
| **Model Drift** | Redução do desempenho do modelo devido às mudanças no comportamento dos dados ou do problema. |

---

#  Prompts Reutilizáveis

###  Aprender um Conceito

```text
Explique este conceito utilizando uma linguagem simples e exemplos do mundo real.
```

###  Comparar Algoritmos

```text
Compare os seguintes algoritmos em formato de tabela contendo:

- Funcionamento
- Vantagens
- Desvantagens
- Complexidade
- Tempo de treinamento
- Interpretabilidade
- Casos de uso
```

###  Preparação para Entrevistas

```text
Você é um entrevistador técnico para uma vaga de Machine Learning Engineer.

Crie 10 perguntas de nível intermediário e avançado baseadas neste material e forneça respostas comentadas.
```

###  Revisão Rápida

```text
Resuma este conteúdo em até 10 tópicos destacando apenas os conceitos mais importantes para uma entrevista técnica.
```

###  Flashcards

```text
Transforme este conteúdo em flashcards no formato pergunta e resposta.
```

###  Aplicação Prática

```text
Mostre como este conceito seria aplicado em um projeto real de Machine Learning, explicando o problema, os dados utilizados, a solução proposta e as tecnologias envolvidas.
```

###  Roadmap de Estudos

```text
Monte um plano de estudos de 60 dias para dominar este assunto considerando aproximadamente duas horas de estudo por dia.
```

---

#  Conclusão

A utilização do NotebookLM demonstrou como ferramentas de Inteligência Artificial podem potencializar o processo de aprendizagem quando combinadas com uma boa curadoria de fontes e uma engenharia de prompts bem estruturada.

Além de consolidar conhecimentos sobre Machine Learning Engineering, este projeto possibilitou desenvolver habilidades importantes, como organização do conhecimento, pensamento crítico, síntese de informações e elaboração de prompts mais eficientes.

O resultado é um material de consulta reutilizável que poderá servir como apoio para futuras revisões, preparação para entrevistas técnicas e desenvolvimento de projetos na área de Inteligência Artificial e Machine Learning.

---

## 👨‍💻 Autor

**Deyvid Manhães**

- GitHub: https://github.com/DeyvidManhaes
- LinkedIn: https://www.linkedin.com/in/deyvidmanhaes/
