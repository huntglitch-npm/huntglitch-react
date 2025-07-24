
<h1 align="left">
  react-huntglitch
  <img src="https://app.huntglitch.com/images/logo.svg" align="right" width="140" height="140"/>
</h1>

<p>
  A lightweight and elegant utility for sending error logs to the <a href="https://huntglitch.com">HuntGlitch</a> logging service — built for React apps with support for both JavaScript and TypeScript.
</p>

![npm](https://img.shields.io/npm/v/react-huntglitch)
![downloads](https://img.shields.io/npm/dt/react-huntglitch)
![license](https://img.shields.io/npm/l/react-huntglitch)
![typescript](https://img.shields.io/badge/TS-Supported-blue)

---

## 🚀 Features

- 🔁 Centralized error logging with promise-based feedback
- 🧠 Intelligently categorizes logs by severity
- ⚙️ Supports custom log levels (`debug`, `info`, `warning`, `error`, etc.)
- ⚡ Quick setup via `.env` keys
- 📦 Supports both JavaScript & TypeScript projects
- 🌐 Lightweight for client-side usage in React apps
- 🔐 Secure delivery via HuntGlitch keys

---

## 📦 Installation

```bash
npm install react-huntglitch
```

---

## ⚙️ Environment Setup

Create a `.env` file in your project root:

```env
PROJECT_KEY=your_project_key
DELIVERABLE_KEY=your_deliverable_key
```

> 🔐 You can find these keys in your HuntGlitch dashboard:  
> https://app.huntglitch.com

---

## ✨ Usage

### JavaScript / TypeScript

```js
import Log from "react-huntglitch";

try {
  throw new Error("Something went wrong!");
} catch (error) {
  Log({
    error,
    logType: 5, // Optional, defaults to 5 (Error)
  })
    .then(() => console.log("✅ Log sent successfully."))
    .catch(() => console.error("❌ Failed to send log."));
}
```

---

## 📋 Props Reference

| Prop       | Type    | Required | Description                                                              | Example |
|------------|---------|----------|--------------------------------------------------------------------------|---------|
| `error`    | object  | ✅        | JavaScript error object to be logged                                     | `error` |
| `logType`  | number  | ❌        | Log level: `1=debug`, `2=warning`, `3=notice`, `4=info`, `5=error`       | `5`     |

---


## 🛠 Best Practices

- Wrap all async operations and business logic in `try...catch` blocks.
- Send contextual information (user IDs, request data, etc.) via enriched `Error` objects.
- Use different `logType` values to categorize errors for better filtering in HuntGlitch.

---

## 🙌 Special Thanks

Inspired by [HuntGlitch](https://app.huntglitch.com) — built to make error logging clean, centralized, and developer-friendly.

> If you like this package, consider starring ⭐ the GitHub repo or sharing feedback!

---

## 📃 License

MIT © [HuntGlitch](https://huntglitch.com)
