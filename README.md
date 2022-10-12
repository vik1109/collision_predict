# Прогнозирование заказов такси

**Цель проекта:** Нужно создать систему, которая могла бы оценить риск ДТП по выбранному маршруту движения. Под риском понимается вероятность ДТП с любым повреждением транспортного средства. Как только водитель забронировал автомобиль, сел за руль и выбрал маршрут, система должна оценить уровень риска. Если уровень риска высок, водитель увидит предупреждение и рекомендации по маршруту.

Идея создания такой системы находится в стадии предварительного обсуждения и проработки. Чёткого алгоритма работы и подобных решений на рынке ещё не существует. Текущая задача — понять, возможно ли предсказывать ДТП, опираясь на исторические данные одного из регионов.

**Результат проекта:** На основании предоставленных данных невозможно построение системы оценки риска попасть в ДТП. Данные отображают только одну категорию - "Водители попавшие в ДТП", второй категории - "Водители не попавшие в ДТП" нет совсем. Наша система обучаясь на данных в которых 100% дисбаланс классов учится предсказывать, что все поездки закончатся ДТП.

Если же рассматривать таргет, который предложил заказчик - то мы по нему можем предсказать только виновен ли водитель в ДТП или нет. Столбец at_fault именно это и сигнализирует. Однако самый важный признак по которому строиться хорошее предсказание это сведенья о нарушении, которые мы получаем из компетентных органов вероятно вместе с заключением о виновности или невиновности конкретного лица. В результате система предсказания виновности в ДТП в целом теряет смысл, т.к. нам не нужно предсказывать виновного, в акте и так это уже будет написано.

Для создания модели, которая бы могла предсказывать ДТП, нам дополнительно нужны данные о поездках без ДТП, иначе построить адекватную систему предсказаний не возможно.

**Используемые инструменты:** Pandas, Matplotlib, sqlalchemy, sklearn, catboost, optuna, lightGBM, numpy