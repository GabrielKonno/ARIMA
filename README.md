# Previsão de Produção de Energia usando ARIMA

## 📋 Descrição
Este projeto implementa um modelo de séries temporais SARIMA (Seasonal ARIMA) para prever a produção de energia com base em dados históricos. O modelo leva em consideração tanto a tendência quanto a sazonalidade dos dados, permitindo previsões mais precisas para o planejamento da produção energética.

## 🎯 Objetivo do Projeto
- Analisar o comportamento temporal da produção de energia
- Identificar padrões sazonais e tendências na série temporal
- Desenvolver um modelo preditivo capaz de realizar previsões precisas para os próximos 12 meses
- Fornecer intervalos de confiança para as previsões realizadas

## 📊 Dados
- **Fonte**: Arquivo 'energy.xlsx' contendo dados históricos de produção de energia
- **Variáveis**: 
  - DATE: índice temporal das observações
  - producao: quantidade de energia produzida
- **Frequência**: Dados mensais
- **Período**: Determinado pela análise dos índices mínimo e máximo do dataset

## 🔍 Metodologia

### 1. Análise Exploratória
- Visualização da série temporal
- Decomposição sazonal para identificação de:
  - Tendência
  - Sazonalidade
  - Resíduos

### 2. Preparação dos Dados
- Verificação de estacionariedade através do teste Augmented Dickey-Fuller (ADF)
- Diferenciação da série para torná-la estacionária
- Identificação da ordem de diferenciação necessária

### 3. Modelagem
- Utilização do auto_arima para identificação automática dos melhores parâmetros
- Implementação do modelo SARIMAX com os parâmetros:
  - ARIMA(1,1,1)
  - Componente Sazonal(1,1,2,6)
- Geração de previsões com intervalos de confiança
- Validação do modelo usando os últimos 12 meses de dados

## 📈 Resultados
- Geração de previsões para os próximos 12 meses
- Avaliação do modelo usando Mean Absolute Error (MAE)
- Visualizações incluindo:
  - Dados reais vs. previsões
  - Intervalos de confiança para as previsões
  - Decomposição da série temporal

## 🛠️ Tecnologias Utilizadas
- Python 3.x
- pandas: Manipulação de dados
- numpy: Operações numéricas
- matplotlib: Visualizações
- statsmodels: Implementação do modelo SARIMAX
- pmdarima: Auto ARIMA para seleção de parâmetros
- scikit-learn: Métricas de avaliação

## 📂 Estrutura do Projeto
```
projeto/
│
├── data/
│   └── energy.xlsx          # Dataset de energia
│
├── src/
│   └── arima.py            # Script principal com a implementação
│
├── requirements.txt         # Dependências do projeto
└── README.md               # Esta documentação
```

## 🚀 Como Executar o Projeto

```bash
# Clone este repositório
git clone https://github.com/seu-usuario/previsao-energia.git

# Entre no diretório
cd previsao-energia

# Instale as dependências
pip install -r requirements.txt

# Execute o script
python src/arima.py
```

## 📝 Principais Conclusões
- O teste ADF confirmou a necessidade de diferenciação para tornar a série estacionária
- O modelo SARIMA captura adequadamente tanto a tendência quanto a sazonalidade dos dados
- As previsões incluem intervalos de confiança que podem ser úteis para o planejamento

## 🔄 Próximos Passos
- Implementar validação cruzada para séries temporais
- Comparar resultados com outros modelos (Prophet, LSTM)
- Adicionar variáveis exógenas que possam influenciar a produção de energia
- Criar uma interface web para visualização das previsões

## 👤 Autor
[Seu Nome]
- LinkedIn: <https://www.linkedin.com/in/gabrielkonno>
- Email: gkonnoc@gmail.com
