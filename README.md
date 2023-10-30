<h1 align="center">Baltic Alfa Hack</h1>

На хакатоне, проходившем 6-8 октября в БФУ им. И. Канта в Калининграде, при поддержке Альфа Банка, перед участниками стояла задача оптимизации работы с корпоративными клиентами банка на основе больших данных.

В данном репозитории представлено решение команды pip, занявшей 2 место в соревновании. В репозитории находитися 3 папки:
* solution, содержащая решение команды;
* drafts, в которой находится личная доработка модели, для достижения максимального значения метрики roc auc;
* data, должна содержать датасеты для обучения и валидации модели, но пустая, поскольку датасеты, предоставленные банком, размещать не разрешено.

# Постановка задачи
На клиентских данных для юридических лиц необходимо спрогнозировать отток клиентов из банка. Под оттоком подразумевается прекращение финансовой активности клиента или закрытие РКО (Расчетно-кассового обслуживания)

# Первый этап

Изучить данные, обработать и визуализировать

Предобработать данные
Отобрать наиболее важные факторы, проанализировать на наличие зависимостей между ними и визуализировать
Выполнить задачу классификации клиентов:

Построить модель, прогнозирующую отток клиента из банка
Оценить точность предсказания по метрике ROC-AUC на открытой выборке
Набор данных представлял собой таблицу со 100 факторами и содержал информацию о клиентах и их активностях внутри банка.

<code>300000 записей - обучающая выборка</code>

<code>100000 записей - тестовая выборка</code>

Целевая переменная:

Прекразение финансовой активности клиента (Y1) или закрытие РКО (Y2).
Итоговый таргет Y = max(Y1,Y2).
Оценка решения на первом этапе производилась только по метрике ROC-AUC.

# Второй этап
## Задачи:

* Доработать модель, создать репозитрий с документацией и поспроизводимым решением.
* Сформулировать базнес-инсайты по результатам визуализации и моделировани.
* Определить наиболее интерпретируемые для бизнеса метрики, с помощью которых оценить модель.
* Презентовать свое решение и результаты перед членами жюри: подготовить выступление на 5-7 минут.

## В презентации решения:

* Описать подход к решению задачи и полученные результаты.
* Подготовить визуализацию данных.
* На основе построенной модели сформулировать полезные и понятные для бизнеса выводы.
* Критерии, по которым оценивали решения в финале:

## Техническая сторона:

* Значение метрики ROC-AUC.
* Воспроизводимость и читабельность кода.
* Широта подхода: использование различных ML-алгоритмов, метрик качества модели.

## Бизнес-сторона:
* Качество и обоснованность инсайтов (выводов), полученных по результатам создания модели.
* Оригинальность подхода и защиты решения.
* Качество визуального оформления и логика презентации.

Наши решения оценивались по нескольким критериям командой экспертов Альфа-Банка и БФУ.


<h1 align="center">Модель</h1>

## Установка:

* Установить python, версии 3.11.3 или выше.
* Установить библиотеки, указанные в requirements.txt: <code>pip install -r requirements.txt</code>
* По возможности, добавить в папку data датасеты train.parquet, test.parquet.
* Запустить любой ноутбук и выполнить все ячейки по очереди, на выходе получится csv файл.
