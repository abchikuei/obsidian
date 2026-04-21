## ☀️ Raycast Configuration

---

### 🔗 **Quicklinks**

```json
[
  { "name": "Look Downloads", "link": "file:///Users/eldos/Downloads" },
  { "name": "Look Documents", "link": "file:///Users/eldos/Documents" },
  { "name": "Look Applications", "link": "file:///Applications" },
  {
    "name": "Look YouTube",
    "link": "https://www.youtube.com/results?search_query={Query}"
  },
  {
    "name": "Look Reddit",
    "link": "https://www.reddit.com/search/?q={Query}"
  },
  { "name": "Look NPM", "link": "https://www.npmjs.com/search?q={Query}" },
  {
    "name": "Look Github",
    "link": "https://github.com/search?q={Query}&type=repositories"
  },
  {
    "name": "Look MDN",
    "link": "https://developer.mozilla.org/en-US/search?q={Query}"
  }
]
```

---

### 📝 **Snippets**

````json
[
  {
    "name": "🌐 Search and Fix in Terminal",
    "text": "code $(fzf --preview='bat {} --color=always')",
    "keyword": "\\run"
  },
  {
    "name": "📝 Explain the technology prompt for AI",
    "text": "Объясни мне {argument name=\"Technology\"} ясно и коротко. Я хочу знать:\n\n1. Что эта за штука и какие у нее юзкейсы\n2. Как устроен внутри\n3. Какие аналоги имеются\n4. Чем отличается от других аналогов\n5. Покажи примеры как использовать эту штуку",
    "keyword": "\\tech"
  },
  {
    "name": "📝 Review the code prompt for AI",
    "text": "Пройдись по этому коду и выяви если есть проблемы по следующим категориям:\n\n1. Синтаксические ошибки\n2. Логическая ошибка\n3. Семантическая ошибка\n4. Производительность\n5. Читабельность\n6. Есть ли edge кейсы и проходит ли их мой алгоритм\n7. 7. Дай свой финальный вердикт\n\nБудь конкретен.\n\nВот код: \n```typescript\n{clipboard}\n```",
    "keyword": "\\review"
  },
  {
    "name": "📝 Find the bug prompt for AI",
    "text": "В этом коде есть какой то баг. Найди этот баг и объясни из за чего этот баг всплывает.\n\nВот код: {clipboard}\n\nВот ошибка которую я получаю: {argument name=\"Error\"}\n\nВот контекст для понимания: {argument name=\"Context\"}",
    "keyword": "\\bug"
  },
  {
    "name": "📝 Explain the concept prompt for AI",
    "text": "Объясни на пальцах {argument name=\"Concept\"}. Старайся выразить себя простыми словами и желательно используй иллюстрации и аналогии для ясности. Я хочу знать:\n\n1. Что из себя оно представляет\n2. Какие проблемы решает\n3. Как работает (интуитивно)\n4. Примеры использования\n5. Модифицированные версии (если есть таковы)\n",
    "keyword": "\\concept"
  },
  {
    "name": "📝 Explain the problem prompt for AI",
    "text": "Объясни мне задачу {argument name=\"Problem\"}. Я хочу чтобы ты разобрал следующие вопросы:\n\n1. Что дано в инпуте?\n2. Что от нас хотят (интиутивно)?\n3. Какие возможные пути решение есть у этой задачи?\n4. Какой путь ты выбрал бы?",
    "keyword": "\\problem"
  },
  {
    "name": "📝 Explain the word prompt for AI",
    "text": "Что означает слово/акроним {argument name=\"Word\"}. Так же ответь на эти вопросы:\n\n1. Значение этого слова\n2. Как используется в предложениях\n3. Приведи примеры на 3 языках: (Английский, Русский, Казахский)\n",
    "keyword": "\\word"
  }
]
````

---

### ⚡ **Raycast Extensions & Commands**

| #   | Extension / Command | What it is / Why you use it          | Common Use Case                            |
| --- | ------------------- | ------------------------------------ | ------------------------------------------ |
| 1   | `Brew`              | Raycast interface for Homebrew       | Install/manage CLI tools quickly           |
| 2   | `Color Picker`      | System color grabbing tool           | Pick colors from screen for UI/design      |
| 3   | `Kill Process`      | GUI process manager                  | Force stop frozen apps or processes        |
| 4   | `Ruler`             | On-screen measurement tool           | Measure UI spacing/pixels                  |
| 5   | `Raynotes`          | Custom AI note enhancer for Obsidian | Clean, polish, and structure notes         |
| 6   | `Translate`         | Google Translate                     | Translate into several languages at a time |
| 7   | `Svgl`              | Quick SVG Search                     | Convenient for UI                          |
