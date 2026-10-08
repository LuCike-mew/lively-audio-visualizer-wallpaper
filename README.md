# RU Customizable Audio Visualizer for Lively Wallpaper

Минималистичные и кастомные интерактивные веб-обои для [Lively Wallpaper](https://rocksdanister.github.io/lively/) с аудио-визуализатором и информацией о треке из Spotify/системы.

---

## Особенности

- **Аудио-визуализатор**: 64 спектральные полосы, работающие от системного звука.
- **Интеграция с медиаплеерами**: Отображение обложки, названия и исполнителя трека через Windows SMTC (Spotify, Яндекс Музыка, браузеры).
- **Минималистичный вес**: Репозиторий содержит только логику и структуру — фон вы выбираете сами.

---

## Структура проекта

Для корректной работы в вашей локальной папке должны быть следующие файлы:

```text
├── index.html          # Основной код визуализатора и стилей
├── LivelyInfo.json     # Конфигурационный файл манифеста Lively
└── background.mp4      # Ваше фоновое видео (добавляется вручную)
```

---

## Подробная инструкция по установке

### Шаг 1. Скачивание файлов
1. На странице репозитория нажмите зеленую кнопку **Code** -> **Download ZIP**.
2. Распакуйте архив в любую удобную папку на ПК.

### Шаг 2. Добавление фонового видео
1. Найдите или скачайте любое видео, которое хотите использовать в качестве фона (в формате `.mp4`).
2. Поместите файл видео в папку с распакованным проектом.
3. Переименуйте его строго в **`background.mp4`**.

### Шаг 3. Импорт в Lively Wallpaper
1. Запустите программу **Lively Wallpaper**.
2. В верхней панели нажмите кнопку **Добавить обои** (значок **`+`**).
3. Перетащите папку с проектом (или итоговый ZIP-архив) в открывшееся окно Lively.
4. Нажмите **ОК** во всплывающем окне подтверждения.

---

## Настройка отдельного аудиопотока (Виртуальный кабель)

Если визуализатор не реагирует на звук или вы хотите направить в него аудио из конкретного приложения (например, только из Spotify, не захватывая звук из игр или Discord):

1. **Скачайте драйвер:** Установите бесплатный виртуальный аудиокабель [VB-Audio VB-Cable](https://vb-audio.com/Cable/).
2. **Разделите вывод звука в Windows:**
   - Откройте **Параметры Windows** -> **Система** -> **Звук** -> **Параметры громкости приложений и устройств**.
   - Найдите в списке ваш плеер (Spotify / браузер) и укажите в качестве устройства вывода `CABLE Input`.
3. **Настройте Lively Wallpaper:**
   - В настройках Lively Wallpaper (**Настройки** -> **Аудио**) выберите устройство захвата.
   - Подробную инструкцию по решению проблем со звуком читайте в [официальном руководстве Lively Audio Wiki](https://github.com/rocksdanister/lively/wiki/Audio-Visualizer).

---

## Кастомизация и настройка цветов

Все ключевые параметры легко меняются внутри `index.html`:

### 1. Акцентный цвет рамки и свечения (CSS)
В начале файла `index.html` найдите блок `:root` и установите желаемый цвет в формате RGB:
```css
:root {
  --accent-rgb: 255, 255, 255; /* По умолчанию белый */
}
```

### 2. Цвет полос визуализатора (JavaScript)
В функции `draw()` можно изменить цвет и свечение спектральных полос:
```javascript
ctx.strokeStyle = 'rgba(255, 255, 255, 0.9)'; // Основной цвет полос
ctx.shadowColor = 'rgba(255, 255, 255, 0.6)'; // Цвет свечения
```

# EN Customizable Audio Visualizer for Lively Wallpaper

A minimalist and customizable interactive web wallpaper for [Lively Wallpaper](https://rocksdanister.github.io/lively/) featuring an audio visualizer and media info from Spotify/system.

---

## Features

- **Audio Visualizer**: 64 spectral bars reacting to system audio.
- **Media Player Integration**: Displays album art, track title, and artist via Windows SMTC (Spotify, Yandex Music, web browsers).
- **Lightweight Footprint**: The repository contains only logic and structure — you choose your own background video.

---

## Project Structure

To ensure proper functionality, your local project folder should contain the following files:

```text
├── index.html          # Main visualizer code and styles
├── LivelyInfo.json     # Lively manifest configuration file
└── background.mp4      # Your background video (added manually)
```

---

## Detailed Installation Guide

### Step 1. Download Files
1. On the repository page, click the green **Code** -> **Download ZIP** button.
2. Extract the archive into any folder on your PC.

### Step 2. Add Background Video
1. Find or download any video you want to use as a background (in `.mp4` format).
2. Place the video file into the extracted project folder.
3. Rename it strictly to **`background.mp4`**.

### Step 3. Import into Lively Wallpaper
1. Open **Lively Wallpaper**.
2. In the top toolbar, click the **Add Wallpaper** button (**`+`** icon).
3. Drag and drop the project folder (or the ZIP archive) into the Lively window.
4. Click **OK** in the confirmation popup.

---

## Dedicated Audio Stream Setup (Virtual Cable)

If the visualizer does not react to sound or you want to isolate audio from a specific application (e.g., capture Spotify only, excluding games or Discord):

1. **Download Driver:** Install the free virtual audio cable [VB-Audio VB-Cable](https://vb-audio.com/Cable/).
2. **Split Audio Output in Windows:**
   - Go to **Windows Settings** -> **System** -> **Sound** -> **App volume and device preferences**.
   - Locate your media player (Spotify / browser) in the list and set its output device to `CABLE Input`.
3. **Configure Lively Wallpaper:**
   - In Lively Wallpaper settings (**Settings** -> **Audio**), select the audio capture device.
   - For detailed troubleshooting, refer to the [official Lively Audio Wiki guide](https://github.com/rocksdanister/lively/wiki/Audio-Visualizer).

---

## Customization and Color Settings

All key parameters can be easily modified inside `index.html`:

### 1. Border Accent Color and Glow (CSS)
At the beginning of `index.html`, locate the `:root` block and set your desired RGB color:
```css
:root {
  --accent-rgb: 255, 255, 255; /* Default is white */
}
```

### 2. Visualizer Bar Colors (JavaScript)
Inside the `draw()` function, you can adjust the bar color and glow effect:
```javascript
ctx.strokeStyle = 'rgba(255, 255, 255, 0.9)'; // Main bar color
ctx.shadowColor = 'rgba(255, 255, 255, 0.6)'; // Glow color
```
