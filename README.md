# Тестовое задание Faifly
Для перехода на сайт или к просмотру графика кликните по соостветствующим ссылкам
1. Верстка сайта (+ responsive) ["Tajam Agency"](https://ant-nov.github.io/Tajam%20agency/ "Перейти на сайт")
2. [Bar charts](https://ant-nov.github.io/bar%20charts/index.html "Посмотреть") на html, css и js

На выполнение задания затрачено времени:
- верстка сайта - 8 часов 30 минут;
- отзывчивость сайта - 4 часа 30 минут;
- гистограммы - 2 часа 25 минут.

Папка 'Tajam agency' содержит:
- файл **index.html** - скелет страницы;
- **script.js** - небольшой интеркатив (на экранах шириной меньше 580 пикселей нажатие на кнопку "бургер" открывает навигационное меню;  при нажатии кнопки "play" в секции "our story" появляется видеопреер);
- **папку images** - здесь находятся все изображения, которые были использованы для верстки страницы;
- **папку css** - стили страницы (содержит scss и css файлы);

Папка'bar charts' содержит:
- файл **index.hmtl** скелет страницы;
- **script.js** - логика для отрисовки гистограмм;
- **папку styles** - стили страницы (содержит scss и css файлы).

### Описание

  При создании страницы для именования её составляющих была использованя методология БЭМ ("имя-блока__имя-элемента_имя-модификатора_значение-модификатора"). Страница разделена на 9 блоков, 2 из которых это шапка и подвал, а остальные это тематические секции. Также имеется два контейнера, первый - с макс. шириной 1600px (для того, чтобы на очень большых экранах контент не растянулся на всю ширину монитора), второй - 940px (ширина взята из расстояния между первой и последней направляющей макета).
  
  Стили создавались при помощий препроцессора Sass. Но изначально был подключен файл normalize.css, который обеспечивает лучшую кроссбраузерность стилей html-элементов по умолчанию.
  
  Шрифты были импортированы с сайта "Google Fonts". Для каждого из них был создан свой миксин для экономии времени написания стилей текста в дальнейшем. Также были созданы отдельные переменные для использованых цветов на странице.
  
  Для создания списков (например: навигационное меню шапки) отменялся его стандартный стиль и применялась технология flex-box. Также flex-box был использован для размещения составных подвала сайта, карточек в секции "Our team" и других блоков и элементов страницы. Технология grid применена для отображения логотипов компаний клиентов (секция "news-clients") и работ агенства (секция "work").
  
  В секции с видео, чтобы спрятать видеоплеер за блоком с кнопкой "play" были использованы настройки позиционирования. Плееру было задано абсолютное позиционирование и низкий z-индекс, тогда как родительскому - относительное позиционирования с большим z-индексом.
  
  Для маленьких экранов был убран навигационный список из шапки сайта, вместо этого добавлена кнопка "бургер", нажатие которой разворачивает этот самый список на ширину и высоту всего дисплея.
  
  Для стилизации страницы под разные размеры экранов были применены медиа запросы с такими условиями максимальной ширины экрана: 580px 800px и 1000px. Выбраны такие брейкпоинты, потому что на данных размерах экранов верстка начинала "съезжать".
  
  При создании гисторгамм создано один родительский блок и три дочерних(шкала значений, названия столбцов (индексы) и блок с отображенными данными). Данные отрисовывались при помощий технологии "grid". Каждый столбец занимал определенное количество ячеек сетки. Это было реализовано уже при помощи javascript. На основе максимального значения в массиве определялась высота блока с гистограмамми (к максимальному значению добавлено 2, чтобы самый высокий столбец не упирался в верх блока). Ширина рассчитывалась на основе количества значений в массиве (количество умножено на 2, чтобы родительский блок смог уместить столбцы через одну ячейку). Отрисовка реализована с помощью цикла for с кол-вом итераций, которая равна кол-ву значений. Каждую итерацию создавался новый блок, которому задавались стили размещения в сетке (поскольку для размещения блоков в сетке используются границы ячеек, а не сами ячейки, то от значения высоты блока (макс. значение в массиве + 2), к которому ещё добавлена 1 (получаем кол-во границ ячеек в столбце) отнималось значение из массива - это была верхняя точка столбца, а нижней - высота блока + 1). В конце каждой итерации столбец присоединялся к главному блоку(метод "append"). Шкала и блок с индексами также создавались при помощи "grid".   
