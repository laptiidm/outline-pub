## Таск: Реалізація базового сервісу вібрації (VibrationService)

**🎯 Мета:**

Створити окремий сервіс `VibrationService`, який відповідатиме за виклик вібрації пристрою. Сервіс має бути простим у використанні та доступним для виклику з будь-якої частини застосунку.

**🔍 Research:**

* Ознайомитися з Flutter-пакетом `vibration`.
* Зрозуміти:
    * як перевірити, чи пристрій підтримує вібрацію.
    * як викликати короткі та патернові вібрації.

**🛠 Реалізація:**

1.  **Встановити пакет:** Додати залежність `vibration: ^версія` до файлу `pubspec.yaml` та виконати `flutter pub get`.
2.  **Створити сервіс:** Створити файл `lib/services/vibration_service.dart`.
3.  **Реалізувати клас (приклад) `VibrationService`:**

    ```dart
    import 'package:vibration/vibration.dart';

    class VibrationService {
      Future<void> vibrateShort() async {
        if (await Vibration.hasVibrator() ?? false) {
          Vibration.vibrate(duration: 500); // Вібрація протягом 500 мілісекунд
        }
      }

      Future<void> vibratePattern() async {
        if (await Vibration.hasVibrator() ?? false) {
          Vibration.vibrate(pattern: [0, 100, 100, 200]); // Патерн: пауза 0мс, вібрація 100мс, пауза 100мс, вібрація 200мс
        }
      }

      // Метод для майбутньої синхронізації (простий приклад)
      Future<void> vibrate(int durationMs) async {
        if (await Vibration.hasVibrator() ?? false) {
          Vibration.vibrate(duration: durationMs);
        }
      }
    }
    ```

4.  **Приклад використання (у тестовому екрані або кнопці):** Для перевірки створіть простий спосіб викликати сервіс. Наприклад, додайте кнопки на вашому тестовому екрані (`test_riverpod_screen.dart` або створіть ще один простий екран):

    ```dart
    import 'package:flutter/material.dart';
    import 'package:your_app_name/services/vibration_service.dart'; // Шлях до вашого сервісу

    class VibrationTestScreen extends StatelessWidget {
      final VibrationService _vibrationService = VibrationService();

      @override
      Widget build(BuildContext context) {
        return Scaffold(
          appBar: AppBar(title: const Text('Тест Вібрації')),
          body: Center(
            child: Column(
              mainAxisAlignment: MainAxisAlignment.center,
              children: <Widget>[
                ElevatedButton(
                  onPressed: () => _vibrationService.vibrateShort(),
                  child: const Text('Коротка вібрація'),
                ),
                const SizedBox(height: 20),
                ElevatedButton(
                  onPressed: () => _vibrationService.vibratePattern(),
                  child: const Text('Вібрація за патерном'),
                ),
                const SizedBox(height: 20),
                ElevatedButton(
                  onPressed: () => _vibrationService.vibrate(1000),
                  child: const Text('Вібрація 1 секунду'),
                ),
              ],
            ),
          ),
        );
      }
    }
    ```

5.  **Додати кнопку для переходу (якщо ви створили окремий `VibrationTestScreen`):** На головному екрані або іншому зручному місці додайте кнопку для навігації на `VibrationTestScreen`.

**📦 Output:**

* Працюючий модуль `VibrationService` з методами для короткої вібрації, вібрації за патерном та вібрації заданої тривалості.
* Простий спосіб (наприклад, `VibrationTestScreen`) для тестування функціональності вібрації.

**📅 Оцінка часу:**

3-4 години (включаючи ресерч та базове тестування).

**Примітки:**

* На цьому етапі ми не прив'язуємо сервіс до Riverpod. Ви зможете імпортувати `VibrationService` безпосередньо в ті місця коду, де потрібно викликати вібрацію.
* У майбутніх тасках ми можемо розглянути інтеграцію з Riverpod для більш централізованого управління та доступу до сервісу, особливо при синхронізації зі звуком або іншими подіями.

Цей спрощений таск зосереджений виключно на створенні функціоналу вібрації, що робить його більш простим для виконання на початковому етапі.
