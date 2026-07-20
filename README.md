# T2-Trabalho-Final-PLN

# Avaliação Multidimensional de Grandes Modelos de Linguagem em Ambientes RAG para Detecção de Alucinações

Este repositório contém a implementação utilizada no trabalho final da disciplina de **Processamento de Linguagem Natural (PLN)**. O objetivo é avaliar o desempenho de Grandes Modelos de Linguagem (LLMs) em uma tarefa de perguntas e respostas em português utilizando um ambiente de **pseudo-Retrieval-Augmented Generation (pseudo-RAG)** baseado no conjunto de dados SQuAD-PT.

## Objetivo

O experimento compara cinco modelos de linguagem de código aberto quanto à capacidade de gerar respostas:

- semanticamente próximas às respostas de referência;
- lexicalmente fundamentadas no contexto recuperado.

A avaliação utiliza duas métricas complementares:

- Similaridade Semântica
- TF-IDF

As métricas são normalizadas e combinadas em um **Score Final**, permitindo comparar o desempenho dos modelos.

---

## Modelos Avaliados

- Sabiá-7B
- Tucano-2b4
- Gaia-4B
- SmolLM2-1.7B-Instruct
- Qwen2.5-7B-Instruct

---

## Dataset

Foi utilizada a divisão de validação do **SQuAD-PT v1.1**, versão em português do Stanford Question Answering Dataset.

O experimento considera:

- 250 perguntas;
- 5 tópicos;
- contextos em português;
- respostas de referência.

---

## Metodologia

O pipeline experimental é composto pelas seguintes etapas:

1. Seleção dos exemplos do SQuAD-PT;
2. Pré-processamento dos textos;
3. Segmentação dos contextos em *chunks*;
4. Recuperação pseudo-RAG utilizando Similaridade Semântica e TF-IDF;
5. Geração das respostas pelos LLMs;
6. Avaliação por Similaridade Semântica, TF-IDF e Score Final.

---

## Bibliotecas Utilizadas

- Python
- Transformers
- PyTorch
- Sentence Transformers
- datasets
- spaCy
- scikit-learn
- pandas
- NumPy
- BitsAndBytes
- ftfy

---

## Como Executar

### 1. Clone o repositório

```bash
git clone https://github.com/Felix-Leonel/T2-Trabalho-Final-PLN.git
cd T2-Trabalho-Final-PLN
```

### 2. Instale as dependências

```bash
pip install datasets transformers accelerate bitsandbytes sentencepiece
pip install sentence-transformers pandas numpy tqdm scikit-learn torch spacy ftfy
python -m spacy download pt_core_news_sm
```

### 3. Execute o notebook

Abra o notebook

```
Trabalho_Final_PLN_Detecção_de_Alucinações.ipynb
```

no Google Colab ou no Jupyter Notebook.

A execução seguirá automaticamente todas as etapas do experimento.

---

## Saídas Geradas

Ao final da execução são produzidos arquivos contendo, entre outros resultados:

- respostas geradas pelos modelos;
- Similaridade Semântica;
- TF-IDF;
- Score Final;
- ranking geral dos modelos;
- ranking por tópico.

---

## Hardware Utilizado

Os experimentos foram executados no **Google Colab** com aceleração por **GPU**, utilizando quantização em **4 bits (NF4)** quando suportada pelo modelo para reduzir o consumo de memória.

---

## Reprodução

Para reproduzir os resultados:

1. instalar todas as dependências;
2. executar o notebook na ordem em que as células estão organizadas;
3. aguardar a geração das respostas e o cálculo das métricas.

---

## Autores

**Félix Leonel Vasconcelos da Silva**

**Ivanilton Reinato de Andrade**

**Luis Eduardo Rasch**
