

---

### 📝 Таск: Додати локалізацію (ua/en) за допомогою easy_localization

**Ціль:** Додати підтримку мультимовності (українська та англійська) у застосунок.

**Що потрібно зробити:**

- Підключити пакет [`easy_localization`](https://pub.dev/packages/easy_localization)
- Створити папку `assets/translations/` та додати файли `uk.json`, `en.json`
- Зареєструвати шляхи до файлів у `pubspec.yaml`
- Ініціалізувати EasyLocalization у `main.dart` (або через `core/localization/localization_setup.dart`)
- Додати приклад використання `.tr()` у будь-якому тестовому екрані
- Додати можливість перемикання мови (наприклад, кнопкою)

**Папки:**
- `lib/core/localization/` — зберігати налаштування локалізації

---

