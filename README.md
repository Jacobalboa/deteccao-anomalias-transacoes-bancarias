# Detecção de Anomalias em Transações Bancárias

Projeto desenvolvido durante a aula da DIO com **Isadora Ferrão**, utilizando Python e Machine Learning para trabalhar com a detecção de fraudes em transações bancárias.

## Objetivo

Explorar um conjunto de dados de transações de cartão de crédito e aplicar técnicas de Machine Learning para identificar transações fraudulentas, considerando principalmente o problema de **classificação desbalanceada**.

## Tecnologias utilizadas

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- imbalanced-learn (SMOTE)
- XGBoost
- SHAP

## Dataset

O notebook carrega o dataset diretamente da URL:

`https://storage.googleapis.com/download.tensorflow.org/data/creditcard.csv`

O arquivo de dados não é incluído neste repositório. Ele é carregado automaticamente pelo notebook.

## Etapas do projeto

### 1. Carregamento do dataset
Leitura dos dados utilizando Pandas.

### 2. Classificação desbalanceada
Análise da distribuição da variável `Class`, considerando que fraudes são raras.

### 3. Feature Engineering
Criação da variável `Amount_log` utilizando `log1p` e posterior padronização para criar `Amount_scaled`.

### 4. Treinamento do modelo
Separação dos dados em treino e teste utilizando `train_test_split` com estratificação.

### 5. Logistic Regression
Treinamento e avaliação utilizando `classification_report`.

### 6. Curvas ROC e Precision-Recall
Avaliação do comportamento do modelo utilizando AUC, ROC e Precision-Recall.

### 7. Balanceamento dos dados
Demonstração de:
- Undersampling
- Oversampling com SMOTE

### 8. Random Forest
Treinamento de um modelo Random Forest com `class_weight='balanced'`.

### 9. Pipeline
Aplicação de um Pipeline com `StandardScaler` e Logistic Regression.

### 10. Ajuste de Threshold
Teste de um threshold de `0.2` para alterar a classificação das transações.

### 11. XGBoost
Aplicação do XGBoost considerando o desbalanceamento das classes.

### 12. Importância das variáveis
Visualização da importância das variáveis utilizadas pelo XGBoost.

### 13. Ajuste de hiperparâmetros
Uso de `GridSearchCV` para testar combinações de `n_estimators` e `max_depth`, utilizando Recall como métrica.

### 14. Explicabilidade com SHAP
Uso do SHAP para analisar como as variáveis influenciam as decisões do modelo.

## Conclusões da aula

De acordo com o notebook, o **Random Forest** apresentou resultado melhor que a Logistic Regression na detecção das fraudes, principalmente em Recall.

Na etapa seguinte, o **XGBoost** apresentou resultado melhor que o Random Forest nas métricas finais de **Recall, Precision e F1-score**.

O projeto também mostra a importância de métricas adequadas para problemas desbalanceados e da explicabilidade dos modelos de Machine Learning.

## Estrutura do repositório

```text
deteccao-anomalias-transacoes-bancarias/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── notebooks/
│   └── Detecção_de_Anomalias_em_Transações_em_Python.ipynb
│
├── data/
│   └── README.md
│
├── images/
│   └── README.md
│
└── src/
    └── README.md
```

## Como executar

### 1. Clone o repositório

```bash
git clone https://github.com/SEU-USUARIO/deteccao-anomalias-transacoes-bancarias.git
```

### 2. Entre na pasta

```bash
cd deteccao-anomalias-transacoes-bancarias
```

### 3. Instale as dependências

```bash
pip install -r requirements.txt
```

### 4. Abra o notebook

O projeto principal está na pasta `notebooks`.

Você pode executar o notebook pelo **VS Code**, Jupyter Notebook ou Google Colab.

## Autor

**Jacomo Silvestre Domingos**

Projeto desenvolvido como parte dos estudos na **DIO**.
