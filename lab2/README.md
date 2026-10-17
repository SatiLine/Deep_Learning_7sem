# Лабораторная работа №2. Обучение нейронной сети с нуля

**ФИО:** Горюнова Алина

**Зачётная книжка:** ИЦ-230453

**Вариант:** 3  

## Цель работы
Освоить полный цикл обучения нейронной сети «с нуля» на PyTorch (CPU): подготовить данные через Dataset и DataLoader, корректно разделить их на обучающую и валидационную выборки, реализовать прямой и обратный проход с ручным обновлением параметров без `torch.optim`, сравнить ручной шаг оптимизации со стандартным `torch.optim`, подобрать learning rate и построить кривые обучения, применить регуляризацию (dropout, weight decay, early stopping) и оценить её эффект на валидации, а также оформить воспроизводимый проект.

## Конфигурация варианта 3
- **Датасет:** Fashion-MNIST
- **Архитектура:** 784 → 128 → 64 → 10
- **Активация:** ReLU
- **Стартовый lr:** 0.05

## Датасет
Fashion-MNIST загружается автоматически через `torchvision.datasets.FashionMNIST(root="./data", train=True, download=True)`. Файлы данных в репозиторий не коммитятся (папка `data/` добавлена в `.gitignore`).

## Окружение
Python 3.13  


## Команда запуска
```bash
python -m venv .venv
source .venv/bin/activate          # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install torch torchvision --index-url https://download.pytorch.org/whl/cpu
pip install -r requirements.txt
