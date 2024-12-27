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

**Установка**

    pip install -r requirements.txt
    
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

  * Окружающая среда постоянно меняется под воздействием природных факторов и деятельности человека. Экологам, научным работникам и представителям власти необходимы достоверные данные для мониторинга состояния экосистем, принятия обоснованных решений по сохранению и реагированию на экологические проблемы. Однако традиционные методы сбора данных трудоемки и часто показывают высокий процент ошибок.

  * Точные и оперативные экологические исследования приобретают все большее значение в связи с усилением антропогенного воздействия и изменением климата. Мониторинг флоры и фауны, качества воздуха, воды и состояния земель требует интеграции различных типов и форматов данных.

* **Цель**
  * Интеграция предварительно обученных моделей машинного обучения для анализа данных о загрязнении воздуха, чтобы:
       * Прогнозировать общий индекс качества воздуха (AQI ).
       * Классифицировать уровень загрязнения (AQI Category).
       * Оценивать влияние отдельных загрязнителей (CO, Ozone, NO2, PM2.5) на качество воздуха.

* **Этапы реализации**
  * **Подготовка данных:**
    * Загрузка и очистка табличных данных, содержащих информацию о стране, городе, уровне загрязнения и категории AQI.
    * Кодирование категориальных данных (Country, City, AQI Category) с использованием методов, таких как Label Encoding.

 2. **Обучение модели:**
      * Использование предварительно обученных моделей CatBoost для выполнения следующих задач:
      * Прогнозирование значений AQI Value.
      * Классификация AQI Category.
      * Оценка влияния загрязняющих веществ на AQI.
      * Применение методов машинного обучения для обучения модели с использованием показателей процентного содержания загрязняющих веществ и географическое положение.
  
  3. **Оценка модели:**
       * Оценка качества модели с помощью различных метрик:
       * Для задачи регрессии: Mean Squared Error (MSE), R² Score.
       * Для задачи классификации: Accuracy
       * Проведение кросс-валидации для повышения надежности результатов.
    
  4. **Визуализация и интерпретация результатов:**
       * Построение графиков важности признаков, чтобы понять, какие вредные вещества оказывают наибольшее влияние на результаты.
       * Визуализация предсказаний модели и реальных значений AQI.
