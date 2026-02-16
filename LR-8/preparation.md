# Підготовка


## 0) Передумови 

Переконайся, що встановлено:

- **Node.js (LTS)**
- **IntelliJ IDEA** (Community або Ultimate)
- (Бажано) **Git**

Перевір у терміналі:

```bash
node -v
npm -v
```

<img width="497" height="267" alt="image" src="https://github.com/user-attachments/assets/1473b4c0-8315-40df-b8a7-7b402b85ddcb" />


## 1) Створення проєкту (рекомендований спосіб) 

### 1.1) Створи папку і запусти генератор Playwright

```bash
mkdir ui-playwright-intro
cd ui-playwright-intro
npm init playwright@latest
```
<img width="454" height="185" alt="image" src="https://github.com/user-attachments/assets/f76af996-01a6-4990-865b-2745e4525ce9" />

Під час майстра було обрано:

- **Language** → `TypeScript`
- **Tests folder** → `tests` (або залиш за замовчуванням)
- **Install browsers** → `Yes`
- **GitHub Actions** → на твій вибір (можна `No` для старту)

<img width="631" height="205" alt="image" src="https://github.com/user-attachments/assets/79bd4290-190c-487c-9d31-ad4cb82366f3" />

Після цього в проєкті з’являться:

- `playwright.config.ts`
- папка `tests/` з прикладом тесту
- `package.json`

<img width="549" height="892" alt="image" src="https://github.com/user-attachments/assets/54341520-0019-466b-8a66-c2616cadb426" />


---

## 2) Відкриття проєкту в IntelliJ IDEA 

1. **File → Open…** → обери папку `ui-playwright-intro`
2. Дочекайся індексації проєкту
3. Якщо IDEA запропонує встановити залежності — погодься. Якщо ні, виконай:

<img width="949" height="541" alt="image" src="https://github.com/user-attachments/assets/11dc46ab-796c-41d6-9a48-6dc09d0c01d8" />


---

## 3) Налаштування Node.js в IntelliJ IDEA 

В IDEA відкрий:

**Settings/Preferences → Languages & Frameworks → Node.js**

Переконайся, що:

- **Node interpreter** вказаний (IDE бачить Node.js)
- **Package manager** = npm

Якщо Node interpreter порожній — натисни **…** і вибери встановлений Node.

> Якщо IDEA не бачить npm/npx — допомагає перезапуск IDE або **Invalidate Caches / Restart**.

---

## 4) Додай зручні команди запуску (scripts) 

Відкрий `package.json` і додай/онови `scripts`:

```json
{
  "scripts": {
    "test": "playwright test",
    "test:headed": "playwright test --headed",
    "test:debug": "playwright test --debug",
    "test:ui": "playwright test --ui",
    "report": "playwright show-report"
  }
}
```

Тепер можна запускати:

```bash
npm test
npm run test:headed
npm run test:debug
npm run test:ui
npm run report
```

---

## 5) Запуск першого тесту 

### 5.1) Звичайний запуск

```bash
npx playwright test
```

або

```bash
npm test
```

### 5.2) Побачити виконання тесту (відкрити браузер)

```bash
npm run test:headed
```

### 5.3) Debug режим (Playwright Inspector + покроково)

```bash
npm run test:debug
```

### 5.4) UI Mode (зручний тест-раннер з кнопками)

```bash
npm run test:ui
```

### 5.5) HTML репорт

Після виконання тестів:

```bash
npm run report
```

---

## 6) “Уповільнення”

⚠️ Опція `--slow-mo` **НЕ працює** з командою `playwright test` (тому буде помилка `unknown option`).

Замість цього є 2 правильні способи:

### 6.1) Уповільнення через конфіг (slowMo)

В `playwright.config.ts` додай:

```ts
import { defineConfig } from '@playwright/test';

export default defineConfig({
  use: {
    headless: false,
    launchOptions: {
      slowMo: 300
    }
  }
});
```

Тепер запускай звичайно:

```bash
npm test
```

і дії будуть виконуватись повільніше.

### 6.2) Пауза під час тесту (інтерактивно)

У тесті можна вставити:

```ts
await page.pause();
```

Це відкриє Inspector і зупинить тест у потрібному місці — дуже зручно для демонстрації.

---

## 7) Запуск прямо з IntelliJ IDEA 

### 7.1) Через npm tool window (найпростіше)

- Відкрий вікно **npm**
- Знайди `test`, `test:headed`, `test:debug`, `test:ui`
- Запускай ▶️ прямо з IDE

### 7.2) Через Run Configuration

**Run → Edit Configurations… → + → npm**

- Command: `run`
- Script: наприклад `test:debug`

---

## 8) Типові помилки та рішення 

### `browser executable doesn't exist`
Не встановлені браузери:

```bash
npx playwright install
```

### `Cannot find module '@playwright/test'`
Не встановлені залежності:

```bash
npm install
```

### В IDEA немає підказок TypeScript/імпортів
- Перевір Node interpreter
- Перевір, що проект відкрито як папку з `package.json`
- Спробуй **Invalidate Caches / Restart**

---

## Codegen 

Codegen відкриває браузер і генерує код під твої кліки:

```bash
npx playwright codegen https://example.com
```

> Тут `--slow-mo` працює:

```bash
npx playwright codegen --slow-mo 300 https://example.com
```

---

Готово ✅ Тепер у тебе є Playwright + TypeScript, запуск з терміналу та з IntelliJ, а також режими headed/debug/ui для демонстрації.
