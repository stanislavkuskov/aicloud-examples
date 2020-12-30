# Примеры работы с сервисом AI Cloud от SberCloud

В репозитории приведены примеры использования сервиса AI Cloud для решения ML задач.

## Model Training (обучение моделей)

Базовые примеры размещены в директории [quick-start](quick-start). Они иллюстрируют процесс обучения моделей одним из указанных способов:

1. Напрямую из Jupyter Server, подключенного к GPU.
   
   Пример доступен по ссылке: [Обучение модели в ноутбуке с GPU](quick-start/notebooks_gpu).

2. Посредством отправки задачи обучения на кластер.

   [Обучение модели через Training Job API на TensorFlow 1](quick-start/job_launch).

   [Обучение модели через Training Job API на TensorFlow 2](quick-start/job_launch_tf2).

У каждого из этих способов обучения есть свои преимущества. Так при отправке задачи обучения на кластер можно задействовать 1000+ GPU, в случае обучения напрямую из Jupyter Server максимальное количество выделенных GPU — 16. Однако обучение из Jupyter Server на выделенных GPU проще и удобнее для пользователя (не требуется знакомство с библиотекой Horovod). Есть некоторые отличия в плане тарификации. При обучении из Jupyter Server на выделенных GPU взимается оплата до удаления сервера, даже если он не используется. При отправке задачи обучения на кластер пользователь платит за фактическое время исполнения задачи: от старта до окончания обучения.

Дополнительные примеры обучения моделей, доступные для использования:

 * В папке [pytorch-example](pytorch-example) рассмотрен пример задачи распределенного обучения Pytorch-модели с двумя типами запуска: `horovod` (стандартный способ) и дополнительный тип запуска `pytorch` (он же `Pytorch.Distributed`).


## Препроцессинг данных

* Загрузка/выгрузка данных на S3 в [стартовом примере](quick-start).
* [Работа с Rapids](rapids), библиотекой, ускоряющей обработку датасетов на GPU.
* С использованием ресурсов кластера Spark. В ноутбуке `Spark_preproc.ipynb` поясняется, как создать SparkSession и SparkContext, загрузить данные на S3 и выполнить препроцессинг этих данных.

## AutoML

В [стартовом ноутбуке для AutoML](automl) содержится объяснение, как обновить библиотеки `autowoe` и `lightautoml`, а также как загрузить туториалы из открытых репозиториев на GitHub для знакомства с функционалом библиотек.