

## What is `require()`? (Hinglish)

**`require()` Node.js ka function hai**
Jo kisi **module / file / package ko import (load)** karne ke kaam aata hai.

👉 Simple words mein:

> **"require() bolta hai → bhai is file / module ka code mujhe de do"**

---

## Basic Syntax

```js
const something = require('module-name');
```

* `require()` → module load karta hai
* `something` → us module ka exported data

---

## Example 1️⃣ Built-in Module

```js
const fs = require('fs');
```

* `fs` = File System module
* Ye Node.js ke saath **already aata hai**

👉 Matlab:
**"fs module ko memory mein load karo"**

---

## Example 2️⃣ Local File Import

```js
const math = require('./math.js');
```

* `./` ka matlab → current folder
* `math.js` ek **local file** hai

### math.js

```js
module.exports.add = (a, b) => a + b;
```

### main file

```js
console.log(math.add(2, 3)); // 5
```

👉 `require()` ne `module.exports` ka data return kiya

---

## Example 3️⃣ NPM Package

```js
const express = require('express');
```

* `express` → npm se install hua package
* Node.js `node_modules` folder mein dhundhta hai

---

## How `require()` Works Internally 🧠

Jab Node.js dekhta hai:

```js
require('fs')
```

To ye steps follow karta hai:

1. Check karta hai → **built-in module?**
2. Nahi mila → **local file?**
3. Nahi mila → **node_modules?**
4. Load karta hai code
5. `module.exports` return karta hai
6. Cache mein store karta hai (dobara load nahi hota)

---

## Important Concept: `module.exports`

```js
module.exports = {
  name: "Krishna",
  role: "Developer"
};
```

```js
const user = require('./user');
console.log(user.name);
```

👉 `require()` **hamesha `module.exports` ka value deta hai**

---

## Common Mistake ❌

```js
require('math.js'); ❌
```

Correct:

```js
require('./math.js'); ✅
```

👉 Local file ke liye **`./` zaroori hai**

---

## `require()` vs `import`

| require()        | import       |
| ---------------- | ------------ |
| CommonJS         | ES Module    |
| Node.js default  | Modern JS    |
| Runtime load     | Compile-time |
| Older but stable | New & clean  |

Example:

```js
import fs from 'fs';
```

---

## Real-Life Analogy 😄

> `require()` =
> Library mein jaake bolna:
> **"Mujhe ye book chahiye, abhi!"**

---

## Summary 🔥

* `require()` = module load karne ka function
* Built-in, local, ya npm packages ke liye
* `module.exports` return karta hai
* Node.js ka **CommonJS system**


