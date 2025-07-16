# ai-startup-website

# 🧠 Mini Project: Git Version Control Basics
---
## 📁 Part 1 — Project Setup

### 1. **Install Git**
- Go to [https://git-scm.com/](https://git-scm.com/)
- Download Git for your OS and install it.
![alt text](img/01.Git_Installed.png)

### 2. **Create a GitHub Repository**
- Sign in to [https://github.com](https://github.com)
- Click `+` → **New repository**
- Name it: `ai-startup-website`
- Initialize with a `README.md`
- Click **Create repository**
![alt text](image-2.png)
![alt text](image.png)

## 💻 Part 2 — Local Project Setup

### 3. **Clone the Repository**
```bash
mkdir -p ~/Desktop/darey-training/git-project
cd ~/Desktop/darey-training/git-project
git clone https://github.com/YOUR-USERNAME/ai-startup-website.git

![![alt text](image-4.png)alt text](image-1.png)
![alt text](image-3.png)
cd ai-startup-website
```
![alt text](image-5.png)
### 4. **Create `index.html` File**
```bash
echo "This is the Admin creating an index.html file for Tom and Jerry." > index.html
```
### 5. **Track and Push File**
```bash
git status
git add index.html
git commit -m "Initial commit: add index.html"
git push origin main
```---
## 👤 Part 3 — Tom’s Workflow

### 6. **Create a Branch**
```bash
git checkout -b update-navigation
```
### 7. **Edit File with Tom’s Message**
```bash
nano index.html
```
- Add: `This is Tom adding Navigation to the AI-website`
- Save: `Ctrl + O`, `Enter`, `Ctrl + X`
![alt text](img/06.staged-commited-pushed-admin-index.html-file.png)
### 8. **Stage, Commit & Push**
```bash
git add index.html
git commit -m "Tom added navigation section"
git push origin update-navigation
```---
## 👥 Part 4 — Jerry’s Workflow

### 9. **Return to Main & Pull**
```bash
git checkout main
git pull origin update-navigation

![alt text](image-6.png)
```
### 10. **Create New Branch**
```bash
git checkout -b add-contact-info
```
### 11. **Edit File with Jerry’s Message**
```bash
nano index.html
```
- Add: `Jerry’s contact info update`
- Save: `Ctrl + O`, `Enter`, `Ctrl + X`

### 12. **Stage, Commit & Push**
```bash
git add index.html
git commit -m "Jerry added contact info"
git push origin add-contact-info
```

# 🔀 Part 5 — Merging Branches into Main

### ✅ **Option A: Merge Without Conflict**

1. Switch to main:
```bash
git checkout main
git pull origin main
```

2. Merge Jerry’s branch:
```bash
git merge add-contact-info
```

3. Push merged result:
```bash
git push origin main
```

---

### ⚔️ **Option B: Merge With Conflict**

1. Still on main:
```bash
git merge add-contact-info
```

2. Git will report a conflict. Open file:
```bash
nano index.html
```

3. You’ll see something like:
```html
<<<<<<< HEAD
This is Tom adding Navigation to the AI-website
=======
Jerry’s contact info update
>>>>>>> add-contact-info
```

4. Manually edit to:
```html
This is Tom adding Navigation to the AI-website
Jerry’s contact info update
```

5. Save and exit:
`Ctrl + O`, `Enter`, `Ctrl + X`

6. Stage and complete merge:
```bash
git add index.html
git commit -m "Resolved conflict between Tom and Jerry's updates"
git push origin main
```

---

## 🔍 Part 6 — Confirm Everything on GitHub

1. Visit: [https://github.com/YOUR-USERNAME/ai-startup-website](https://github.com/YOUR-USERNAME/ai-startup-website)
2. Confirm:
   - `index.html` contains all updates
   - All branches are visible
   - All commits are listed
   - You can view pull requests if created

---
