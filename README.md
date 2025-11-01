# Проєкт Business Forecasting

## 1. Встановлення потрібних програм

1. Переконайтесь, що на комп’ютері встановлено **Python 3.10** або новіший. Перевірити версію можна командою:
   ```bash
   python --version
   ```
2. Оновіть менеджер пакетів `pip` і встановіть необхідні бібліотеки (потрібно виконати обидві команди в терміналі/PowerShell):
   ```bash
   python -m pip install --upgrade pip
   py -3.12 -m pip install pandas
   py -3.12 -m pip install numpy
   py -3.12 -m pip install statsmodels
   py -3.12 -m pip install scikit-learn
   py -3.12 -m pip install xgboost
   py -3.12 -m pip install nbformat
   py -3.12 -m pip install jupyter
   ```

Ці пакети забезпечують роботу нашого пайплайну та ноутбуків.

## 2. Структура папки

У корені репозиторію мають лежати:
- вихідні файли з даними: `forecast_of_market_dataset.csv`, `forecast_revenue_dataset.csv`, `dataset_pcs.csv`;
- ноутбуки: `Model market.ipynb`, `Model money.ipynb`, `Model pcs.ipynb`;
- модуль з пайплайном `three_phase_linear.py` та генератор ноутбуків `build_notebooks.py`.

## 3. Запуск Jupyter Notebook

1. Відкрийте термінал (або PowerShell) у папці проєкту `business_forecasting`.
2. Запустіть середовище Jupyter командою:
   ```bash
   jupyter notebook
   ```
3. У браузері відкриється список файлів. Запускайте потрібний ноутбук:
   - `Model market.ipynb` — прогноз ринку за `product_group_id` (місячні дані).
   - `Model money.ipynb` — прогноз виручки за `category_id` (місячні дані).
   - `Model pcs.ipynb` — прогноз продажів PCS за `sku_id` (тижневі дані).
4. У кожному ноутбуку виконуйте комірки послідовно згори донизу (комбінація клавіш **Shift+Enter**).

Після завершення обчислень у корені репозиторію з’являться CSV-файли з прогнозами:
- `market_three_phase_forecast.csv`
- `money_three_phase_forecast.csv`
- `pcs_three_phase_forecast.csv`

У цих таблицях будуть **лише майбутні періоди**, для яких модель сформувала прогноз.

## 4. Корисні поради

- Перед повторним запуском переконайтесь, що CSV-файли з прогнозом закриті в Excel або інших програмах. Інакше запис може завершитись помилкою `Permission denied`.
- Якщо потрібно працювати лише з одним розрізом, достатньо залишити відповідний ноутбук, файл з даними та модуль `three_phase_linear.py`.
- У разі питань звертайтесь до викладача або наставника — всі скрипти написані так, аби їх можна було запускати «в один клік» без додаткового налаштування. 
