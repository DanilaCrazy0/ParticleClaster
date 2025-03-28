# README: Кластеризация сцинтилляций частиц

## Описание задачи

Данный проект посвящен исследованию и кластеризации сигналов от сцинтилляций частиц. Целью является разделение частиц на три кластера на основе их характеристик. Исходные данные представляют собой временные ряды сигналов, зарегистрированных детектором.

## Исходные данные

- Описание данных: [Kaggle Competition Overview](https://www.kaggle.com/competitions/signal-types/overview)
- Дополнительная информация о сцинтилляциях и методах обработки: PDF-файл в репозитории

## Методы кластеризации

В проекте реализованы три подхода к кластеризации:

### 1. Baseline методы (`claster_baselines.ipynb`)
- **DBSCAN**: Алгоритм кластеризации на основе плотности.
- **K-means**: Кластеризация на 3 кластера.
- **Agglomerative Clustering**: Иерархическая кластеризация.
- **Результаты**: Максимальная accuracy на итоговом тесте - 0.3.

### 2. Статистический метод (`statistic_method.ipynb`)
- **Основная идея**: Использование метода наименьших квадратов (МНК) для определения двух линий, описывающих типы частиц (верхний и нижний пучок). Кластеризация основана на отклонении данных от этих линий.
- **Результаты**: Accuracy - 0.79.

### 3. Физический метод (`physics_metod.ipynb`)
- **Основная идея**: Использование физических характеристик сигналов (площадь под кривой, амплитуда, PSD - отношение короткого и длинного интегралов) для кластеризации.
- **Результаты**: Accuracy - 0.86.

## Результаты

| Метод               | Accuracy |
|---------------------|----------|
| Baseline (K-means)  | 0.30     |
| Статистический      | 0.79     |
| Физический          | 0.86     |

Физический метод показал наилучшие результаты благодаря учету физических особенностей сигналов сцинтилляций.

## Визуализация

Каждый метод включает визуализацию результатов кластеризации с помощью scatter-plot, где:
- По оси X: Площадь под кривой сигнала (`s`).
- По оси Y: Амплитуда сигнала (`a`).
- Цвет точек: Кластер.

## Заключение

Наилучшие результаты показал физический метод, учитывающий PSD и другие физические характеристики сигналов. Это подчеркивает важность использования предметной области при решении задач кластеризации.
