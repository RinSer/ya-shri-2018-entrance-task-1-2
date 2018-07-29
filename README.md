# Задание 1 — найди ошибки

# Moё решение:

## 1) При первом старте обнаружил белый экран и ошибку в консоли о неправильном импорте зависимостей в файле index.js. Сразу же исправил её, добавив фигурные скобки вокруг названия импортируемой функции initMap.

## 2) Начал разбираться, почему не видно карту. В панели разработчика увидел, что высота родительского элемента равна нулю. Исправил, добавив в стиль элемента с идентификатором map высоту и ширину, равные высоте и ширине видимой области экрана.

## 3) Стал разбираться с API yandex maps. В файле map.js убрал строчку objectManager.clusters.options.set('preset', 'islands#greenClusterIcons'), чтобы по кластеру было видно, что в нём есть неактивные станции и добавил строчку myMap.geoObjects.add(objectManager), чтобы данные о базовых станциях добавились на карту.

## 4) Так и не увидев на экране базовых станций, нашёл в файле mapper.js классическую ошибку с перепутанными широтой и долготой.

## 5) Решил баг с открытием и закрытием попапов деталей станций, изменив в файле details.js декларации анонимных функций, передаваемых как колбеки в build и clear на обычную нотацию function(), чтобы scope переменной this соответствовал самой функции. Тоже классика (:

## 6) Поправил отображение графиков: в файле chart.js в опциях создаваемого графика изменил максимально отображаемое значение по оси ординат с 0 на 10 (yAxes: [{ ticks: { beginAtZero: true, max: 10 } }]).

## Запуск

```
npm i
npm start
```

При каждом запуске тестовые данные генерируются заново случайным образом.
