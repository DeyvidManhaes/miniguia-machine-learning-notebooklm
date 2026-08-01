# Prompts Reutilizáveis e Cicatrizes (Troubleshooting)

## Engenharia de Prompts — Antes e Depois

| Objetivo | Prompt Inicial | Prompt Refinado | Aprendizado |
|----------|----------------|-----------------|-------------|
| Entender um conceito | Explique o que é Overfitting. | Explique o que é Overfitting como se eu fosse um desenvolvedor Java iniciando em Machine Learning. | Contextualizar o público gera respostas mais didáticas e objetivas. |
| Comparar algoritmos | Compare Random Forest e XGBoost. | Compare Random Forest e XGBoost considerando desempenho, interpretabilidade, custo computacional, tempo de treinamento e casos de uso. | Definir critérios específicos produz comparações mais completas. |
| Aprender um processo | Como funciona um projeto de Machine Learning? | Explique todas as etapas de um projeto de Machine Learning, desde a coleta dos dados até o monitoramento em produção, utilizando exemplos práticos. | Solicitar o fluxo completo evita respostas fragmentadas. |
| Revisar conteúdo | Faça perguntas sobre Machine Learning. | Crie 10 perguntas de nível intermediário sobre Machine Learning com respostas comentadas ao final. | Definir quantidade e nível melhora a qualidade da revisão. |
| Resumir conteúdo | Faça um resumo sobre Feature Engineering. | Resuma Feature Engineering em no máximo 10 tópicos destacando boas práticas e erros comuns. | Restrições de formato tornam o resumo mais objetivo. |

## Cicatrizes (Troubleshooting)

| Dificuldade Encontrada | Solução Aplicada |
|------------------------|------------------|
| Respostas muito genéricas | Adicionar contexto ao prompt e informar o objetivo da resposta. |
| Explicações excessivamente técnicas | Solicitar linguagem simples e exemplos práticos. |
| Comparações superficiais entre algoritmos | Definir critérios específicos para comparação. |
| Resumos muito extensos | Limitar a quantidade de tópicos ou palavras. |
| Pouca relação com aplicações reais | Solicitar estudos de caso e exemplos utilizados na indústria. |

**Principal aprendizado:** a qualidade das respostas do NotebookLM depende diretamente da clareza, contexto e especificidade dos prompts utilizados.

## Biblioteca de Prompts

### Aprender um Conceito
```text
Explique este conceito utilizando uma linguagem simples e exemplos do mundo real.
```

### Comparar Algoritmos
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

### Preparação para Entrevistas
```text
Você é um entrevistador técnico para uma vaga de Machine Learning Engineer.

Crie 10 perguntas de nível intermediário e avançado baseadas neste material e forneça respostas comentadas.
```

### Revisão Rápida
```text
Resuma este conteúdo em até 10 tópicos destacando apenas os conceitos mais importantes para uma entrevista técnica.
```

### Flashcards
```text
Transforme este conteúdo em flashcards no formato pergunta e resposta.
```

### Aplicação Prática
```text
Mostre como este conceito seria aplicado em um projeto real de Machine Learning, explicando o problema, os dados utilizados, a solução proposta e as tecnologias envolvidas.
```

### Roadmap de Estudos
```text
Monte um plano de estudos de 60 dias para dominar este assunto considerando aproximadamente duas horas de estudo por dia.
```
