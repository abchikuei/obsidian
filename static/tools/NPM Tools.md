## ⚡ Runtimes

|#|Tool|What it is / Why you use it|Common Use Case|Example|
|---|---|---|---|---|
|1|`node`|JavaScript runtime engine|Run backend Node.js apps|`node app.js`|
|2|`bun`|Fast JS runtime + bundler + package manager|Run and bundle apps faster than Node|`bun run index.ts`|
|3|`deno`|Secure modern JS/TS runtime|Run TypeScript without setup|`deno run app.ts`|

---

## 📦 Package Managers

|#|Tool|What it is / Why you use it|Common Use Case|Example|
|---|---|---|---|---|
|1|`npm`|Default Node package manager|Install dependencies|`npm install express`|
|2|`yarn`|Faster alternative package manager|Manage dependencies efficiently|`yarn add express`|
|3|`pnpm`|Disk-efficient package manager|Faster installs, monorepos|`pnpm add express`|
|4|`bun`|All-in-one runtime + package manager|Install packages very fast|`bun add express`|

---

## 🧱 Bundlers & Build Tools

|#|Tool|What it is / Why you use it|Common Use Case|Example|
|---|---|---|---|---|
|1|`vite`|Fast dev server + bundler|Modern frontend builds|`vite dev`|
|2|`webpack`|Classic module bundler|Complex frontend apps|`webpack --config`|
|3|`rollup`|Library bundler|Build npm packages|`rollup -c`|
|4|`rolldown`|Next-gen bundler (Rust-based)|Faster builds than Rollup|`rolldown build`|
|5|`rspack`|Webpack-compatible Rust bundler|Drop-in Webpack replacement|`rspack build`|
|6|`turbopack`|Vercel’s ultra-fast bundler|Next.js development|`next dev --turbo`|
|7|`esbuild`|Extremely fast bundler|Build TS/JS quickly|`esbuild index.ts`|
|8|`parcel`|Zero-config bundler|Simple frontend apps|`parcel index.html`|
|9|`gulp`|Task runner|Automate build workflows|`gulp build`|
|10|`babel`|JS transpiler|Convert modern JS to compatible JS|`babel src --out-dir dist`|
|11|`swc`|Fast JS/TS compiler (Rust)|Replace Babel/TS compiler|`swc src -d dist`|

---

## 🟦 TypeScript Tools

|#|Tool|What it is / Why you use it|Common Use Case|Example|
|---|---|---|---|---|
|1|`tsc`|Official TypeScript compiler|Compile TS to JS|`tsc`|
|2|`ts-node`|Run TypeScript directly in Node|Dev scripting|`ts-node app.ts`|
|3|`tsx`|Fast TS execution runtime|Run TS without compile step|`tsx app.ts`|

---

## 🧪 Testing Tools

|#|Tool|What it is / Why you use it|Common Use Case|Example|
|---|---|---|---|---|
|1|`vitest`|Fast Vite-native test runner|Unit testing modern apps|`vitest run`|
|2|`jest`|Popular testing framework|Unit + integration tests|`jest`|
|3|`mocha`|Flexible test framework|Custom testing setups|`mocha tests/`|
|4|`playwright`|Browser automation testing|E2E testing|`playwright test`|
|5|`cypress`|Frontend E2E testing tool|UI testing in browser|`cypress open`|
|6|`puppeteer`|Headless Chrome automation|Scraping, testing|`node script.js`|
|7|`react testing library`|React component testing|Test UI behavior|`npm test`|

---
# 📦 NPM Utilities & Tools

| #   | Package              | What it is / Why you use it           | Common Use Case                          | Example                            |
| --- | -------------------- | ------------------------------------- | ---------------------------------------- | ---------------------------------- |
| 1   | `axios`              | Promise-based HTTP client             | Call external APIs from backend/frontend | `axios.get('/users')`              |
| 2   | `lodash`             | Utility library for data manipulation | Work with arrays/objects easily          | `_.merge(obj1, obj2)`              |
| 3   | `date-fns`           | Modern date utility library           | Format and manipulate dates              | `format(new Date(), 'yyyy-MM-dd')` |
| 4   | `dayjs`              | Lightweight alternative to moment     | Parse/format dates                       | `dayjs().format()`                 |
| 5   | `async`              | Utilities for async control flow      | Run parallel/series tasks                | `async.parallel([...])`            |
| 6   | `rxjs`               | Reactive programming with streams     | Handle events/data streams               | `fromEvent(btn, 'click')`          |
| 7   | `jsonwebtoken`       | JWT creation & verification           | Auth systems (login tokens)              | `jwt.sign(payload, secret)`        |
| 8   | `bcrypt`             | Password hashing library              | Secure user passwords                    | `bcrypt.hash(password, 10)`        |
| 9   | `multer`             | Middleware for file uploads           | Handle multipart/form-data               | `upload.single('file')`            |
| 10  | `uuid`               | Generate unique IDs                   | Create identifiers                       | `uuid.v4()`                        |
| 13  | `nodemon`            | Auto-restart Node app on changes      | Dev server workflow                      | `nodemon app.js`                   |
| 14  | `dotenv`             | Load env variables from `.env`        | Manage secrets/config                    | `require('dotenv').config()`       |
| 15  | `cross-env`          | Cross-platform env variables          | Fix Windows/Linux env issues             | `cross-env NODE_ENV=prod`          |
| 16  | `nodemailer`         | Send emails via SMTP                  | Build email systems                      | `transporter.sendMail()`           |
| 18  | `joi`                | Schema validation library             | Validate request data                    | `schema.validate(data)`            |
| 19  | `morgan`             | HTTP request logger                   | Log incoming requests                    | `app.use(morgan('dev'))`           |
| 20  | `moment`             | Legacy date library                   | Old projects date handling               | `moment().format()`                |
| 21  | `classnames`         | Conditional class builder             | Clean UI class logic                     | `classnames('btn', active)`        |
| 22  | `ioredis`            | Redis client                          | Caching, queues                          | `redis.set('key', 'value')`        |
| 23  | `connect-redis`      | Redis session store                   | Store sessions in Redis                  | `new RedisStore()`                 |
| 24  | `express-rate-limit` | Rate limiting middleware              | Prevent abuse/DDOS                       | `rateLimit({ windowMs })`          |
| 25  | `body-parser`        | Parse request body                    | Read JSON/form data                      | `app.use(bodyParser.json())`       |
| 26  | `cookie-parser`      | Parse cookies                         | Access request cookies                   | `req.cookies`                      |
| 27  | `express-session`    | Session middleware                    | Manage user sessions                     | `app.use(session({...}))`          |
| 28  | `node-cron`          | Schedule jobs in Node.js              | Run tasks periodically                   | `cron.schedule('* * * * *')`       |
| 29  | `zod`                | TypeScript-first schema validation    | Validate request data with type safety   | `schema.parse(req.body)`           |
| 30  | `yup`                | Schema validation library             | Validate forms or API payloads           | `schema.validate(data)`            |
| 31  | `winston`            | Flexible logging system               | Log errors, events, and system activity  | `logger.info('Server started')`    |
| 32  | `helmet`             | Security middleware for Express       | Set secure HTTP headers                  | `app.use(helmet())`                |
| 33  | `cors`               | Middleware to enable CORS             | Allow frontend to access backend         | `app.use(cors())`                  |
