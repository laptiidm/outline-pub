## Інтеграція Riverpod та Тестовий Екран

**Опис:**

Метою цього таску є базова інтеграція бібліотеки Riverpod у проєкт та створення простого тестового екрану для перевірки її працездатності.

**Критерії виконання:**

1.  Додано залежності `riverpod` та `flutter_riverpod` до файлу `pubspec.yaml` та виконано команду `flutter pub get`.
2.  Створено базовий провайдер (наприклад, простий `StateProvider` або `Provider`) у файлі `lib/core/providers/` (рекомендована директорія для глобальних провайдерів).
3.  Створено новий файл `test_riverpod_screen.dart` у директорії `lib/presentation/screens/`. Цей екран повинен використовувати `ConsumerWidget` або `ref.watch()` для отримання значення з створеного провайдера та відображення його на UI (достатньо простого `Text` віджета).
4.  Додано тимчасову кнопку на головному екрані (`main.dart` або іншому зручному місці) для навігації на `TestRiverpodScreen`.
5.  Переконано, що застосунок успішно запускається, і при переході на `TestRiverpodScreen` відображається значення, отримане з провайдера Riverpod.

**Оцінка часу:**

* 2 години

**Примітки:**

* Для базового провайдера ви можете використати `StateProvider`, щоб створити простий стан, який можна змінювати, або `Provider`, якщо вам потрібно надати незмінне значення.
* У `TestRiverpodScreen` використовуйте `ConsumerWidget` як базовий віджет або отримайте `WidgetRef` у методі `build` `StatelessWidget` чи `StatefulWidget`.
* Головна мета – переконатися, що Riverpod підключено, провайдер створено, і ви можете отримати доступ до його значення з віджета.

Цей таск дозволить швидко перевірити інтеграцію Riverpod перед тим, як заглиблюватися в більш складне управління станом. Директорія `lib/presentation/screens/` є логічним місцем для розміщення тестового екрану, оскільки вона призначена для UI-елементів, що представляють окремі екрани застосунку.
