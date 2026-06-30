# phoenix - до последнего вздоха!

<details>
  <summary>💰 Покупка домена</summary>
</details>

<details>
  <summary>💰 Аренда сервера</summary>
</details>

<details>
  <summary>🔤 DNS запись, связь домена и сервера</summary>
</details>

<details>
<summary>🔄 Шаг 1: Обновление системы</summary>

## 🔄 Шаг 1: Обновление системы

Перед началом настройки обновим все пакеты системы:

```bash
# Обновление списков пакетов
apt update
```
```bash
# Обновление всех пакетов
apt upgrade -y
```
```bash
# Удаление ненужных зависимостей
apt autoremove -y
```
```bash
# Очистка кэша
apt autoclean
```

Или одной командой:

```bash
apt update && apt upgrade -y && apt autoremove -y && apt autoclean
```

### Проверка перезагрузки

После обновления проверим, требуется ли перезагрузка ядра:

```bash
cat /var/run/reboot-required
```

- Если команда вернула `*** System restart required ***` - нужна перезагрузка
- Если файла нет или команда ничего не вернула - можно продолжать

### Перезагрузка (если требуется):

```bash
reboot
```

> ⚠️ **Важно:** После перезагрузки подожди 1-2 минуты и подключись снова по SSH.
</details>

<details>
<summary>🏷️ Шаг 2: Настройка hostname</summary>

## 🏷️ Шаг 2: Настройка hostname

По умолчанию хостер устанавливает своё имя (например, `<generator>.<hosting-domain>.<domain>`).

Нужно изменить на наш домен `<ваш_домен/субдомен>`.

### Смена hostname:

```bash
# Устанавливаем новый hostname
hostnamectl set-hostname <ваш_домен/субдомен>
```

```bash
# Проверяем
hostname
hostname -f
```
</details>
