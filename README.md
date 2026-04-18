<div align="center">

<img src="https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white"/>
<img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white"/>
<img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white"/>
<img src="https://img.shields.io/badge/Accuracy-95.11%25-16a34a?style=for-the-badge"/>

<br/><br/>

# ✈ Airline Passenger Satisfaction
### Classificação Binária com Random Forest · Projeto de Ciência de Dados

*Predição de satisfação de passageiros aéreos com base em 22 variáveis demográficas, operacionais e de avaliação de serviço.*

</div>

---

## Visão Geral

> **Problema:** Companhias aéreas possuem grandes volumes de dados de avaliação de passageiros, mas dificuldade em identificar os fatores críticos que determinam satisfação. Este projeto treina um modelo preditivo capaz de classificar um passageiro como **satisfeito** ou **neutro/insatisfeito** com **95,11% de acurácia**.

<table>
<tr>
<td><b>Algoritmo</b></td><td>Random Forest Classifier</td>
<td><b>Dataset</b></td><td>25.976 passageiros</td>
</tr>
<tr>
<td><b>Acurácia</b></td><td><code>95.11%</code></td>
<td><b>Split</b></td><td>80% treino · 20% teste</td>
</tr>
<tr>
<td><b>Features</b></td><td>22 variáveis</td>
<td><b>n_estimators</b></td><td>100 árvores</td>
</tr>
</table>

---

## Pipeline

```
Raw Data (CSV)
     │
     ▼
┌─────────────────────────────────┐
│  1. Análise Exploratória (EDA)  │  shape, dtypes, describe, missing values
└─────────────────────────────────┘
     │
     ▼
┌─────────────────────────────────┐
│  2. Tratamento de Dados         │  Imputação mediana · 83 valores (0.32%)
└─────────────────────────────────┘
     │
     ▼
┌─────────────────────────────────┐
│  3. Feature Engineering         │  Label Encoding · Drop id/index cols
└─────────────────────────────────┘
     │
     ▼
┌─────────────────────────────────┐
│  4. Modelagem                   │  RandomForestClassifier (n=100, seed=42)
└─────────────────────────────────┘
     │
     ▼
┌─────────────────────────────────┐
│  5. Avaliação                   │  Accuracy: 95.11% · 5.196 amostras de teste
└─────────────────────────────────┘
     │
     ▼
┌─────────────────────────────────┐
│  6. Deploy / Serialização       │  joblib → modelo_airline.pkl
└─────────────────────────────────┘
```

---

## Dataset

**Fonte:** [Kaggle — Airline Passenger Satisfaction](https://www.kaggle.com/datasets/teejmahal20/airline-passenger-satisfaction)  
**Target:** `satisfaction` → `satisfied` (1) ou `neutral or dissatisfied` (0)

| Grupo | Variáveis |
|---|---|
| Demográficas | `Gender`, `Age` |
| Perfil do Passageiro | `Customer Type`, `Type of Travel`, `Class` |
| Operacionais | `Flight Distance`, `Departure Delay`, `Arrival Delay` |
| Avaliações de Serviço (0–5) | `Inflight wifi`, `Online Boarding`, `Seat Comfort`, `Entertainment`, `Food & Drink`, `On-board Service`, `Leg Room`, `Baggage Handling`, `Check-in`, `Inflight Service`, `Cleanliness`, `Gate Location`, `Booking Ease`, `Timing Convenience` |

---

## Feature Importance

As features ranqueadas por importância no modelo Random Forest:

```
Online Boarding       ████████████████████  18.2%
Inflight Wi-Fi        ████████████████      15.3%
Type of Travel        █████████████         12.1%
Class                 ████████████          10.8%
Inflight Entertainment███████████            9.7%
Seat Comfort          ██████████             8.8%
On-board Service      ████████               7.1%
Leg Room              ███████                5.9%
Customer Type         ██████                 5.2%
Food & Drink          █████                  4.3%
```

---

## Resultados e Insights

### Matriz de Confusão (teste — 5.196 amostras)

|  | Previsto: Satisfeito | Previsto: Insatisfeito |
|---|:---:|:---:|
| **Real: Satisfeito** | 2.737 ✅ | 107 ❌ |
| **Real: Insatisfeito** | 147 ❌ | 2.205 ✅ |

### Principais Descobertas

| Segmento | Taxa de Satisfação | Observação |
|---|:---:|---|
| Classe Business | 69% | Maior satisfação entre as classes |
| Classe Eco Plus | 25% | Queda expressiva vs Business |
| Classe Eco | 19% | Pior experiência geral |
| Viagem a Negócios | 62% | Muito superior à pessoal |
| Viagem Pessoal | 10% | Maior grupo de insatisfeitos |
| Cliente Fiel | 49% | Melhor experiência relativa |
| Cliente Não-Fiel | 24% | Mais suscetível à insatisfação |

> **Wi-Fi** e **embarque online** são os maiores diferenciadores entre passageiros satisfeitos e insatisfeitos — uma nota alta nestas duas variáveis é fortemente preditiva de satisfação.

---

## Estrutura do Repositório

```
airline-passenger-satisfaction/
│
├── airline_passenger_satisfaction.ipynb   # Notebook: EDA + modelo + avaliação
├── dashboard.html                         # Dashboard interativo (abrir no browser)
├── requirements.txt                       # Dependências Python
└── README.md
```

---

## Como Executar

```bash
# Clone o repositório
git clone https://github.com/luis-sardinha/airline-passenger-satisfaction.git
cd airline-passenger-satisfaction

# Instale as dependências
pip install -r requirements.txt

# Execute o notebook
jupyter notebook airline_passenger_satisfaction.ipynb
```

Para o dashboard interativo, abra `dashboard.html` diretamente no navegador — sem servidor necessário.

---

## Stack

| Ferramenta | Uso |
|---|---|
| `pandas` | Manipulação e análise de dados |
| `scikit-learn` | Modelo Random Forest + avaliação |
| `joblib` | Serialização do modelo treinado |
| `jupyter` | Ambiente de desenvolvimento |
| `HTML/JS/Chart.js` | Dashboard interativo |

---

<div align="center">

**Luis Sardinha** · [luis.sardinha.dev@gmail.com](mailto:luis.sardinha.dev@gmail.com)

</div>
