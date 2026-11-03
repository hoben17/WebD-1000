# WEBD 1000 — Micro-Activity 01: HTML Foundations — Your First Webpage

**Course:** WEBD 1000 — Website Development  
**Instructor:** Davis Boudreau  
**Series:** Building a Responsive Website — Activity 01 of 12  
**Target time:** 30 minutes (allow additional setup time if Git/GitHub is new)  
**Level:** Complete beginner  
**Learning outcome:** Develop standards-compliant websites using HTML and CSS  
**Assessment:** Formative; no separate Brightspace submission unless directed

## What you will accomplish

You will create a GitHub repository named for **your own website project**, clone it to your computer, organize an activity folder, create an HTML page, connect a CSS stylesheet, test changes in a browser, and commit and push your work.

**Expected result:** A webpage with a main heading, introductory paragraphs, a light background, and a blue heading. Your own text and colours may differ.

> **Learning approach:** This is guided practice, not your finished semester website. The `activities/` folder stores learning checkpoints. Later, you will independently apply the techniques to your project website.

## 1. Understand: What are HTML and CSS? (3 minutes)

A browser reads files to display a webpage. **HTML (HyperText Markup Language)** describes the meaning and structure of the content. **CSS (Cascading Style Sheets)** describes how that content looks.

```html
<h1>My First Website</h1>
<p>Welcome to my website!</p>
```

`<h1>` identifies the page's primary heading. `<p>` identifies a paragraph. Most HTML elements have an **opening tag**, **content**, and a **closing tag**. For example, `<p>` opens a paragraph and `</p>` closes it.

```css
h1 {
    color: #004780;
}
```

This CSS rule makes the text of `h1` elements blue. CSS does **not** replace the heading text: it changes its presentation.

**Predict:** If you change the words between `<h1>` and `</h1>`, will the heading's colour change, or only its wording?

## 2. Prepare: Create and clone your project repository (6 minutes)

### Why use a repository?

A **Git repository** tracks changes to files over time. **GitHub** hosts a copy of your repository online. **Cloning** downloads that repository to your computer so you can work in VS Code. Later, **committing** records a snapshot of your changes, and **pushing** uploads those commits to GitHub.

