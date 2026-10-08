# Лабораторная работа №1. Основы машинного обучения и предобработка данных

**Вариант 3:** Wine Quality — многоклассовая классификация (определение качества вина).

## Цель работы
Получить практический опыт предобработки данных, обучения базовых моделей машинного обучения
(логистическая регрессия, KNN с k = 5, наивный Байес) и оценки их качества на реальном датасете:
кросс-валидация (cv = 5), подбор гиперпараметров через GridSearchCV (3 комбинации), анализ ошибок,
бонус — ансамбли и абляция признаков.

## Датасет
Wine Quality, UCI Machine Learning Repository, ID 186:
https://archive.ics.uci.edu/dataset/186/wine+quality (лицензия CC BY 4.0).
Файлы данных в репозиторий не коммитятся (папка `data/` в `.gitignore`).
Ноутбук сам скачивает архив один раз (`data/winequality-red.csv`, `data/winequality-white.csv`).
Если автоматическая загрузка не сработала, скачайте архив по ссылке
https://archive.ics.uci.edu/static/public/186/wine+quality.zip и положите оба csv-файла в папку `data/`.

## Окружение
* Python 3.12
* Пакеты (версии зафиксированы в `requirements.txt`): numpy 2.5.3, pandas 3.0.6, scikit-learn 1.9.1, matplotlib 3.11.2, scipy 1.18.1
* Для запуска ноутбука дополнительно нужен JupyterLab (на результаты не влияет)

## Команда запуска
```bash
python3.12 -m venv .venv
source .venv/bin/activate          # Windows: .venv\Scripts\activate
pip install -r requirements.txt
pip install jupyterlab
jupyter lab                        # открыть lab1_3_ФАМИЛИЯ.ipynb и выполнить все ячейки (Run All)
```

## Воспроизводимость
Номер варианта `VARIANT = 3`, `SEED = 3`: seed задан в начале ноутбука, `random_state = 3` передаётся в разбиение,
модели, кросс-валидацию и GridSearchCV. Предобработка собрана в sklearn-пайплайн (`fit` только на обучающей выборке).

## Структура репозитория
```
lab1_3_ФАМИЛИЯ.ipynb   основной ноутбук (код, графики, выводы)
requirements.txt       зафиксированные версии пакетов
README.md              описание работы
.gitignore             исключает data/ и служебные файлы
data/                  (не коммитится) скачиваемые данные
```
