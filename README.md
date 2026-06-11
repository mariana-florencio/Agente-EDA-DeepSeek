# Agente EDA com DeepSeek

Projeto desenvolvido para a disciplina de Processamento de Linguagem Natural (NLP).

O objetivo é implementar um agente capaz de realizar Análise Exploratória de Dados (EDA) sobre um dataset CSV utilizando Large Language Models (LLMs) e ferramentas (tools) especializadas.

## Integrantes

* Nome 1
* Nome 2
* Nome 3
* Nome 4

## Dataset Utilizado

Adult Income Dataset (UCI Machine Learning Repository)

Link oficial:

https://archive.ics.uci.edu/dataset/2/adult

Arquivo utilizado:

https://archive.ics.uci.edu/ml/machine-learning-databases/adult/adult.data

Características:

* 32.561 registros
* 15 colunas
* Variáveis numéricas e categóricas
* Problema relacionado à classificação de renda

## Modelo Utilizado

DeepSeek Chat

A API foi escolhida devido ao baixo custo operacional e compatibilidade com tool calling.

## Funcionalidades

O agente é capaz de:

* Carregar um dataset CSV
* Receber perguntas em português
* Selecionar ferramentas automaticamente
* Encadear múltiplas chamadas de ferramentas
* Gerar gráficos
* Tratar erros sem interromper a execução
* Registrar logs completos das execuções

## Ferramentas Implementadas

### listar_colunas()

Retorna nomes e tipos das colunas.

### descrever_dados()

Retorna estatísticas descritivas do dataset.

### contar_valores(coluna)

Retorna distribuição de valores de uma coluna.

### filtrar(coluna, operador, valor)

Retorna subconjunto filtrado do dataset.

### agrupar_e_agregar(grupo, coluna, funcao)

Executa operações groupby e agregações.

### correlacao(coluna_a, coluna_b)

Calcula correlação entre variáveis numéricas.

### detectar_outliers(coluna)

Detecta outliers utilizando método IQR.

### gerar_grafico(tipo, colunas)

Gera gráficos e salva imagens.

## Estrutura do Projeto

```text
.
├── Agente_EDA.ipynb
├── benchmark.json
├── requirements.txt
├── graficos/
├── logs/
├── results_evaluation/
│   ├── benchmark_detalhado.csv
│   └── summary_metrics.json
└── README.md
```

## Instalação

```bash
pip install -r requirements.txt
```

## Configuração da API

No notebook:

```python
from getpass import getpass

DEEPSEEK_API_KEY = getpass("Digite sua chave DeepSeek: ")
```

## Execução

Execute o notebook:

```text
Agente_EDA.ipynb
```

As células devem ser executadas na ordem apresentada.

## Benchmark

O benchmark contém:

* 10 perguntas factuais
* 15 perguntas analíticas
* 5 perguntas ambíguas ou inválidas

Total:

* 30 perguntas

## Métricas Avaliadas

* Acurácia de seleção de ferramenta
* Acurácia de conteúdo
* Taxa de execução bem-sucedida
* Média de tool calls
* Latência média
* Custo médio por pergunta

## Resultados

Os resultados são exportados para:

```text
results_evaluation/
```

Arquivos gerados:

* benchmark_detalhado.csv
* summary_metrics.json

## Licença

Projeto acadêmico desenvolvido para fins educacionais.
