# Алгоритм отсечения отрезков

## Описание задачи

Этот проект реализует два алгоритма отсечения отрезков:

1. **Алгоритм отсечения с использованием Midpoint Clip (для прямоугольных окон)**
2. **Алгоритм отсечения отрезков многоугольником по методу Кируса-Бека**

Оба алгоритма используют графическое отображение, что позволяет наглядно увидеть результат работы алгоритма в реальном времени.

## Установка

1. Скачайте файлы проекта на свой компьютер.
2. Откройте любой текстовый редактор или IDE (например, VSCode или Sublime Text) для редактирования HTML и JS файлов.
3. Для запуска откройте HTML файлы в вашем браузере.

Не требуются дополнительные установки, так как проект использует стандартные технологии HTML, CSS и JavaScript.

## Использование

### 1. Алгоритм отсечения отрезков по прямоугольному окну

В этом режиме пользователю предлагается ввести отрезки и окно (прямоугольник), через которое будет выполнено отсечение. Все отрезки, которые выходят за пределы этого окна, будут обрезаны и отображены в виде зеленых отрезков.

#### Как использовать:
- Введите координаты отрезков в поле **Отрезки** в формате `x1 y1 x2 y2`.
- Укажите координаты прямоугольного окна в поле **Окно** в формате `Xmin Ymin Xmax Ymax`.
- Нажмите кнопку **Отобразить**, чтобы увидеть результат.

### 2. Алгоритм Кируса-Бека

Этот алгоритм позволяет отсекать отрезки, пересекающие многоугольник. Многоугольник вводится как список координат его вершин, а отрезки — как набор координат их концов. Алгоритм будет отсекать отрезки, которые выходят за границы многоугольника.

#### Как использовать:
- Введите вершины многоугольника в поле **Многоугольник** в формате `x y` для каждой вершины на новой строке.
- Введите координаты отрезков в поле **Отрезки** в формате `x1 y1 x2 y2`.
- Нажмите кнопку **Отобразить**, чтобы увидеть результат.

## Функции

### 1. **Функции для отрисовки**
   - **drawGrid()** — рисует сетку и оси координат.
   - **toCanvasX(x)** и **toCanvasY(y)** — преобразуют мировые координаты в координаты холста.
   - **drawRectangle(xmin, ymin, xmax, ymax)** — рисует прямоугольник, который представляет окно для отсечения.
   - **drawSegment(x1, y1, x2, y2, color)** — рисует отрезок с заданными координатами и цветом.

### 2. **Алгоритм Midpoint Clip**
   - **midpointClip(x1, y1, x2, y2, xmin, ymin, xmax, ymax)** — отсечение отрезка, который находится вне или частично внутри заданного прямоугольного окна. Алгоритм рекурсивно делит отрезок пополам, проверяя его попадание в окно.

### 3. **Алгоритм Кируса-Бека**
   - **getNormal(p1, p2)** — вычисляет нормаль к ребру многоугольника, которая используется для вычисления пересечений с отрезками.
   - **dotProduct(v1, v2)** — вычисляет скалярное произведение двух векторов.
   - **cyrusBeckClip(segment, polygon)** — отсечение отрезка по многоугольнику с помощью алгоритма Кируса-Бека.

## Пример работы

- Введите несколько отрезков, например:  
  ```
  -20 -20 30 30
  -40 50 60 -60
  -10 10 40 40
  ```
- Введите окно:  
  ```
  -50 -50 50 50
  ```
- Нажмите "Отобразить" для выполнения отсечения и отображения результатов.

## Заключение

Этот проект демонстрирует работу двух популярных алгоритмов отсечения отрезков. Он может быть полезен для обучения или для использования в графических приложениях, которые требуют обработки и визуализации геометрических объектов.
