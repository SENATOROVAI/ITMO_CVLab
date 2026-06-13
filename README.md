# Computer Vision — лабораторные работы (ITMO)

Четыре практические работы по компьютерному зрению, выполненные на Python в Jupyter. Решения сделаны в **двух независимых вариантах** (`Вариант_1` и `Вариант_2`): один и тот же набор задач решён по-разному — другие изображения, параметры и структура кода.

## Технологический стек

![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-cv2-5C3EE8?logo=opencv&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?logo=numpy&logoColor=white)
![scikit-image](https://img.shields.io/badge/scikit--image-F7931E)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)

- **Python 3** + **Jupyter Notebook** — среда выполнения.
- **OpenCV (`cv2`)** — основная библиотека: пороги, морфология, Хаф, SIFT/ORB, каскады Хаара.
- **NumPy** — векторные операции над изображениями.
- **scikit-image** — энтропия текстуры и преобразование Хафа (альтернатива OpenCV).
- **Matplotlib** — вывод изображений внутри ноутбука (`pa_utils.ShowImages`).

## Задачи и решения

| № | Задача | Что реализовано |
|---|--------|-----------------|
| **PA1** | Сегментация изображений | Бинаризация (одиночный/двойной/Оцу/адаптивный порог), сегментация по Веберу и по цвету кожи, хроматическая сегментация в Lab и HSV + `k`-means, текстурная сегментация по энтропии (и по локальному СКО). |
| **PA2** | Преобразование Хафа | Поиск прямых и окружностей на нескольких изображениях, классический и вероятностный варианты, двумя библиотеками — OpenCV и scikit-image. |
| **PA3** | Детекторы особых точек | Детекторы SIFT и ORB, сопоставление дескрипторов (`BFMatcher`, `knn` + ratio-тест Лоу), оценка гомографии через RANSAC. |
| **PA4** | Детекция лиц (Виола–Джонс) | Каскады Хаара: поиск лиц, затем глаз и рта в области интереса (ROI), покадровая обработка видео. |

Каждый ноутбук содержит выполненные секции **Self-work**, ответы на контрольные вопросы и заключение на русском языке.

## Структура

```
Вариант_1/  и  Вариант_2/
└── PAx_Python_CV_ITMO/
    ├── pax.ipynb     # ноутбук с решением и выводами
    ├── pax.pdf       # версия для сдачи
    ├── pa_utils.py   # вспомогательные функции (отображение, морфология)
    └── images/       # исходные данные (+ pano/ у PA3, haarcascades/ у PA4)
```

## Запуск

```bash
pip install opencv-python numpy scikit-image matplotlib jupyter
jupyter notebook                      # открыть нужный pax.ipynb
# либо экспорт в PDF:
jupyter nbconvert --to webpdf pax.ipynb
```