1. Think of a topic for your semester website, such as a local tourism guide, a portfolio, or a community organization.
2. Sign in to [GitHub](https://github.com) and create a **new repository** with a descriptive, lowercase, hyphenated name, such as `cape-breton-travel-guide`.
3. Choose **Public** if you intend to publish using GitHub Pages; do not include personal or confidential information.
4. Initialize the repository with a **README** and create it.
5. On the repository page, choose **Code → HTTPS** and copy the clone URL.
6. Open **VS Code**, press **Ctrl+Shift+P**, choose **Git: Clone**, paste the URL, and choose a local parent folder.
7. When prompted, **Open** the cloned repository in VS Code. Complete GitHub sign-in if requested.

> **Checkpoint:** In VS Code's Explorer, you should see the repository folder and `README.md`. If `Git: Clone` is unavailable, Git may need to be installed or configured; ask your instructor for help rather than creating an unrelated folder.

## 3. Organize: Create the activity files (3 minutes)

### Why separate folders?

Every activity will use a file named `index.html`. This is safe because each activity has its **own folder**. You can compare versions without overwriting earlier work. `index.html` is the conventional default webpage filename for a directory.

In VS Code's Explorer:

1. Right-click the repository folder and choose **New Folder** → `activities`.
2. Inside `activities`, create `activity-01-html-foundations`.
3. Inside that folder, create **two files**: `index.html` and `activity.css`.

```text
cape-breton-travel-guide/        ← example: use YOUR repository name
├── README.md
└── activities/
    └── activity-01-html-foundations/
        ├── index.html
        └── activity.css
```

**File management rule:** Use lowercase names and hyphens; avoid spaces and names like `index-final-v2.html`. In Activity 02, you will copy the completed files into a **new** activity folder.

## 4. Build: Write your HTML document (5 minutes)

### Theory at the point of use: How is an HTML document organized?

An HTML document has two major parts:

- **`<head>`** contains information *about* the page, including its title, character encoding, mobile viewport setting, and stylesheet reference.
- **`<body>`** contains the page's visible content, including headings and paragraphs.

The first line, `<!DOCTYPE html>`, tells the browser to use modern HTML. `<html lang="en">` identifies the document language. The `<meta name="viewport">` element helps browsers size the page appropriately on mobile devices.

Open `activities/activity-01-html-foundations/index.html` and enter:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="An introduction to my website project.">
    <title>My First Website</title>
    <link rel="stylesheet" href="activity.css">
</head>
<body>
    <h1>My First Website</h1>
    <p>Welcome to my website!</p>
    <p>This is my first webpage built with HTML and CSS.</p>
</body>
</html>
```

Save with **Ctrl+S**.

### Theory at the point of use: How does the stylesheet link work?

```html
<link rel="stylesheet" href="activity.css">
```

- **`link`** connects this HTML document to another resource.
- **`rel="stylesheet"`** identifies the resource as a CSS stylesheet.
- **`href="activity.css"`** gives the file's location. This is a **relative path**: the browser looks in the same folder as `index.html`.

**Predict:** What would happen if the CSS file were named `styles.css` but the HTML still referred to `activity.css`?

## 5. Build: Learn CSS selectors and style the page (5 minutes)

### Theory at the point of use: What is a CSS selector?

A **selector** tells the browser **which HTML elements** a rule should style. A CSS rule has a selector, curly braces, and one or more **declarations**. Each declaration contains a **property** and a **value**, separated by a colon and usually followed by a semicolon.

```css
h1 {                     /* selector: all h1 elements */
    color: #004780;      /* property: value; */
}
```

Read this as: **“Select every `h1` element and make its text colour `#004780`.”**

| CSS part | Example | Meaning |
|---|---|---|
| Selector | `h1` | Which HTML elements to style |
| Opening/closing braces | `{` and `}` | Where this rule begins and ends |
| Property | `color` | What appearance to change |
| Value | `#004780` | The chosen setting (a hexadecimal colour) |
| Declaration | `color: #004780;` | One complete styling instruction |
| Semicolon | `;` | Ends the declaration |

### Why `body` and `h1`?

- `body` is a **type selector** that matches the `<body>` element. Its `background-color` fills the page background, while its text colour and font normally **inherit** into descendant elements, including paragraphs and headings.
- `h1` is another type selector, matching **every `<h1>`** on the page. Its `color` declaration sets the heading's text colour specifically, overriding the inherited body text colour.
- `background-color` changes the background; `color` changes the text. These are different properties.
- A colour such as `#004780` is a **hexadecimal colour value**. You do not need to memorize its digits.

Open `activity.css` and enter:

```css
/* Styles for Activity 01 */
body {
    background-color: #edf2f7;
    color: #14253a;
    font-family: Arial, sans-serif;
}

h1 {
    color: #004780;
}
```

Save with **Ctrl+S**.

**Notice:** The text between `/*` and `*/` is a **CSS comment**. It helps humans understand the file and does not change the page's appearance.

**Predict before testing:** Will the paragraph text be blue like the heading, or dark like the `body` rule? Why?

## 6. Run, test, and debug (4 minutes)

### Open the page

**Option A — Live Server:** If installed, right-click this activity's `index.html` in VS Code and select **Open with Live Server**.

**Option B — Browser:** In your computer's File Explorer, navigate to the activity folder and double-click `index.html`.

You should see a heading and two paragraphs, with a pale background and a blue heading.

### Test A — HTML content

Change `<h1>My First Website</h1>` to `<h1>Welcome to My Website Project</h1>`. Save and refresh. **Only the words should change**; the `h1` selector still matches the element.

### Test B — CSS property value

Change `background-color: #edf2f7;` to `background-color: #ffffff;`. Save and refresh. The page background should turn white. Restore the original value if you prefer.

### Test C — CSS selector

Temporarily change the selector `h1` to `p`, leaving its `color: #004780;` declaration in place. Save and refresh. **The paragraphs should become blue**, because `p` selects paragraph elements. Change the selector back to `h1` afterward.

**This is the key lesson:** The **selector** determines *what* is styled; the **property and value** determine *how* it is styled.

### Troubleshooting

| Problem | Check |
|---|---|
| Page is blank | Did you save `index.html`? Did you open the correct activity folder? |
| Heading or paragraphs missing | Are the elements inside `<body>`? Are the opening and closing tags correct? |
| CSS has no effect | Is `activity.css` in the same folder? Does the `<link>` filename match exactly? |
| Latest change is not visible | Save both files and refresh the browser |
| Unexpected elements are blue | Check whether the selector is `h1`, `p`, or `body` |

## 7. Apply independently (2 minutes)

Without copying a new example, make these three changes:

- [ ] Change the `<h1>` heading to your **own project name**.
- [ ] Add another `<p>` paragraph explaining what visitors will find on your future website.
- [ ] Change the heading's `color` value to another colour. Explain to yourself why this does not change the paragraphs.

Save and refresh after each change.

## 8. Commit and push (2 minutes)

1. Open **Source Control** in VS Code.
2. Review your changed files, then stage them using **Stage All Changes** or the **+** controls.
3. Enter the commit message `Activity 01 - HTML foundations`.
4. Select **Commit**, then **Push** or **Sync Changes**.
5. Open your repository on GitHub and verify that both files appear under `activities/activity-01-html-foundations/`.

> **Why commit?** A commit records a named checkpoint in your project's history. **Why push?** Pushing sends that checkpoint to GitHub, where it can be reviewed or recovered.

## Completion checkpoint

- [ ] I created a project-specific GitHub repository and cloned it into VS Code.
- [ ] I created `activities/activity-01-html-foundations/`.
- [ ] My folder contains `index.html` and `activity.css`.
- [ ] My browser displays my heading and paragraphs.
- [ ] I can explain the difference between HTML and CSS.
- [ ] I can identify a CSS selector, property, and value.
- [ ] I tested what happens when the CSS selector changes from `h1` to `p`.
- [ ] My completed files are committed and visible on GitHub.

## Quick reflection

Answer these briefly in your learning notes or be prepared to explain them during class:

1. What is the difference between HTML and CSS?
2. What does the `h1` selector match? What does the `p` selector match?
3. Why do paragraphs normally use the `body` text colour while the heading is blue?
4. What does `href="activity.css"` tell the browser?
5. What problem did you encounter, and how did you solve it?

**Submission:** Keep the files and Git history as evidence of practice. No separate Brightspace submission is required unless directed by your instructor.

## Next activity — 02: Semantic Header and Navigation

Create `activities/activity-02-header-navigation/` and **copy** the completed `index.html` and `activity.css` from Activity 01 into it. Do not move or overwrite the originals. You will learn what semantic HTML means and add a header, site branding, and navigation links.

---

### Instructor note: Workplan alignment

Place this series under **WS03 — Semantic HTML & Multi-Page Website Development (Week 5)**, with the subsequent activities cross-referenced in CSS foundations (WS04), responsive layouts (WS05), and QA (WS06). For a time-constrained class, run the activities as an accelerated recovery lab. Keep assessment within existing workshops and project milestones rather than creating 12 new graded submissions.

**Timing guidance:** The section times total 30 minutes. Git/GitHub first-time installation, authentication, or access problems may require additional setup time; provide a preconfigured repository or instructor checkpoint when necessary.
