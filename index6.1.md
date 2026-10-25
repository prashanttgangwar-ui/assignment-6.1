
## 1. Aim

To create a webpage containing three cards and understand the CSS Box Model by modifying content, padding, border, and margin. To compare `content-box` and `border-box` and inspect the box model using Chrome DevTools.

## 2. Files Required

Create a folder named `Assignment-6.1` and add these two files:

```text
Assignment-6.1/
├── index.html
└── style.css
```

## 3. HTML Code — `index.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Assignment 6.1 - Box Model Inspection</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <header class="page-header">
        <h1>CSS Box Model Inspection</h1>
        <p>Understanding Content, Padding, Border and Margin</p>
    </header>

    <main class="container">
        <section class="card card-one">
            <h2>Card 1: Content Box</h2>
            <p>
                This card uses box-sizing: content-box. Its specified width
                applies only to the content. Padding and border are added
                to the total rendered width.
            </p>
            <span class="label">box-sizing: content-box</span>
        </section>

        <section class="card card-two">
            <h2>Card 2: Border Box</h2>
            <p>
                This card uses box-sizing: border-box. Its specified width
                includes the content, padding, and border, making the
                overall dimensions easier to control.
            </p>
            <span class="label">box-sizing: border-box</span>
        </section>

        <section class="card card-three">
            <h2>Card 3: Custom Spacing</h2>
            <p>
                This card has different padding, border thickness, and
                margin. Inspect it in Chrome DevTools to see how each
                property affects its layout.
            </p>
            <span class="label">Custom padding, border and margin</span>
        </section>
    </main>

    <section class="explanation">
        <h2>The Four Parts of the CSS Box Model</h2>

        <div class="box-part">
            <h3>1. Content</h3>
            <p>The innermost area containing text, images, or other elements.</p>
        </div>

        <div class="box-part">
            <h3>2. Padding</h3>
            <p>The space between the content and the border.</p>
        </div>

        <div class="box-part">
            <h3>3. Border</h3>
            <p>The line surrounding the content and padding.</p>
        </div>

        <div class="box-part">
            <h3>4. Margin</h3>
            <p>The outer space separating an element from other elements.</p>
        </div>
    </section>

    <footer>
        <p>Assignment 6.1 | Web Development Practice</p>
    </footer>

</body>
</html>
```

## 4. CSS Code — `style.css`

```css
/* Basic page styling */
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: Arial, sans-serif;
    background-color: #f1f5f9;
    color: #1e293b;
    line-height: 1.6;
}

.page-header {
    background-color: #1d4ed8;
    color: white;
    text-align: center;
    padding: 30px 20px;
}

.page-header h1 {
    margin: 0 0 10px;
}

.page-header p {
    margin: 0;
}

.container {
    width: 90%;
    max-width: 1100px;
    margin: 35px auto;
}

/* Common card styles */
.card {
    width: 100%;
    max-width: 700px;
    background-color: white;
    border-radius: 8px;
}

.card h2 {
    margin-top: 0;
}

.label {
    display: inline-block;
    margin-top: 10px;
    padding: 5px 10px;
    background-color: #dbeafe;
    color: #1d4ed8;
    border-radius: 4px;
    font-size: 14px;
    font-weight: bold;
}

/* Card 1: content-box */
.card-one {
    box-sizing: content-box;
    width: 600px;
    padding: 20px;
    border: 5px solid #2563eb;
    margin: 20px 0 35px;
    background-color: #eff6ff;
}

/* Card 2: border-box */
.card-two {
    box-sizing: border-box;
    width: 600px;
    padding: 30px;
    border: 8px solid #16a34a;
    margin: 20px 0 35px;
    background-color: #f0fdf4;
}

/* Card 3: different padding, border and margin */
.card-three {
    box-sizing: border-box;
    width: 600px;
    padding: 15px 40px;
    border: 12px dashed #ea580c;
    margin: 45px 0 50px;
    background-color: #fff7ed;
}

/* Box model explanation section */
.explanation {
    width: 90%;
    max-width: 1100px;
    margin: 40px auto;
    padding: 25px;
    background-color: white;
    border: 2px solid #cbd5e1;
    border-radius: 8px;
}

.explanation h2 {
    color: #1d4ed8;
}

.box-part {
    margin: 15px 0;
    padding: 12px 18px;
    border-left: 5px solid #2563eb;
    background-color: #f8fafc;
}

.box-part h3 {
    margin: 0 0 5px;
}

.box-part p {
    margin: 0;
}

footer {
    text-align: center;
    background-color: #0f172a;
    color: white;
    padding: 15px;
    margin-top: 40px;
}

