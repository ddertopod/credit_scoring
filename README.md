# Проект машинного обучения для предсказания одобрения кредита

Этот проект реализует модель машинного обучения для классификации заявок на получение кредита. В основе модели лежит логистическая регрессия с предобработкой данных.

## Описание проекта

- Используются все доступные признаки из исходного набора данных.
- Добавляется новый признак `AssetHealth` (NetWorth / TotalAssets).
- Признаки `AnnualIncome`, `NetWorth`, `TotalAssets` удаляются как избыточные или сильно коррелирующие.
- Категориальные признаки преобразуются с помощью OneHotEncoding.
- Для модели используется `LogisticRegression` из библиотеки scikit-learn.
- Результаты оцениваются с помощью отчёта классификации.

## Структура проекта

```
loan_ml/
├── config.py              # Настройки проекта
├── data_loader.py         # Загрузка и разбиение данных
├── features.py            # Генерация и преобразование признаков
├── model.py               # Построение модели
├── evaluate.py            # Оценка результатов модели
├── main.py                # Точка входа
├── requirements.txt       # Зависимости проекта
├── README.md              # Документация проекта
```

## Установка

1. Скопируйте проект в рабочую директорию.
2. Скачайте файл `Loan.csv` с Kaggle (https://www.kaggle.com/datasets/lorenzozoppelletto/financial-risk-for-loan-approval?select=Loan.csv). 
3. Добавьте файл `Loan.csv` в корень проекта.
4. Установите зависимости:

```
pip install -r requirements.txt
```

## Запуск

```
python main.py
```

## Ожидаемый результат

После запуска будет выведен отчёт классификации с основными метриками: точность, полнота, F1-мера.

## Примечания

- При расчёте `AssetHealth` используется деление на `TotalAssets + 1` для избежания деления на ноль.