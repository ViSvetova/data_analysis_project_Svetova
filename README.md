# data_analysis_project_Svetova

Для исследовательского проекта был выбран массив фильмов, которые номинировались и побеждали на ежегодной церемонии Оскар в категории "Лучший фильм", начиная с 1929 года, заканчивая последней церемонией.

**Парсинг Данных**

Я парсила датасет с одного из разделов Кинопоиска: *https://www.kinopoisk.ru/lists/movies/oscar-best-film-nominees/?ysclid=lvxq6c75mu335657925*. Там представлен топ из 601 фильма, которые являлись номинантами на кинопремию Оскар за все время существования Академии. Для парсинга использовался silenium и для того, чтобы все работало правильно и крректно отображалось необходимо установить ChromeDriver (или драйвер другого используемого браузера): *https://chromedriver.chromium.org/downloads*

НА ДАННЫЙ МОМЕНТ парсинг разбит на 2 файла: в первом происходит постраничный парсинг фильмов на Кинопоиске, оттуда забираются русское и оригинальное название фильма, год, режиссера и другие характеристики, а также ссылка на этот фильм на сайте. Все эти данные сохраняются в csv файл под названием df_films_pages_1-13. Во втором файле также парсятся данные, но уже находящиеся на внутренних страничках каждого фильма, такие, как бюджет и сборы по миру и США. Эти данные сохраняются в другой csv файл под названием df_films_budget.csv.

**Визуализации**

НА ДАННЫЙ МОМЕНТ  в файле с визуализациями происходит объединение данных из двух csv файлов. В данных остаются пустые ячейки - они не идеальны - я думаю над способом их устранения. 
Представлены такие диаграммы, как топ-10 фильмов из выборки по бюджету, топ-10 фильмов по сборам в мире, топ-10 фильмов по сборам в США. Также на данный момент есть график пересечений топов по сборам и бюджетам (для проверки мысли о том, что чем больше бюджет, тем больше сборы). 

**Дальнейшая работа**
Впоследствии я планирую добавить в датасет статус фильма на оскаре, на основе этих данных будет добавлена еще одна визуализация и, соответственно, вывод о тенденции, которую можно будет проследить по построенным диаграмам и графикам.
В качестве дополнительного признака я выбрала прибыль фильма, которая будет считаться очень просто: сборы - бюджет. 
Гипотеза, которая будет проверяться в этом проекте, звучит следующим образом: правда ли, что чем больше прибыль фильма, тем больше у него будет шансов выиграть заветную статуэтку Оскара.

В разделе с машинным обучением планируется прогнозирование результатов оскара этого года. (или, в виду отсутствия данных, я исключу из выборки фильмы 2023 года и прогнозирование буду ориентировать на уже проведенную премию. заодно можно будет оценить правдивость моей гипотезы).
