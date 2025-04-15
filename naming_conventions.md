# 📘 Naming Conventions — Flutter/Dart

Цей документ описує стандарти найменування, яких потрібно дотримуватися в проєкті для підтримки читабельності, послідовності та легкості масштабування коду.

---

## 🧱 Загальні принципи

- ✅ Англійська мова для всіх назв
- ✅ Використовуй зрозумілі, описові назви
- ✅ Уникай скорочень, якщо вони не є загальноприйнятими
- ✅ Назва має відповідати ролі/призначенню об’єкта

---

## 📦 Файли та папки

| Тип               | Формат            | Приклад                      |
|------------------|-------------------|------------------------------|
| Папки            | `snake_case`      | `core/services`, `features/home` |
| Dart файли       | `snake_case.dart` | `animal_feedback_service.dart` |

---

## 🔹 Класи

| Тип           | Формат      | Приклад                      |
|----------------|--------------|------------------------------|
| Клас           | `PascalCase` | `AnimalService`, `HomeScreen` |
| Віджет         | `PascalCase` | `MainButton`, `AnimalCard`    |
| Enum           | `PascalCase` | `AnimalType`, `UserRole`      |

---

## 🧩 Функції та методи

| Тип             | Формат         | Приклад                     |
|------------------|----------------|-----------------------------|
| Функція/метод    | `camelCase()`  | `loadAnimals()`, `playPurr()` |
| Асинхронна дія   | `camelCase()` + дієслово | `fetchData()`, `saveProgress()` |

> 🔹 Іменування функцій — дієслівні, що відображають дію: `get`, `load`, `save`, `build`, `update`, `reset`, `select`, `show`, `hide`.

---

## 🧮 Змінні

| Тип         | Формат         | Приклад                  |
|-------------|----------------|--------------------------|
| Локальні    | `camelCase`    | `isActive`, `animalList` |
| Константи   | `camelCase` або `SCREAMING_SNAKE_CASE` | `defaultAnimal`, `MAX_VIBRATION_DURATION` |

---

## 🔁 Пакети / Провайдери

- Назви провайдерів мають чітко відображати суть:
  - `animalServiceProvider`
  - `authControllerProvider`

---

## 📍 Приклади "хорошого" коду

```dart
class AnimalService {
  Future<void> playPurrFeedback() async {
    // ...
  }

  List<Animal> getAnimalsByType(AnimalType type) {
    // ...
  }
}

final animalServiceProvider = Provider<AnimalService>((ref) {
  return AnimalService();
});
