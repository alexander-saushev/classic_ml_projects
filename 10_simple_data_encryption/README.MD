# Защита персональных данных клиентов страховой компании

[Посмотреть проект в NBViewer](https://nbviewer.org/github/alexander-saushev/classic_ml_projects/blob/main/10_simple_data_encryption/simple_data_encryption.ipynb) — в нем работает оглавление. Иногда сервис сбоит и проект не рендерится. Тогда можно [открыть работу здесь, на гитхабе](https://github.com/alexander-saushev/classic_ml_projects/blob/main/10_simple_data_encryption/simple_data_encryption.ipynb).

### Задача

Нужно защитить данные клиентов страховой компании «Хоть потоп». Разработаем такой метод преобразования данных, чтобы по ним было сложно восстановить персональную информацию, но при этом качество модели линейной регрессии не ухудшилось.

### Данные

Данные для тестирования алгоритма:

- **Признаки:** пол, возраст и зарплата застрахованного, количество членов его семьи.
- **Целевой признак:** количество страховых выплат клиенту за последние 5 лет.

### Ход работы

1. Знакомство с данными;
2. Теоретическое обоснование метода шифрования:
    1. разбор задачи линейной регрессии,
    2. разбор умножения на обратимую матрицу и описание алгоритма шифрования.
3. Проверка алгоритма:
    1. обучение модели на *незакодированных* данных и проверка ее качества,
    2. инициализация матрицы кодирования,
    3. обучение модели на *закодированных* данных и проверка ее качества.
4. Подведение итогов.

### Выводы

Для решения задачи мы теоретически доказали, что предсказания линейной регрессии не изменятся, если подаваемые ей признаки будут умножены на обратимую матрицу. На основе этого свойства мы создали алгоритм кодирования данных. Затем мы проверили его на реальных данных и получили подтверждающий теорию результат.

### Используемые инструменты

pandas, numpy, sklearn