/* Responsive layout */
@media (max-width: 700px) {
    .card-one,
    .card-two,
    .card-three {
        width: 100%;
    }

    .container,
    .explanation {
        width: 92%;
    }

    .card-one,
    .card-two,
    .card-three {
        padding: 20px;
    }
}
```

## 5. Understanding the CSS Box Model

Every HTML element is treated as a rectangular box with four parts:

1. **Content:** The actual text, image, or other content.
2. **Padding:** Space between the content and the border.
3. **Border:** The boundary around the content and padding.
4. **Margin:** Space outside the border, separating the element from other elements.

### Box Model Diagram

```text
+-----------------------------------------------+
|                    MARGIN                     |
|   +---------------------------------------+   |
|   |                BORDER                 |   |
|   |   +-------------------------------+   |   |
|   |   |            PADDING            |   |   |
|   |   |   +-----------------------+   |   |   |
|   |   |   |       CONTENT         |   |   |   |
|   |   |   |   Heading and text    |   |   |   |
|   |   |   +-----------------------+   |   |   |
|   |   +-------------------------------+   |   |
|   +---------------------------------------+   |
+-----------------------------------------------+
```

## 6. Difference Between `content-box` and `border-box`

| Property | `content-box` | `border-box` |
|---|---|---|
| Specified width includes | Content only | Content + padding + border |
| Padding added outside specified width | Yes | No |
| Border added outside specified width | Yes | No |
| Overall width | Usually larger | Equal to specified width |
| Layout control | Requires extra calculation | Easier to manage |

### Example Calculation

For a box with:

- Width = 600px
- Left and right padding = 20px each
- Left and right border = 5px each

**Using `content-box`:**

Total width = Content + Padding + Border

Total width = 600 + 40 + 10 = **650px**

**Using `border-box`:**

Total width = **600px**

The padding and border are included inside the specified width. The content area becomes 550px.

Note: Margin is outside the border and is not included in either width calculation.

## 7. Steps to Run the Project

1. Open Visual Studio Code.
2. Create a folder named `Assignment-6.1`.
3. Create `index.html` and `style.css`.
4. Paste the corresponding code into each file.
5. Save both files.
6. Open `index.html` using the Live Server extension.
7. View all three cards in the browser.

## 8. Inspect the Box Model in Chrome DevTools

1. Open the webpage in Google Chrome.
2. Right-click the first card and select **Inspect**.
3. In the **Elements** panel, select the card's HTML element.
4. Open the **Computed** tab in the right-hand panel.
5. Locate the box model diagram.
6. Observe the displayed content, padding, border, and margin values.
7. Select the second and third cards and compare their values.
8. Click a padding, border, or margin value in the diagram to edit it.
9. Change the value and observe how the card's size and spacing change.
10. Edit `box-sizing` in the Styles panel to compare `content-box` and `border-box`.

## 9. Screenshot and Annotation

Take a screenshot of the webpage and another screenshot of the Chrome DevTools box model.

**Screenshot 1 — Webpage**

- Open the page in Chrome.
- Make sure all three cards are visible. If necessary, zoom out slightly.
- Take a screenshot using `Win + Shift + S`.
- Save it as `box-model-webpage.png`.

**Screenshot 2 — Box Model Inspection**

- Right-click Card 1 and select **Inspect**.
- Keep the Computed tab and box model diagram visible.
- Take a screenshot and save it as `box-model-devtools.png`.

**Annotate the DevTools screenshot:**

Use Paint, PowerPoint, or another image editor to add arrows and labels to the four regions of the DevTools box model diagram:

- **Content:** Center area containing the element's content dimensions.
- **Padding:** Space surrounding the content inside the border.
- **Border:** Region surrounding the padding.
- **Margin:** Outermost spacing around the element.

Save the annotated screenshot as `box-model-annotated.png`.

Attach the annotated screenshot to the assignment along with the HTML and CSS files.

## 10. Result

The webpage was created successfully with three cards using different padding, border, and margin values. The behavior of `content-box` and `border-box` was compared, and the box model was inspected and modified using Chrome DevTools.

## 11. Conclusion

The CSS Box Model helps explain the dimensions and spacing of HTML elements. Padding creates space inside the border, margin creates space outside the border, and borders surround the content and padding. The `border-box` value makes element sizing easier to control because padding and borders are included in the specified width.

## 12. Submission Checklist

- [ ] `index.html`
- [ ] `style.css`
- [ ] Screenshot of the webpage
- [ ] Chrome DevTools screenshot
- [ ] Annotated screenshot labeling Content, Padding, Border, and Margin
- [ ] Result and conclusion
