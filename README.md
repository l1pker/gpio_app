# GPIO APP

Система керування GPIO, написана мовою програмування Rust із застосуванням бібліотеки `rppal` для роботи з GPIO на платформах, заснованих на Linux (наприклад, Raspberry Pi). Дозволяє взаємодіяти з апаратними компонентами через GPIO-піни, вести журнал подій та демонструвати роботу системи у режимі реального часу.

## Зміст
- [Опис](#опис)
- [Особливості](#особливості)
- [Вимоги](#вимоги)
- [Інструкція з встановлення](#інструкція-з-встановлення)
  - [Windows](#windows)
  - [macOS](#macos)
  - [Linux](#linux)
  - [Raspberry Pi](#raspberry-pi)
- [Діаграми](#діаграми)
- [Використання](#використання)
- [Ліцензія](#ліцензія)

## Опис
Цей проект реалізує систему керування GPIO, що дозволяє:

- Ініціалізувати GPIO-піни для кнопки та світлодіода.
- Зчитувати стан кнопки та перемикати стан світлодіода.
- Вести журнал подій у файл `log.txt` із позначками часу.
- Забезпечувати стабільну роботу при виникненні короткочасних фальшивих сигналів.


## Особливості
- **Безпечне управління пам’яттю**: Використання Rust мінімізує ризик помилок, характерних для мов C/C++.
- **Низькорівневий доступ до GPIO**: Бібліотека `rppal` надає простий інтерфейс для роботи з GPIO.
- **Журналювання подій**: Кожна зміна стану фіксується у `log.txt`.
- **Адаптивність**: Підтримується запуск на Linux та в емуляційному режимі на Windows/macOS.
- **Документація**: UML-діаграми у папці `diagrams`.

## Вимоги
- **Операційна система**: Linux (рекомендовано Raspberry Pi OS), Windows або macOS (для симуляції).
- **Rust та Cargo**: Остання версія Rust та Cargo.
- **Git**: Для клонування репозиторію.
- **Бібліотеки**: `rppal`, `chrono`, `std::fs`.

## Інструкція з встановлення

### Windows
```sh
# Встановіть Rust та Git

# Клонуйте репозиторій
git clone https://github.com/l1pker/gpio_app.git
cd gpio_led

# Побудуйте проект
cargo build

# Запустіть програму
cargo run
```

### macOS
```sh
# Встановіть Rust та Git

# Клонуйте репозиторій
git clone https://github.com/l1pker/gpio_app.git
cd gpio_led

# Побудуйте проект
cargo build

# Запустіть програму
cargo run
```

### Linux
```sh
# Встановіть Rust та Git
sudo apt update && sudo apt install -y git
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

# Клонуйте репозиторій
git clone https://github.com/l1pker/gpio_app.git
cd gpio_led

# Побудуйте проект
cargo build

# Запустіть програму
cargo run
```

### Raspberry Pi
```sh
# Оновіть систему та встановіть необхідні пакети
sudo apt update && sudo apt upgrade -y

# Встановіть Rust та Git
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
sudo apt install -y git

# Клонуйте репозиторій
git clone https://github.com/l1pker/gpio_app.git
cd gpio_led

# Побудуйте проект
cargo build

# Запустіть програму 
cargo run
```

## Діаграми
Усі UML-діаграми знаходяться у папці `diagrams`, включаючи:
- **Діаграми варіантів використання**
- **Діаграми послідовності**
- **Діаграми класів**
- **Діаграми діяльності**

## Використання
Після запуску програми виводиться інформація про платформу (Raspberry Pi або інша) та зміни станів кнопки і світлодіода. Журнал подій зберігається у файлі `log.txt`.

