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
