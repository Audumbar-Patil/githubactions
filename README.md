## 🚀 Automated CI/CD for Static Website using GitHub Actions

I have implemented a complete CI/CD workflow for deploying and hosting a **static website** (HTML, CSS, JS) using **GitHub Actions**. Below are the steps I followed to automate the deployment process:

---

### 🔧 Project Setup

1. **Created a GitHub repository** for my portfolio/static site.
2. Added my project files (`index.html`, `style.css`, `script.js`, etc.).
3. Pushed the project to the `main` branch.

---

### ⚙️ GitHub Actions Workflow Configuration

I created a GitHub Actions workflow file in:

```
.github/workflows/deploy.yml
```

#### Sample Workflow File:

```yaml
name: 🚀 Deploy Static Website

on:
  push:
    branches:
      - main  # Trigger on push to main

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest

    steps:
    - name: 📥 Checkout repository
      uses: actions/checkout@v3

    - name: 📦 Upload site to GitHub Pages
      uses: peaceiris/actions-gh-pages@v3
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./  # Root directory for HTML/CSS/JS files
```

> 💡 I used the `peaceiris/actions-gh-pages` action for seamless GitHub Pages deployment.

---

### 🌐 GitHub Pages Hosting

1. Enabled **GitHub Pages** from the repository settings.
2. Selected `gh-pages` branch as the **deployment source**.
3. After a push to `main`, GitHub Actions builds and deploys automatically to GitHub Pages.

---

### ✅ Result

* Any changes I push to the `main` branch trigger the workflow.
* The latest version is automatically deployed and live at:

  ```
  https://<your-github-username>.github.io/<your-repo-name>/
  ```

---

### 🛠️ Tech Stack

* HTML5, CSS3, JavaScript
* GitHub Actions (CI/CD)
* GitHub Pages (Hosting)
