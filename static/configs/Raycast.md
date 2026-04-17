## ☀️ Raycast Configuration

---
### 🔗 **Quicklinks**

```json
[
	{
		"link": "https:\/\/google.com\/search?q={Query}",
		"name": "Search Google"
	},
	{
		"link": "https:\/\/www.youtube.com\/results?search_query={Query}",
		"name": "Search YouTube"
	},
	{
		"link": "https:\/\/www.reddit.com\/search\/?q={Query}",
		"name": "Search Reddit"
	},
	{
		"link": "https:\/\/stackoverflow.com\/search?q={Query}",
		"name": "Search Stack Overflow"
	},
	{
		"link": "https:\/\/www.npmjs.com\/package\/{Query}",
		"name": "Search NPM Package",
		"iconName": "brand-npm-16"
	},
	{
		"link": "https:\/\/hub.docker.com\/search?q={Query}",
		"name": "Search Docker Hub"
	},
	{
		"link": "https:\/\/github.com\/search?q={Query}&type=repositories",
		"name": "Search Github"
	},
	{
		"link": "https:\/\/developer.mozilla.org\/en-US\/search?q={Query}",
		"name": "Search MDN"
	},
	{
		"link": "https://github.com/devought/my-settings/blob/main/.prettierrc",
		"name": "My Prettier Config"
	},
	{ "link": "file:///Users/eldos/Downloads", "name": "Downloads" },
	{ "link": "file:///Users/eldos/Documents", "name": "Documents" },
	{ "link": "file:///Applications", "name": "Applications" }
]
```

---

### 📝 **Snippets**

```json
[
	{
		"name": "Explain Technology",
		"text": "Объясни мне {argument name=\"Technology\"} ясно и коротко. Я хочу знать:\n\n1. Что эта за штука и какие у нее юзкейсы\n2. Как устроен внутри\n3. Какие аналоги имеются\n4. Чем отличается от других аналогов\n5. Покажи примеры как использовать эту штуку",
		"keyword": "\\explain"
	},
	{
		"name": "Review",
		"text": "Пройдись по этому коду и выяви если есть проблемы по следующим категориям:\n\n1. Синтаксические ошибки\n2. Логическая ошибка\n3. Семантическая ошибка\n4. Производительность\n5. Читабельность\n6. Есть ли edge кейсы и проходит ли их мой алгоритм\n7. 7. Дай свой финальный вердикт\n\nБудь конкретен.\n\nВот код: \n```typescript\n{clipboard}\n```",
		"keyword": "\\review"
	},
	{
		"name": "Find the Bug",
		"text": "В этом коде есть какой то баг. Найди этот баг и объясни из за чего этот баг всплывает.\n\nВот код: {clipboard}\n\nВот ошибка которую я получаю: {argument name=\"Error\"}\n\nВот контекст для понимания: {argument name=\"Context\"}",
		"keyword": "\\bug"
	},
	{
		"name": "Explain Concept",
		"text": "Объясни на пальцах {argument name=\"Concept\"}. Старайся выразить себя простыми словами и желательно используй иллюстрации и аналогии для ясности. Я хочу знать:\n\n1. Что из себя оно представляет\n2. Какие проблемы решает\n3. Как работает (интуитивно)\n4. Примеры использования\n5. Модифицированные версии (если есть таковы)\n",
		"keyword": "\\concept"
	},
	{
		"name": "Explain the Problem",
		"text": "Объясни мне задачу {argument name=\"Problem\"}. Я хочу чтобы ты разобрал следующие вопросы:\n\n1. Что дано в инпуте?\n2. Что от нас хотят (интиутивно)?\n3. Какие возможные пути решение есть у этой задачи?\n4. Какой путь ты выбрал бы?",
		"keyword": "\\problem"
	},
	{
		"name": "Explain the Word",
		"text": "Что означает слово\/акроним {argument name=\"Word\"}. Так же ответь на эти вопросы:\n\n1. Значение этого слова\n2. Как используется в предложениях\n3. Приведи примеры на 3 языках: (Английский, Русский, Казахский)\n",
		"keyword": "\\word"
	},
	{ "name": "Typescript", "text": "typescript", "keyword": "\\ts" },
	{ "name": "Javascript", "text": "javascript", "keyword": "\\js" }
]

```

---

### ⚡ **Raycast Extensions & Commands**

| #   | Extension / Command | What it is / Why you use it          | Common Use Case                       | Example                              |
| --- | ------------------- | ------------------------------------ | ------------------------------------- | ------------------------------------ |
| 1   | `Brew`              | Raycast interface for Homebrew       | Install/manage CLI tools quickly      | Search → install `node`              |
| 2   | `Color Picker`      | System color grabbing tool           | Pick colors from screen for UI/design | Copy hex code `#FF5733`              |
| 3   | `Kill Process`      | GUI process manager                  | Force stop frozen apps or processes   | Kill `Chrome` or PID                 |
| 4   | `Ruler`             | On-screen measurement tool           | Measure UI spacing/pixels             | Measure button padding in Figma/web  |
| 5   | `Raynotes`          | Custom AI note enhancer for Obsidian | Clean, polish, and structure notes    | Convert raw notes → markdown summary |
