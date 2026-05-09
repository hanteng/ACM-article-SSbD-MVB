# README

A step-by-step writing a research project (doctoral level) using the ACM article template provided by Quarto article template.

## Instructions 

Using **Positron** (the new, language-agnostic IDE from Posit) with **Quarto** is a highly efficient way to manage academic manuscripts. Because Positron has a built-in terminal and first-class Quarto support, you can move from a `.docx` mindset to a professional **ACM journal** output seamlessly.

Here is the step-by-step guide to setting up the ACM template using the modern **Typst** engine (which is faster and simpler than LaTeX) within Positron.

---

### **Step 1: Open Positron & Prepare Your Project**

1. Launch **Positron**.
2. Go to `File > Open Folder...` and create/select a folder for your research project (e.g., `AI-Semiconductor-Abstract`).
3. Open the **Terminal** in Positron (usually at the bottom, or use `Ctrl + ~`).

### **Step 2: Install the ACM Typst Template**

Instead of manually downloading files, use the Quarto CLI directly in the Positron terminal. Run the following command:

```bash
quarto use template quarto-journals/acm

```

* **What this does:** It downloads the official ACM format files, including the necessary styles for both PDF (via Typst) and Word.
* **Prompt:** It will ask if you want to create a subdirectory. Type `Y` and give it a name like `acm-abstract`.


### **Step 3a: Initialize Git in your Project**

Follow these steps to connect it to a new GitHub repository.

If you haven't initialized Git in your folder yet:

1. In Positron, open the **Terminal** (`Ctrl + ~`).
2. Type: `git init -b main`
3. Stage and commit your current files:
```bash
git add .
git commit -m "Initial commit: ACM Extended Abstract setup"

```

### **Step 3b: Create a Repository on GitHub**

1. Go to [github.com](https://github.com) and log in.
2. Click the **+** icon in the top right and select **New repository**.
3. Name it (e.g., `ai-semiconductor-abstract`).
4. **Important:** Leave "Initialize this repository with..." (README, .gitignore, license) **unchecked**. Since you already have code locally, you want a blank slate.
5. Click **Create repository**.

### **Step 3b: Connect Positron to GitHub**

GitHub will show you a page with "Quick setup." Look for the section titled **"…or push an existing repository from the command line"**.

Copy the three lines provided there and paste them into your **Positron Terminal**:

```bash
git remote add origin https://github.com/hanteng/ACM-article-SSbD-MVB.git
git branch -M main
git push -u origin main

```

*(You may be prompted to log in via a browser popup to authorize Positron.)*

---

### **Step 4: Using the Graphical Interface (The "Easy" Way)**

Once that connection is made, you don't need the terminal for daily work.

1. Look at the **Left Sidebar** in Positron. Click the **Source Control** icon (the one that looks like a small branch/node).
2. When you make changes to your abstract:
* Click the **+** icon next to the file to "Stage" it.
* Type a message in the box (e.g., "Updated method section").
* Click **Commit**.
* Click **Sync Changes** (or the "Cloud" icon) at the bottom left to push to GitHub.

### **Pro-Tip for arXiv/SSRN**

Since you are working with Quarto, I recommend adding a `.gitignore` file to your project so you don't clutter GitHub with temporary build files. Create a new file named `.gitignore` and add these lines:

```text
/.quarto/
/index_files/
*_files/
*.log
*.aux

```

This keeps your GitHub repository clean, showing only your source `.qmd` and your final `.pdf` or `.docx`.

### **Step 5: Test Generateing .pdf and .docx **
