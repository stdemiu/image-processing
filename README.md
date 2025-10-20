Набор ноутбуков и скриптов по базовым операциям цифровой обработки изображений: арифметика и геометрия, автоконтраст, выравнивание гистограммы, цветовые преобразования, свёртки и фильтры (box, медианный, Гаусс), повышение резкости, а также иллюстрация теоремы о свёртке и фрагменты JPEG-пайплайна.

# Структура проекта
```perl
IMAGE_PROCESSING/
├─ 2-image-manipulation/               # Базовые операции и задания раздела 2.x
│  └─ ... (ноутбуки и изображения)
├─ 3-color-manipulation/               # Контраст, гистограммы, цвет
│  ├─ autocontrast/
│  │  ├─ autocontrast.ipynb
│  │  ├─ image.jpg                     # исходное
│  │  ├─ image-gray.png                # серый
│  │  ├─ image-low-contrast.png        # низкий контраст
│  │  ├─ image-high-contrast.png       # высокий контраст (линейный)
│  │  └─ high-contrast-my.png          # полученный результат
│  ├─ color-auto/
│  │  ├─ color-auto.ipynb
│  │  ├─ image.jpg
│  │  └─ image-color-contrast.png
│  ├─ gray-world/
│  │  ├─ gray-world.ipynb
│  │  ├─ image.jpg
│  │  └─ grey.jpg / grey-world.ipynb   # результат "серый мир"
│  └─ histo/
│     ├─ histo.ipynb
│     ├─ image.jpg
│     ├─ my-landscape.png              # низкоконтрастный аналог
│     ├─ my-landscape-histeq.png       # гист. выравнивание результата
│     └─ landscape-my.png              # проверочный вывод
├─ 4-cnn/                              # Свёртки и фильтры
│  ├─ gauus/                           # (gauss)
│  │  ├─ cnn.ipynb
│  │  ├─ image.png
│  │  ├─ my-box.png
│  │  ├─ gauss-my.png
│  │  └─ sharp-my.png
│  └─ median/
│     ├─ median.ipynb
│     ├─ image.png
│     └─ median-my.png
└─ 5-fourier/
   ├─ a-mirrored.png
   ├─ a-gauss.png
   └─ image-gray.png
```

# Содержимое разделов
## 3-color-manipulation
### autocontrast/

autocontrast.ipynb — линейное растяжение контраста серого изображения: вычисление min/max, нормализация в [0, 255], проверка гистограммы.

### histo/

histo.ipynb — построение гистограммы яркости и выравнивание гистограммы (histogram equalization) через CDF.

На выходе: my-landscape.png (искусственно низкоконтрастный вариант) и my-landscape-histeq.png (после выравнивания).

### gray-world/

gray-world.ipynb — реализация алгоритма Grey World (белый баланс): разложение на RGB, усреднение каналов, нормировка и обратная сборка.

### color-auto/

color-auto.ipynb — устойчивый цветной автоконтраст (работа в цветовых компонентах YUV/Y′UV или подобном пространстве): контраст усиливается на яркостном канале без «перекраски» оттенков.

## 4-cnn (Convolution & Filtering)

### gauus/ (Gauss)

cnn.ipynb — генерация гауссова ядра (по σ), box-фильтр, гаусс-фильтрация свёрткой, повышение резкости (unsharp/sharpen kernel).

Файлы: my-box.png, gauss-my.png, sharp-my.png.

### median/

median.ipynb — реализация медианного фильтра «в лоб» (скользящее окно, медиана по окну) и сравнение с эталоном.

# 5-fourier

Демонстрация теоремы о свёртке (свертка ↔ умножение спектров), построение гаусса в пространственной/частотной области.

Несколько изображений для иллюстрации промежуточных шагов (a-mirrored.png, a-gauss.png).

