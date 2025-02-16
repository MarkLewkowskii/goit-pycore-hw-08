# Address Book CLI

## Опис
Це простий додаток для управління контактами в адресній книзі. Дозволяє зберігати номери телефонів, редагувати, видаляти їх, а також знаходити контакти за ім'ям. Крім того, підтримується збереження даних у файл для їх подальшого використання.

## Функціонал
- Додавання нового контакту
- Додавання номерів телефону
- Редагування номерів телефону
- Видалення номерів телефону
- Пошук номерів телефону
- Видалення контактів
- Відображення всіх контактів
- Додавання дня народження
- Відображення дня народження контакту
- Відображення найближчих днів народження
- Збереження та завантаження контактів

## Використання

### Запуск програми
Запустити програму можна через Python:
```bash
python main.py
```

### Приклад використання
```python
# Завантаження даних
book = load_data()

# Створення запису для John
john_record = Record("John")
john_record.add_phone("1234567890")
john_record.add_phone("5555555555")

# Додавання запису John до адресної книги
book.add_record(john_record)

# Створення та додавання нового запису для Jane
jane_record = Record("Jane")
jane_record.add_phone("9876543210")
book.add_record(jane_record)

# Виведення всіх записів у книзі
print(book)

# Знаходження та редагування телефону для John
john = book.find("John")
john.edit_phone("1234567890", "1112223333")
print(john)  # Виведення: Ім'я контакту: John, Номери: 1112223333; 5555555555

# Додавання дня народження
john.add_birthday("15.07.1990")
print(john)

# Отримання найближчих днів народження
print(book.get_upcoming_birthdays())

# Видалення номеру телефону у записі John
john.remove_phone("1112223333")

# Пошук конкретного телефону у записі John
found_phone = john.find_phone("5555555555")
print(f"{john.name}: {found_phone}")  # Виведення: John: 5555555555

# Видалення запису Jane
book.delete("Jane")

# Збереження змін
save_data(book)
```

## Вимоги
- Python 3.x

## Ліцензія
Проект надається "як є" без гарантій або відповідальності.

