# Semantic HTML

  

---

  

## 1. **What is HTML?**

  

HTML (HyperText Markup Language) is the skeleton of the web. It tells the browser what content looks like.

  

But before we build, we must understand **tags**. HTML uses "tags" to wrap content.

  

```html

<tagname id="" disabled >Content goes here...</tagname>

````

  

---

  

> [!info]

>

> **Key Concept:**

>

> A web page isn't just a picture; it is a document. Computers (like Google bots and Screen Readers for the blind) need to read this document to understand what is a title, what is a button, and what is just a paragraph.

  

---

  

## 2. **What is "Semantic" HTML?**

  

"Semantic" means _relating to meaning_.

  

When writing Semantic HTML, you choose tags that describe **what the content is**, not just how it looks.

  

---

  

```ad-tldr

- **Non-Semantic:** Tells the browser "put this in a box." (e.g., `<div>`, `<span>`)

- **Semantic:** Tells the browser "this is a navigation menu" or "this is a main article." (e.g., `<nav>`, `<article>`)

```

  

---

  

## 3. **The "Div Soup" Problem**

  

In the past, developers used the `<div>` tag for everything. A `<div>` is a generic container with no meaning.

  

**Bad (Non-Semantic) Example:**

  

```html

<div id="header">

  <div class="title">My Website</div>

  <div class="menu">

     <div>Home</div>

     <div>About</div>

  </div>

</div>

```

  

If a blind user visits this page, their screen reader just says: _"Group. Group. My Website. Group. Group. Home..."_ It's confusing!

  

---

  

### 4. **Core Semantic Layout Elements**

  

Instead of `<div>`, we use specific tags to define the major areas of a webpage.

  

---

  

| **Tag**     | **Description**                                                  |

| ----------- | ---------------------------------------------------------------- |

| `<header>`  | The introductory content (logos, title).                         |

| `<nav>`     | A section containing navigation links.                           |

| `<main>`    | The dominant content of the specific page.                       |

| `<footer>`  | Copyright, contact info, usually at the bottom.                  |

| `<article>` | A self-contained piece of content (like a blog post).            |

| `<aside>`   | Content related to the main story but separate (like a sidebar). |

  

---

  

> [!tip]

>

> Think of these tags like rooms in a house. You wouldn't call the kitchen, bedroom, and bathroom just "Room 1", "Room 2", and "Room 3". You give them specific names so people know what to do inside them.

  

---

  

### 5. **Text Hierarchy (Headings & Paragraphs)**

  

Semantics applies to text, too.

  

**Headings (`<h1>` to `<h6>`)**

  

Headings create an outline of your page.

  

- `<h1>`: The main topic of the page (Use only one per page!).

- `<h2>`: Major sections.

- `<h3>`: Sub-sections.

  

**Paragraphs (`<p>`)**

  

Use `<p>` for blocks of text.

  

---

  

> [!warning]

>

> **Do not** use headings just to make text big and bold.

>

> **Do not** use `<b>` or `<strong>` to make headings.

>

> Browsers use headings to generate a "Table of Contents" for users with disabilities.

  

---

  

### 6. **Interactive Elements: Links vs. Buttons**

  

A very common mistake for beginners is confusing links and buttons.

  

- **`<a>` (Anchor/Link):** Use this when moving the user to a **new page** or a different place on the current page.

- **`<button>`:** Use this when performing an **action** (submitting a form, opening a menu, playing a video).

  

```html

<a href="about.html">Go to About Page</a>

<button>Submit Form</button>

  

<div onclick="goToPage()">Go to About Page</div>

```

  

---

  

### 7. **Project Setup**

  

Let's build a simple, semantically correct blog page.

  

#### **Directory Structure**

  

```

project/

└── index.html

```

  

---

### **Code Walkthrough**

  

Open `index.html`. Here is how we structure a semantic document.

  

```html

<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <title>My Semantic Blog</title>

</head>

<body>

  

    <header>

        <h1>My Coding Journey</h1>

        <nav>

            <ul>

                <li><a href="#home">Home</a></li>

                <li><a href="#posts">Posts</a></li>

                <li><a href="#contact">Contact</a></li>

            </ul>

        </nav>

    </header>

  

    <main>

        <article>

            <h2>Understanding Semantics</h2>

            <p>Today I learned why semantics matter.</p>

            <p>It helps accessibility and SEO (Search Engine Optimization).</p>

        </article>

  

        <article>

            <h2>My First Code</h2>

            <p>I wrote my first HTML tag today!</p>

        </article>

  

    </main>

  

    <aside>

        <h3>About Me</h3>

        <p>I am a student learning web development.</p>

    </aside>

  

    <footer>

        <p>&copy; 2023 My Semantic Blog</p>

    </footer>

  

</body>

</html>

```

  

---

  

> [!info]

>

> Notice how we didn't use a single `<div>`? We used tags that describe exactly what the data is. A browser reading this knows exactly where the navigation ends and the main article begins.

  

---

  

### **Activities:**

  

1. **The Refactor Challenge:**

    Take the following "Div Soup" code and rewrite it using the correct Semantic HTML tags

    ```html

    <div class="top-bar">

        <span class="big-text">Welcome</span>

    </div>

    <div class="content">

        <div class="story">

           <div class="story-title">My Day</div>

           <div class="story-text">It was good.</div>

        </div>

    </div>

    <div class="clickable-box" onclick="like()">Like This Post</div>

    ```

---

```ad-answer

collapse:

  

- `.top-bar` -> `<header>`

  

- `.big-text` -> `<h1>`

  

- `.content` -> `<main>`

  

- `.story` -> `<article>`

  

- `.story-title` -> `<h2>`

  

- `.story-text` -> `<p>`

  

- `.clickable-box` -> `<button>`

```

---

  

2. **Validate Your Code:**

    Use an online validator to check if your HTML is written correctly.

  

---

  

### **Resources:**

  

- [MDN Web Docs - HTML Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics): The official bible of web development.

- [W3C Validator](https://validator.w3.org/): A tool to check if your HTML has errors.

- [HTML5 Doctor](http://html5doctor.com/): Articles explaining exactly when to use specific tags.