# Обучение нейронной сети, формирующей эмбеддинги изображений для распознавания места
Этот проект был сделан за 2 недели, во время летней школы по искуственному интеллекту от AIRI. 

Мы использовали NetVlad для
решения задачи Place Recognition.
В процессе решения было
подготовлено несколько
датасетов, рассмотрены разные
архитектуры модели, а так же
применён метод Skip Connection,
показавший существенный
прирост метрик качества.
## Данные
Для решения задачи Visual Place
Recognition в рамках данной
работы был собран датасет из
фотографий аудиторий и мест,
знакомых всем участникам
летней школы AIRI. Собранный
датасет состоит из 851
изображения. В датасете
присутствуют фотографии 21-го
места.
Также был собран датасет из 4164
изображений 100 различных
мест, являющийся
подмножеством датасета Google
Landmarks.
## Методология
Базовой архитектурой в нашей
модели является NetVLAD. Это
модель интеллектуального
пуллинга локальных признаков
изображения, извлекаемых с
помощью предобученного на
задаче классификации feature
extractor'а.
Для улучшения протекания градиентов через feature extractor мы
предлагаем конкатенировать его выходное признаковое
пространство с выходом NetVLAD пуллинга. Также, для
уменьшения размерности выходного эмбеддинга применяется
полносвязный слой. Данный подход мы назвали ConcatNetVLAD.
## Результаты
Мы сравнили наш метод с базовой моделью NetVLAD и с
обученным с помощью triplet loss ResNet'ом. Подход
ConcatNetVLAD показал улучшенную сходимость, как видно на
графиках лосса моделей.
## Заключение
Благодаря добавлению skip connection, аналогичному
предложенному в модели ResNet, было получено существенное
улучшение сходимости модели и метрик качества для задачи Visual
Place Recognition (VPR).
