<div align="center">

# findtits 🎯

**Учебный проект: кастомная YOLO11 модель для детекции женской груди на фото**

[![Python](https://img.shields.io/badge/Python-3.8+-blue?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![YOLO11](https://img.shields.io/badge/YOLO-11-00BFFF?style=for-the-badge)](https://docs.ultralytics.com/)
[![Ultralytics](https://img.shields.io/badge/Ultralytics-8.x-00CC66?style=for-the-badge)](https://github.com/ultralytics/ultralytics)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

</div>

---

## 📌 О проекте

Модель **YOLO11n** (nano), обученная на **367 фотографиях** реальных женщин в различных позах, разных рас, в разной обстановке. Детектирует один класс — **грудь** (женская, обнажённая).

Основная цель проекта — учебная: показать полный цикл обучения YOLO на собственном датасете с нуля:

1. Сбор и разметка данных (367 изображений)
2. Подготовка датасета в формате YOLO
3. Обучение модели (YOLO11nano)
4. Инференс и валидация

---

## 🚀 Быстрый старт

```bash
# Установка
pip install ultralytics

# Инференс (предобученная модель)
from ultralytics import YOLO
model = YOLO("titsyolo11n.pt")
results = model("image.jpg")
results[0].show()
```

---

## 📂 Файлы

| Файл | Описание |
|------|----------|
| `titsyolo11n.pt` | Предобученная модель YOLO11n (веса) |

---

## 🧠 Обучение

```python
from ultralytics import YOLO

model = YOLO("yolo11n.pt")  # предобученная baseline
model.train(
    data="dataset.yaml",
    epochs=100,
    imgsz=640,
    batch=16,
    name="tits_yolo11n",
)
```

---

## 📊 Характеристики модели

| Параметр | Значение |
|----------|:--------:|
| Архитектура | YOLO11nano |
| Классов | 1 (breast) |
| Датасет | 367 изображений (обнажённая женская грудь, в репозитории отсутствует) |
| Размер входа | 640×640 |
| Формат весов | PyTorch (.pt) |

---

## ⚠️ Замечания

- Проект создан в **учебных целях** для демонстрации пайплайна тренировки кастомной YOLO-модели
- Модель обучена на изображениях обнажённой женской груди (NSFW-контент, в репозитории отсутствует)
- Малый датасет (367 фото) не подходит для production-использования
- Для серьёзных задач необходимы тысячи размеченных изображений

---

<div align="center">

**Учебный проект для освоения YOLO и computer vision**

</div>
