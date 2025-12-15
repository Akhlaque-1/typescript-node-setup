## 📦 Prerequisites

Make sure you have:

* Node.js (v18+ recommended)
* npm (comes with Node.js)
* VS Code or any code editor

Check versions:

```bash
node -v
npm -v
```

---

## 1️⃣ Initialize Node.js Project

```bash
mkdir ts-functions-project
cd ts-functions-project
npm init -y
```

This creates `package.json`.

---

## 2️⃣ Install TypeScript Locally

```bash
npm install typescript --save-dev
```

Check TypeScript version:

```bash
npx tsc --version
```

---

## 3️⃣ Create TypeScript Configuration

```bash
npx tsc --init
```

Update `tsconfig.json`:

```json
"rootDir": "./src",
"outDir": "./dist",
"strict": true,
"esModuleInterop": true
```

* `rootDir` → where your TypeScript files are
* `outDir` → where compiled JavaScript files go
* `strict` → ensures type safety

---

## 4️⃣ Project Folder Structure

```text
ts-functions-project/
├── src/       ← TypeScript source files
│   └── app.ts ← main TypeScript file
├── dist/      ← Compiled JavaScript files
├── package.json
├── tsconfig.json
└── README.md
```

---

## 5️⃣ Create Your Main TypeScript File

File: `src/app.ts`

```ts
// Function with parameters and return type
function add(a: number, b: number): number {
  return a + b;
}

console.log(add(5, 10)); // Output: 15

// Function with optional parameter
function greet(name: string, greeting?: string): string {
  return `${greeting || 'Hello'}, ${name}!`;
}

console.log(greet('Akhlaque'));           // Output: Hello, Akhlaque!
console.log(greet('Akhlaque', 'Hi'));    // Output: Hi, Akhlaque!

// Arrow function
const multiply = (x: number, y: number): number => x * y;
console.log(multiply(4, 5)); // Output: 20
```

---

## 6️⃣ Compile TypeScript

```bash
npx tsc
```

Output files will be in the `dist/` folder.

---

## 7️⃣ Run Compiled JavaScript

```bash
node ./dist/app.js
```

---

## 8️⃣ Development Mode (Simplified)

Install `ts-node` for running TypeScript directly:

```bash
npm install ts-node --save-dev
```

Add scripts to `package.json`:

```json
"scripts": {
  "build": "tsc",
  "start": "node dist/app.js",
  "dev": "ts-node src/app.ts"
}
```

Run in dev mode:

```bash
npm run dev
```

Benefits:

* Run TypeScript directly without compiling first
* Simple for learning and small projects

---

## 9️⃣ Add `.gitignore` File

`.gitignore` prevents unnecessary files from being committed to GitHub.

Create `.gitignore` in project root:

```bash
touch .gitignore
```

Add the following to `.gitignore`:

```text
node_modules/
dist/
.env
*.log
.vscode/
.DS_Store
```

Save the file and commit:

```bash
git add .gitignore
git commit -m "Add .gitignore"
```

✅ Now your repository is clean and ready for GitHub.

---

## 🔧 Commands Summary

```bash
npm init -y
npm install typescript --save-dev
npx tsc --version
npx tsc --init
npx tsc
node ./dist/app.js
npm install ts-node --save-dev
npm run dev
touch .gitignore
git add .gitignore
git commit -m "Add .gitignore"

