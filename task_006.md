
---

### 📌 **Задача: Інтеграція GoRouter у Flutter-проєкт**

#### 🎯 **Мета**
Інтегрувати бібліотеку [GoRouter](https://pub.dev/packages/go_router) для зручного й централізованого управління маршрутизацією в додатку. Замість використання `Navigator.push`, реалізувати навігацію через декларативний роутінг згідно з навігаційним флоу MVP.

---

#### 📁 **Структура проєкту (контекст)**

- Архітектура: **MVVM + feature-first**
- Основні екрани MVP:
  - `SplashScreen`
  - `ChooseAnimalScreen`
  - `InstructionScreen`
  - `InteractionScreen`

---

#### ✅ **To-Do**

1. **Додати залежність**
   У `pubspec.yaml` додати бібліотеку:
   ```yaml
   dependencies:
     go_router: ^13.0.0
   ```

2. **Створити файл конфігурації роутера**
   ```
   lib/core/routing/app_router.dart
   ```
   У файлі оголосити `GoRouter` зі шляхами для всіх MVP-екранів:
   - `/` → SplashScreen
   - `/choose-animal` → ChooseAnimalScreen
   - `/instruction` → InstructionScreen
   - `/interaction` → InteractionScreen

3. **Підключити GoRouter у `main.dart`**
   Замінити `MaterialApp` на `MaterialApp.router`, передати `routerConfig`.

4. **Переписати переходи між екранами**
   Усі переходи реалізовувати через `context.go(...)` або `context.goNamed(...)`.

5. **(Опціонально)** Створити enum або утиліти для назв маршрутів:
   ```
   lib/core/routing/router_utils.dart
   ```

---

#### 🧪 **Критерії прийому (Definition of Done)**

- Усі переходи виконуються через `GoRouter`.
- Екрани відкриваються **без дублікатів у стеку**.
- `main.dart` використовує `MaterialApp.router`.
- Усі маршрути оголошено централізовано в `app_router.dart`.

---

