<h1 align="center">Detecção de Ataques Cibernéticos com Machine Learning</h1>

<p align="center">
  Sistema de classificação de tráfego de rede utilizando Machine Learning para identificação de tráfego benigno e diferentes tipos de ataques cibernéticos.
</p>

## Sobre o projeto

Este projeto aplica técnicas de **Data Science e Machine Learning** à análise de tráfego de rede com o objetivo de identificar padrões associados a atividades maliciosas.

O desenvolvimento contempla diferentes etapas de um pipeline de Ciência de Dados, incluindo preparação dos dados, análise exploratória, engenharia de atributos, treinamento de modelos e disponibilização das previsões por meio de uma aplicação interativa desenvolvida em **Streamlit**.

A solução permite trabalhar com dois tipos de problema:

- **Classificação Binária:** diferencia tráfego benigno de tráfego malicioso.
- **Classificação Multiclasse:** identifica diferentes categorias de ataques presentes no tráfego de rede.

## Pipeline do projeto

O projeto foi dividido em quatro principais etapas:

### 1. Pré-processamento dos dados

Preparação dos dados utilizados pelos modelos de Machine Learning, incluindo limpeza, tratamento e padronização das informações.

### 2. Análise Exploratória de Dados (EDA)

Investigação das características dos dados de tráfego de rede para identificar distribuições, padrões e diferenças entre tráfego benigno e malicioso.

### 3. Feature Engineering

Preparação e seleção das variáveis utilizadas no treinamento dos modelos preditivos.

### 4. Machine Learning

Treinamento e avaliação de diferentes algoritmos para os cenários de classificação binária e multiclasse.

## Modelos utilizados

### Classificação Binária

- Logistic Regression
- Support Vector Machine (SVM)

### Classificação Multiclasse

- Random Forest
- K-Nearest Neighbors (KNN)
- XGBoost

Os modelos treinados são utilizados posteriormente pela aplicação Streamlit para realizar previsões sobre novos dados de tráfego de rede.

## Funcionalidades da aplicação

- Upload de arquivos CSV contendo dados de tráfego de rede
- Identificação automática do tipo de classificação quando possível
- Seleção manual entre classificação binária e multiclasse
- Seleção do modelo de Machine Learning
- Execução de previsões
- Exibição das probabilidades previstas
- Visualização da distribuição das previsões
- Gráficos para análise dos resultados
- Heatmap das probabilidades na classificação multiclasse

## Tecnologias

- **Python**
- **Pandas**
- **NumPy**
- **Scikit-learn**
- **XGBoost**
- **Matplotlib**
- **Seaborn**
- **Streamlit**
- **Joblib**
- **Jupyter Notebook**

## Estrutura do projeto

```text
Data-Science-Capstone/
├── amostras/
│   ├── amostra_1.csv
│   ├── amostra_2.csv
│   ├── amostra_3.csv
│   ├── amostra_4.csv
│   ├── amostra_5.csv
│   └── amostra_6.csv
│
├── notebooks/
│   ├── 1-data-preprocessing.ipynb
│   ├── 2-exploratory-data-analysis.ipynb
│   ├── 3-feature-engineering.ipynb
│   └── 4-ml-models.ipynb
│
├── scripts/
│   ├── app.py
│   ├── arquivos.py
│   └── visuals.py
│
├── Resumo Executivo - Engenharia Reversa de Malware.pdf
├── requirements.txt
├── LICENSE
└── README.md
```

## Como instalar e executar

### 1. Clone o repositório

```bash
git clone https://github.com/gut0oliveira/Data-Science-Capstone.git
cd Data-Science-Capstone
```

### 2. Crie um ambiente virtual

```bash
python -m venv .venv
```

No Windows:

```bash
.venv\Scripts\activate
```

No Linux/macOS:

```bash
source .venv/bin/activate
```

### 3. Instale as dependências

```bash
pip install -r requirements.txt
```

### 4. Baixe os modelos treinados

O arquivo `modelos.pkl` possui aproximadamente **111 MB** e, por isso, não está armazenado diretamente neste repositório.

➡️ **[Baixar modelos.pkl](https://drive.google.com/uc?export=download&id=1G2KdSuNIB2AhkjIxHYltHwDCeeYp3XHn)**

Após o download, coloque o arquivo dentro da pasta:

```text
notebooks/modelos.pkl
```

A estrutura deverá ficar assim:

```text
notebooks/
├── 1-data-preprocessing.ipynb
├── 2-exploratory-data-analysis.ipynb
├── 3-feature-engineering.ipynb
├── 4-ml-models.ipynb
└── modelos.pkl
```

### 5. Execute a aplicação

Acesse a pasta `scripts`:

```bash
cd scripts
```

Execute o Streamlit:

```bash
streamlit run app.py
```

A aplicação será disponibilizada localmente em:

```text
http://localhost:8501
```

## Como usar a aplicação

### 1. Faça o upload dos dados

Na aplicação, faça upload de um arquivo `.csv` contendo os dados de tráfego de rede que serão analisados.

Para facilitar os testes, o repositório possui arquivos de exemplo disponíveis na pasta:

```text
amostras/
```

### 2. Defina o tipo de classificação

A aplicação trabalha com dois cenários:

- **Classificação Binária:** identifica se o tráfego é benigno ou malicioso.
- **Classificação Multiclasse:** identifica diferentes categorias de ataques.

Quando o arquivo contém a coluna `Tipos de Ataques`, a aplicação identifica automaticamente o tipo de classificação com base nos dados disponíveis.

Caso essa informação não esteja disponível, é possível selecionar manualmente entre:

- Binário
- Multiclasse

### 3. Escolha o modelo

Para **Classificação Binária**, estão disponíveis:

- Logistic Regression
- Support Vector Machine (SVM)

Para **Classificação Multiclasse**, estão disponíveis:

- Random Forest
- K-Nearest Neighbors (KNN)
- XGBoost

### 4. Execute a previsão

Após selecionar o modelo desejado, clique em:

**🔍 Realizar Previsão**

A aplicação processará os registros utilizando o modelo selecionado.

### 5. Analise os resultados

#### Classificação Binária

A aplicação apresenta:

- Probabilidade de tráfego benigno
- Probabilidade de tráfego malicioso
- Classe prevista para cada registro
- Distribuição das previsões
- Proporção entre tráfego benigno e malicioso

#### Classificação Multiclasse

A aplicação apresenta:

- Probabilidade associada a cada classe de ataque
- Classe prevista para cada registro
- Distribuição das classes previstas
- Heatmap das probabilidades de classificação

## Interface da aplicação

Caso todas as etapas tenham sido executadas corretamente, a aplicação apresentará uma interface semelhante à imagem abaixo:

![Aplicação Streamlit](https://github.com/user-attachments/assets/55744db9-be76-4eef-ba8b-abe72ded8d08)

Após carregar um dos arquivos disponíveis em `amostras/`, basta selecionar o modelo desejado e executar a previsão.

## Documentação

O repositório também contém um resumo executivo com uma visão geral do projeto, metodologia utilizada e principais etapas desenvolvidas:

📄 **[Resumo Executivo — Engenharia Reversa de Malware](https://github.com/gut0oliveira/Data-Science-Capstone/blob/main/Resumo%20Executivo%20-%20Engenharia%20Reversa%20de%20Malware.pdf)**

## Autor

**Augusto Oliveira**

[LinkedIn](https://www.linkedin.com/in/augusto-oS/) • [GitHub](https://github.com/gut0oliveira)
