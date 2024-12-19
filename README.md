# Проектный Хакатон MIFIML команды Space Plans

## Вводные данные
**Название команды(Рабочее):** Space plans

**Структура команды:**

* **Team leader:** Кловер Натан ( Clover9301@gmail.com )

* **Product manager:** Воронин Михаил Михайлович ( mixan2912@gmail.com )

* **Analytics team:** 
  * Прокофьев Михаил Всеволодович ( k0rsair@mail.ru )
  * Жадаев Василий Васильевич ( st1m_97@mail.ru )
  * Колотий Марианна Павловна ( mildburg@rambler.ru )
## Тема проекта - мониторинг качества воздуха

**[Набор данных](https://www.kaggle.com/datasets/hasibalmuzdadid/global-air-pollution-dataset)**

**requirements.txt:**

    catboost==1.2.7
    pandas==2.2.2
    numpy==1.26.4
    kagglehub==0.3.5
    lightgbm==4.5.0
    sklearn-pandas==2.2.0
    matplotlib==3.8.0
    seaborn==0.13.2
## Пример использования

```python
new_data = pd.DataFrame({
    'CO AQI Value': [20],
    'Ozone AQI Value': [50],
    'NO2 AQI Value': [30],
    'PM2.5 AQI Value': [40],
    'Country': ['USA'],
    'City': ['New York']
})

aqi_value, aqi_category = predict_aqi(new_data)
aqi_category_for_map = aqi_category[0][0]
print(f'Predicted AQI Value: {aqi_value}')
print(f'Predicted AQI Category: {aqi_category_mapping[aqi_category_for_map]}')
```
### Бизнес-постановка задачи
* **Проблема**

  * Окружающая среда подвергается постоянным изменениям под влиянием естественных факторов и человеческой деятельности. Экологам, научным исследователям и властям необходимы надёжные данные для мониторинга состояния экосистем, принятия обоснованных решений по охране природы и реагирования на экологические вызовы. Однако традиционные методы сбора данных трудоёмки, часто неожиданно высока вероятность ошибок.

  * Из-за роста техногенного воздействия и изменения климата актуальность точных и оперативных экологических исследований возрастает. Наблюдение за флорой и фауной, качеством атмосферного воздуха, состоянием водных ресурсов и земельных участков требует интеграции данных самого разного рода и формата.

* **Цель**

  Интегрировать предобученную модель машинного обучения для анализа данных о загрязнениях воздуха, чтобы:
    * Прогнозировать общий индекс качества воздуха (AQI Value).
    * Классифицировать уровень загрязнения (AQI Category).
    * Оценивать влияние отдельных загрязнителей (CO, Ozone, NO2, PM2.5) на качество воздуха.

### Этапы реализации
  1. **Подготовка данных:**
    * Загрузка и очистка табличных данных, включающих информацию о стране, городе, уровне загрязнения и категориях AQI.
    * Кодирование категориальных данных (Country, City, AQI Category) с использованием методов, таких как Label Encoding.

 2. **Обучение модели:**
    * Использование предобученной модели CatBoost для выполнения задач:
      * Прогнозирование AQI Value.
      * Классификация AQI Category.
      * Оценка влияния загрязнителей на AQI.
      * Применение методов машинного обучения для обучения модели с учетом фич, таких как показатели загрязняющих веществ и географическое расположение.
  
  3. **Оценка модели:**
    * Оценка качества модели с помощью метрик, таких как:
    * Для задачи регрессии: Mean Squared Error (MSE), R² Score.
    * Для задачи классификации: Accuracy, Precision, Recall, F1-Score.
    * Проведение кросс-валидации для повышения надежности результатов.
    
  4. **Визуализация и интерпретация результатов:**
    * Построение графиков важности признаков, чтобы понять, какие загрязнители оказывают наибольшее влияние на результаты.
    * Визуализация предсказаний модели и реальных значений AQI.
