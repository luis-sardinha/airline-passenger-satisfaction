# ✈ Airline Passenger Satisfaction — Previsão com Machine Learning

Projeto de Ciência de Dados que utiliza **Random Forest Classifier** para prever se um passageiro ficará **satisfeito** ou **neutro/insatisfeito** com uma companhia aérea, com base em suas características e avaliações de serviço.

---

## 📊 Resultado

| Métrica | Valor |
|---|---|
| Algoritmo | Random Forest Classifier |
| Acurácia | **95,11%** |
| Total de passageiros | 25.976 |
| Features utilizadas | 22 |
| Árvores (n_estimators) | 100 |

---

## 📁 Estrutura do Projeto

```
projeto-ciencia-de-dados/
│
├── airline_passenger_satisfaction.ipynb   # Notebook principal (análise + modelo)
├── dashboard.html                         # Dashboard interativo para apresentação
├── requirements.txt                       # Dependências Python
└── README.md                              # Este arquivo
```

---

## 🗃 Sobre o Dataset

- **Fonte:** [Kaggle — Airline Passenger Satisfaction](https://www.kaggle.com/datasets/teejmahal20/airline-passenger-satisfaction)
- **Linhas:** 25.976 passageiros
- **Divisão:** 80% treino / 20% teste
- **Alvo:** `satisfaction` → `satisfied` ou `neutral or dissatisfied`

### Variáveis

| Tipo | Variáveis |
|---|---|
| Demográficas | Gender, Age |
| Perfil | Customer Type, Type of Travel, Class |
| Operacionais | Flight Distance, Departure Delay, Arrival Delay |
| Notas de serviço (0–5) | Wi-Fi, Online Boarding, Seat Comfort, Entertainment, Food & Drink, On-board Service, Leg Room, Baggage Handling, Check-in, Inflight Service, Cleanliness, Gate Location, Booking Ease, Timing Convenience |

---

## 🔍 Pipeline do Projeto

```
1. Carregamento dos dados
      ↓
2. Análise de qualidade (missing values)
      ↓
3. Imputação (mediana em Arrival Delay — 0,32% faltantes)
      ↓
4. Label Encoding das variáveis categóricas
      ↓
5. Remoção de colunas irrelevantes (id, Unnamed:0)
      ↓
6. Divisão Treino/Teste (80/20, random_state=42)
      ↓
7. Treinamento — RandomForestClassifier (100 árvores)
      ↓
8. Avaliação — Acurácia: 95,11%
      ↓
9. Serialização do modelo (.pkl via joblib)
```

---

## 🏆 Features Mais Importantes

| # | Feature | Importância |
|---|---|---|
| 1 | Online Boarding | 18,2% |
| 2 | Inflight Wi-Fi Service | 15,3% |
| 3 | Type of Travel | 12,1% |
| 4 | Class | 10,8% |
| 5 | Inflight Entertainment | 9,7% |
| 6 | Seat Comfort | 8,8% |
| 7 | On-board Service | 7,1% |

---

## 💡 Principais Insights

- Passageiros em **classe Business** têm ~69% de satisfação vs. ~19% na classe Eco
- Viagens a **negócios** geram muito mais satisfação (62%) do que viagens pessoais (10%)
- **Clientes fiéis** têm melhor experiência mesmo na classe Eco
- **Atrasos grandes (>60 min)** impactam negativamente a satisfação de forma significativa
- As notas de **Wi-Fi** e **embarque online** são os maiores diferenciadores entre satisfeitos e insatisfeitos

---

## 🚀 Como Executar

```bash
# 1. Clone o repositório
git clone https://github.com/luissardinha/airline-passenger-satisfaction.git
cd airline-passenger-satisfaction

# 2. Instale as dependências
pip install -r requirements.txt

# 3. Execute o notebook
jupyter notebook airline_passenger_satisfaction.ipynb
```

Para visualizar o dashboard, basta abrir `dashboard.html` em qualquer navegador.

---

## 🛠 Tecnologias

- **Python 3.x**
- **Pandas** — manipulação de dados
- **Scikit-learn** — modelo Random Forest
- **Joblib** — serialização do modelo
- **HTML / CSS / JavaScript + Chart.js** — dashboard interativo

---

## 👤 Autor

**Luis Sardinha**  
[luis.sardinha.dev@gmail.com](mailto:luis.sardinha.dev@gmail.com)
