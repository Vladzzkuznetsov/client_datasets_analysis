# Analysis_of_client_cash_data
Проведен анализ полученных данных о платежах клиентов
#### Примененные инструменты
- Сводные таблицы
- KMeans кластеризация
- Анализ корреляционных зависимостей и зависимостей fig
- Анализ log_loss — scikit-learn
- Анализ RandomForestClassifier — scikit-learn
- Подобраны и оценены параметры работы модели с помощью метрик accuracy_score, precision_score, recall_score, f1_score, roc_auc_score
- Применен алгоримт анализа выживаемости пациентов из библиотеки lifelines

<body>
  <p><img src="https://user-images.githubusercontent.com/111303182/201114797-cac5fd13-14b9-47ef-8cdb-a7fcde62ec7e.png"></p>
</body>

### Выводы и Результаты

Исследовательский анализ данных

- Клиенты у которых метод оплаты "Electronic check" склонны к оттоку
- phone_service  при наличии у клиента сервиса отток становится вероятнее (он есть у большинства клиентов в принципе)

Меньше отток среди тех, кто:

- SeniorCitizen: клиент пожилой гражданин
- Partner: у клиента есть партнер
- PaperlessBilling: клиент имеет безбумажный биллинг
- MonthlyCharges: клиенты заплатившие больше
- InternetService: без оптоволокна
- OnlineSecurity: если у клиента есть защита данных он уходит реже
- OnlineBackup: если у клиента есть онлайн-резервное копирование он уходит реже
- DeviceProtection: если у клиента есть защита устройства он уходит реже
- TechSupport: если у клиента есть техническая поддержка он уходит реже
- streaming_tv_No_service: почти всегда означает что клиент останется

- StreamingMovies: уходит чуть чуть реже (если есть фильмы то и телевидение есть)
- Contract: те к кого длительные контракты тот меньше уходит или что вероятней при сроке контракта клиенту не выгодно уходить до истечения сроке
- TotalCharges: клиент уже много заплатил компании
- Tenure: заплатил больше
- MonthlyCharges: всплеск соотношения отточных клиентов в цене 80
- TotalCharges: заплатил больше

#### Корреляции
- Есть сильная корреляция (0,83) между столбцами tenure и total_charges бсолютно логично- чем больше клиент находится с компанией - тем больше общая 
сумма которую он заплатил за услуги компании
- dependns и partner (0.45) логично у кто в браке у того есть дети в данном случае у 45 процентов людей в этой выборке которые в браке у них есть дети
- monthly_charges и total_charges (0,65) понятно- что платеж за месяц просто умножается на количество месяцев проведенных с компанией

![image](https://user-images.githubusercontent.com/111303182/201114921-e472dd03-2e64-4dc0-ad6c-1a801d13ed20.png)

#### Зависимость fig
- Tenure: если месяцев мало то отток вероятнее
- MonthlyCharges: всплеск соотношения отточных клиентов в цене 80
- TotalCharges: Клиенты заплатившие больше оттекают реже
- tenure - количество месяцев, в течение которых клиент оставался в компании
- payment_method - способ оплаты клиента (электронный чек, чек по почте, автоматический банковский перевод, автоплатеж с карты)
- monthly_charges - сумма, взимаемая с клиента ежемесячно
- paperless_billing - есть ли у клиента безбумажный биллинг (да, нет)

#### Рекомендации
- поощрять клиентов в случае покупки различных доп услуг (защита данных, телефонного сервиса и тд);
-  внедрить абонементы на несколько месяцев 6 или 3 ;
- Проверить работу оптоволоконных кабелей ;
