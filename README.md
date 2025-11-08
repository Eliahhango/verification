<div align="center">

# 🔍 GitHub Repo Verification

<img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=22&duration=3000&pause=1000&color=2E9EF7&center=true&vCenter=true&width=435&lines=Check+if+repos+are+forked!;Simple+%26+Fast+Verification;No+Dependencies+Needed!" alt="Typing SVG" />

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)
[![GitHub](https://img.shields.io/badge/GitHub-Eliahhango-black?style=for-the-badge&logo=github)](https://github.com/Eliahhango/verification)
[![Stars](https://img.shields.io/github/stars/Eliahhango/verification?style=for-the-badge&logo=github)](https://github.com/Eliahhango/verification/stargazers)

<img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif" width="700">

</div>

---

## ✨ What It Does

<img align="right" alt="Coding" width="400" src="https://user-images.githubusercontent.com/74038190/229223263-cf2e4b07-2615-4f87-9c38-e37600f8381a.gif">

This tool checks whether any GitHub repository is a **fork** or an **original repository** using the GitHub API.

**Perfect for:**
- 🎯 Repository verification
- 🔎 Fork detection
- 📊 Repository analysis
- 🚀 Quick checks

<br clear="right"/>

---

## 🚀 Quick Start

### 1️⃣ Clone or Download

```bash
git clone https://github.com/Eliahhango/verification.git
```

<div align="center">
<img src="https://user-images.githubusercontent.com/74038190/212284087-bbe7e430-757e-4901-90bf-4cd2ce3e1852.gif" width="100">
</div>

### 2️⃣ Use in Your Project

<details>
<summary><b>📱 Option A: Standalone Usage</b></summary>

```bash
# Simply open the HTML file in your browser
open index.html
```
</details>

<details>
<summary><b>🌐 Option B: Integrate into Your Web Project</b></summary>

Copy the HTML file into your project:
```
your-project/
  ├── index.html
  └── verification.html  ← Add this file
```
</details>

<details>
<summary><b>🔗 Option C: Embed in Your Website</b></summary>

```html
<!-- In your existing HTML -->
<iframe src="verification.html" width="100%" height="400px"></iframe>
```
</details>

<details>
<summary><b>⚡ Option D: Extract the JavaScript Function</b></summary>

```javascript
// Add this function to your JavaScript file
async function checkForkedRepo(username, repo) {
    const response = await fetch(`https://api.github.com/repos/${username}/${repo}`);
    const data = await response.json();
    return data.fork;
}

// Usage example
const isForked = await checkForkedRepo('Eliahhango', 'verification');
console.log(isForked ? "Forked repo" : "Original repo");
```
</details>

---

## 📝 Usage Examples

<img src="https://user-images.githubusercontent.com/74038190/212284115-f47cd8ff-2ffb-4b04-b5bf-4d1c14c0247f.gif" width="1000">

### 🎨 Example 1: Basic Implementation

```html
<!DOCTYPE html>
<html>
<head>
    <title>My Project</title>
</head>
<body>
    <input type="text" id="username" placeholder="Username">
    <input type="text" id="repo" placeholder="Repository">
    <button onclick="checkRepo()">Check</button>
    <p id="result"></p>

    <script>
        async function checkForkedRepo(username, repo) {
            const response = await fetch(`https://api.github.com/repos/${username}/${repo}`);
            const data = await response.json();
            return data.fork;
        }

        async function checkRepo() {
            const username = document.getElementById('username').value;
            const repo = document.getElementById('repo').value;
            const isForked = await checkForkedRepo(username, repo);
            document.getElementById('result').innerText = 
                isForked ? "✓ This is a forked repo" : "✗ This is an original repo";
        }
    </script>
</body>
</html>
```

### ⚛️ Example 2: React Integration

```jsx
import React, { useState } from 'react';

function RepoChecker() {
    const [result, setResult] = useState('');

    const checkForkedRepo = async (username, repo) => {
        const response = await fetch(`https://api.github.com/repos/${username}/${repo}`);
        const data = await response.json();
        return data.fork;
    };

    const handleCheck = async () => {
        const username = document.getElementById('username').value;
        const repo = document.getElementById('repo').value;
        const isForked = await checkForkedRepo(username, repo);
        setResult(isForked ? "Forked repo" : "Original repo");
    };

    return (
        <div>
            <input id="username" placeholder="Username" />
            <input id="repo" placeholder="Repository" />
            <button onClick={handleCheck}>Check</button>
            <p>{result}</p>
        </div>
    );
}
```

### 🖥️ Example 3: Node.js/Express Backend

```javascript
const express = require('express');
const axios = require('axios');
const app = express();

app.get('/check-fork/:username/:repo', async (req, res) => {
    const { username, repo } = req.params;
    try {
        const response = await axios.get(`https://api.github.com/repos/${username}/${repo}`);
        res.json({ 
            isForked: response.data.fork,
            message: response.data.fork ? "Forked repo" : "Original repo"
        });
    } catch (error) {
        res.status(500).json({ error: 'Failed to check repository' });
    }
});

app.listen(3000, () => console.log('Server running on port 3000'));
```

---

## 🎨 Customization

<img align="left" alt="Design" width="300" src="https://user-images.githubusercontent.com/74038190/212749447-bfb7e725-6987-49d9-ae85-2015e3e7cc41.gif">

Modify the styles to match your project:

```css
.container {
    max-width: 500px;
    margin: auto;
    padding: 30px;
    border-radius: 10px;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

button {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    border-radius: 5px;
    transition: transform 0.2s;
}

button:hover {
    transform: scale(1.05);
}
```

<br clear="left"/>

---

## 🔧 API Details

<div align="center">

| Endpoint | Method | Description |
|----------|--------|-------------|
| `https://api.github.com/repos/{username}/{repo}` | GET | Get repository info |

<img src="https://user-images.githubusercontent.com/74038190/212284136-03988914-d899-44b4-b1d9-4eeccf656e44.gif" width="400">

</div>

**Response includes:**
- ✅ `fork`: Boolean - true if forked, false if original
- 📦 `parent`: Object - parent repo details (if forked)
- 📊 Other repo metadata

---

## 📦 Features

<div align="center">

| Feature | Status |
|---------|--------|
| 🚀 No Dependencies | ✅ |
| 💻 Pure JavaScript | ✅ |
| 🎨 Customizable | ✅ |
| 📱 Responsive | ✅ |
| ⚡ Fast & Light | ✅ |

<img src="https://user-images.githubusercontent.com/74038190/212284158-e840e285-664b-44d7-b79b-e264b5e54825.gif" width="400">

</div>

---

## 🤝 Contributing

<img align="right" alt="Contribute" width="300" src="https://user-images.githubusercontent.com/74038190/212749695-a6817c5a-a794-462b-afca-1b5ce31a9846.gif">

Found a bug or have a feature idea? 

1. 🍴 Fork the repo
2. 🔧 Create your feature branch
3. 💾 Commit your changes
4. 📤 Push to the branch
5. 🎉 Open a Pull Request

[Open an issue](https://github.com/Eliahhango/verification/issues)

<br clear="right"/>

---

## 📄 License

<div align="center">

MIT License - feel free to use in any project!

<img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif" width="700">

</div>

---

<div align="center">

### 💖 Made with Love

<img src="https://user-images.githubusercontent.com/74038190/213844263-a8897a51-32f4-4b3b-b5c2-e1528b89f6f3.png" width="50px" /> &nbsp; **[Eliah Hango](https://github.com/Eliahhango)** &nbsp; <img src="https://user-images.githubusercontent.com/74038190/213844263-a8897a51-32f4-4b3b-b5c2-e1528b89f6f3.png" width="50px" />

<img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif" width="500">

⭐ **Star this repo if you find it useful!** ⭐

[![GitHub followers](https://img.shields.io/github/followers/Eliahhango?style=social)](https://github.com/Eliahhango)
[![GitHub stars](https://img.shields.io/github/stars/Eliahhango/verification?style=social)](https://github.com/Eliahhango/verification/stargazers)

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=100&section=footer"/>

</div>
