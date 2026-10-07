# Credit Scoring — Prediction of Loan Default

Проект по предсказанию дефолта заёмщика на основе исторических данных кредитного бюро.

## 📋 О проекте
Бинарная классификация: предсказать, вернёт ли заёмщик кредит (`loan_status`) 
или уйдёт в дефолт.

## 📊 Данные
- Источник: [Kaggle — Credit Risk Dataset](https://www.kaggle.com/datasets/laotse/credit-risk-dataset)
- ~32 000 записей, 12 признаков
- Целевая переменная: `loan_status` (0 — выплачен, 1 — дефолт)
- Дисбаланс классов: ~78% / ~22%

## 🔍 Ключевые шаги
1. **EDA** — анализ распределений, проверка гипотез, корреляционный анализ
2. **Предобработка** — заполнение пропусков, обработка выбросов, фильтрация
3. **Feature Engineering** — `age_at_first_credit`, `int_rate_residual`, логарифмирование
4. **Модель** — Logistic Regression с `class_weight='balanced'`
5. **Метрики** — ROC-AUC, Precision, Recall, F1

## 📈 Результаты
| Метрика | Значение |
|---|---|
| ROC-AUC | **0.872** |
| Precision (default) | 0.49 |
| Recall (default) | 0.80 |
| F1 (default) | 0.61 |

## 🗂️ Структура проекта
Credit_scoring/
├── main.ipynb # Разведочный анализ + модель
├── requirements.txt # Зависимости
├── .gitignore
└── README.md


## 🚀 Как запустить
```bash
git clone <repo_url>
cd Credit_scoring
python -m venv venv
source venv/bin/activate     # Windows: venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook main.ipynb