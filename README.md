# Insilico Medicine

Задача двоичной классификации для проверки общих навыков работы с данными.

Задание заключается в построении бинарного классификатора на представленном наборе данных. Кроме целевой метрики на тесте, будет оцениваться подход к решению задачи, а также код. Приватной тестовой выборки нет, метрика на публичном тесте является окончательной.

Основные критерии оценки
- Целевая метрика на тестовом множестве (ROC-AUC)
- Полнота анализа данных, использование графиков
- Препроцессинг/постпроцессинг
- Выбор моделей, настройка гиперпараметров, метод валидации
- Использование нейронных сетей
- Общая сложность решения
- Прозрачность и структура кода, комментарии

# Основные решения

Препроцессинг заключался, в исключении значений NaN, +-inf из датасета, путем удаления столбцов (если количество NaN больше на 5%, чем строк тренировочного и тестового датасета), а также строк. P.S. Способ о сохранении всех строк (описан в коде), будет произведён позже если останется время после докера!

В качестве построения нейронной сети, взял модель Keras Sequental API. В Jupiter Notebook, есть раздел, описывающий подбор параметров, размер нейронной сети и количества эпох. При выборе параметров, опирался на статьи, документацию и эксперименты с параметрами, чтобы добиться лучшего значения (время - AUC).

![ROC curve](https://github.com/VladicNaAmure/Insilico-Medicine/raw/master/images/ROC.png)

При построении ROC curve, параметры предсказания из результатов задания (sample_submission.csv), брался за истинные значения и сравнивался с моими значениями.

# Сравнение моделей для задач бинарной классификации

Сравнение ROC-AUC и F1 score, для разных моделей задач бинарной классификации.

![Сравнение моделей](https://github.com/VladicNaAmure/Insilico-Medicine/raw/master/images/models_compare.png)

P.S. Если быстро разберусь с докером, возможно проведу эксперимент на обучение еще одной сложной модели для бинарной классификации.

Визуализация некоторых параметров из истории обучения модели keras.

![accuracy_loss](https://github.com/VladicNaAmure/Insilico-Medicine/raw/master/images/accuracy_loss.png)

![f1_score](https://github.com/VladicNaAmure/Insilico-Medicine/raw/master/images/f1_score.png)
