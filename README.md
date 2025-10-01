# Project: Portfolio Site

## Project Overview

### Building a Portfolio Homepage

Congratulations on completing all the lessons of the course! You're almost there! It’s time to put your newly acquired skills into practice by building the homepage for your portfolio site. This project will showcase your ability to create a responsive, accessible, and professional webpages.

You’ll build two key sections: The first is an **Intro Banner**, featuring your photo, a short blurb, and two 'call to action' buttons with alternative colors. The second section is **Latest Projects** containing three project cards and a button. You’ll work from a provided wireframe to match the layout as closely as possible. Your site will be fully responsive across devices and meet **A and AA accessibility standards**.

By completing this project, you’ll demonstrate your proficiency with CSS methodologies, preprocessors, accessibility practices, and advanced CSS techniques, all while creating a polished addition to your portfolio.

## Instructions

### Project Instructions

1. **Starter Code**:

   - Download and unzip the provided [starter code](https://github.com/udacity/cd14106-project-starter-code), which includes:
     - **Dist Folder**: Where your compiled CSS file (main.css) will live.
     - **Src Folder**:
       - `img`: Store all image files here. This folder has a placeholder image for your Introduction banner. You're welcome to use it, but are encouraged to find your own image, which better reflects your personality.
       - `scss_less`: Store all CSS preprocessor folders and files here. Rename this folder to match the preprocessor you are using (`scss` or `less`).
   - Download the wireframes to guide the website layout for desktop and mobile views.

2. **Folder Structure**:

   - As per BEM methodology, your `scss` or `less` folder will contain `base`, `blocks`, and `utils` folders with a primary stylesheet that matches the name (see example folder structure below):
     - **Base**: Contains foundational styles such as resets, typography, and general element styles (e.g., for body, headings, links).
     - **Blocks**: Houses styles for individual components, each in its own file, following the BEM methodology (e.g., `button.scss`, `header.scss`).
     - **Utils**: Includes reusable helper styles like variables, mixins, and utility classes that support the design system.
   - Compile all preprocessor files into a single `main.css` file inside the `dist` folder.

3. **Intro Banner**:

   - **Content**:
     - Include a background image for the banner.
     - Add a bio section with:
       - A profile image.
       - A main heading (e.g., "[Your Name]'s Web Development Portfolio").
       - A short paragraph describing yourself.
     - **Note:** If you don't feel comfortable using your own photo, you can use a placeholder image for the purpose of this project. Using a professional headshot can positively contribute to a developer's personal branding, but you don't have to make that decision just yet.
   - **Responsive Behavior**:
     - Align the profile image and text content side by side on larger screens.
     - Stack the profile image above the text content on mobile.

4. **Latest Projects Section**:

   - **Content**:
     - Include a heading (e.g., "Latest Projects").
     - Add three project cards, each with:
       - An image (placeholder images are fine).
       - A title.
       - A short description.
     - Add a centered button below the cards that would link to a projects page.
   - **Design**:
     - Ensure the cards are equal in width and height.
     - Apply hover or tabbing transitions to project cards.

5. **Navigation Header**:

   - Create a fixed navbar with projects, skills, resume, and contact links.
   - The navbar should:
     - Stick to the top of the page and shrink in height on scroll.
     - Display links on desktop and optionally collapse into a mobile-friendly "burger" menu for smaller screens.
     - **Note:** If you choose not to incorporate a burger menu into your mobile view, keep in mind that you still need to adhere to responsiveness standards and ensure that your links do not overflow beyond the width of the header.

6. **Footer**:

   - Create a footer at the bottom of your page with copyright information. (e.g. `&copy; [Your full name] 2025`)

7. **Accessibility**:

Meet the A and AA accessibility standards outlined in the provided checklist.

### Example Style Folder Structure

```
src
├── index.html
├── scss
│     ├── base
│     │   ├── _resets.scss
│     │   └── base.scss
│     ├── blocks
│     │   ├── _footer.scss
│     │   ├── _header.scss
│     │   ├── _any_block_partial.scss
│     │   └── blocks.scss
│     └── utils
│         ├── _mixins.scss
│         ├── _variables.scss
│         └── utils.scss
```

### Submission Instructions

1. **Submission**:
   - Submit the entire project, including:
     - `dist`: Compiled main.css file.
     - `src`:
       - `img`: Any images used in the project.
       - `scss`/`less`: All preprocessor files and folders.
       - `index.html`: HTML file containing your web components.
       - `package.json`: For reviewers to install dependencies if needed.

Zip the project folder as `[first_name_lastname]_homepage` and upload it.

## Organizing Utilities with BEM

When working with SCSS or Less and the BEM methodology, you can choose between two approaches for organizing utilities: the **Aggregated Approach** or the **Granular Approach**. Follow these examples based on the preprocessor you're using.

### 1. The Aggregated Approach

This approach uses a single file (`utils.scss` or `utils.less`) to aggregate all utility files, which is then imported into each block file.

#### SCSS Example

1. Create a utils.scss file:

```scss
@use './variables';
@use './mixins';
```

2. Import `utils.scss` in a block file (e.g., `_header.scss`):

```scss
@use '../utils/utils';

.header {
  background-color: utils.$primary-color;
  @include utils.flex-center;
}
```

#### Less Example

1. Create a `utils.less` file:

```less
@import './variables';
@import './mixins';
```

2. Import `utils.less` in a block file (e.g., `header.less`):

```less
@import '../utils/utils';

.header {
  background-color: @primary-color;
  .flex-center();
}
```

### 2. The Granular Approach

With the granular approach, each block file directly imports the specific utility files it needs.

#### SCSS Example

In your block file (e.g., `_header.scss`):

```scss
@use '../utils/variables';
@use '../utils/mixins';

.header {
  background-color: _variables.$primary-color;
  @include _mixins.flex-center;
}
```

#### Less Example

In your block file (e.g., `header.less`):

```less
@import '../utils/variables';
@import '../utils/mixins';

.header {
  background-color: @primary-color;
  .flex-center();
}
```

### Notes

- Choose **one approach**—aggregated or granular—and apply it consistently.
- SCSS users should use `@use` for modular imports, while Less users rely on `@import`.
- Organize your `utils` folder to store all utility files (e.g., `_variables.scss`, `_mixins.scss` for SCSS or `variables.less`, `mixins.less` for Less).
- If you're using the granular approach, you don't need a `utils` file since your partials get imported directly into your other stylesheets.

By following these guidelines, you can effectively manage utilities in both SCSS and Less while adhering to the BEM methodology.

## Development Strategy

For this project, you are encouraged to implement your own design workflow, but if you get stuck—here is a brief primer to get you up and running!

### 1. Review the Wireframe

- Carefully study the provided wireframe to understand the expected layout for the **Intro Banner** and **Latest Projects** sections.
- Pay attention to spacing, alignment, and element placement as you will be evaluated on your ability to match the wireframe.

### 2. Decide on a Visual Theme

- Think about your site's aesthetics:
  - Will you use a light or dark theme?
  - What colors will you use for consistency?
  - How will your buttons look—rounded, flat, or with shadows?
- Apply these choices consistently to maintain a cohesive design.

### 3. Set Up Your Project

- Clone or download the starter project and set up your folder structure:
  - Create your `base`, `blocks`, and `utils` folders within your scss or less directory.
  - Within these folders, create your base stylesheets that will use all your future partials, `base.scss`, `blocks.scss`, and `utils.scss`.
- Compile your CSS into a `main.css` file. Ensure that it compiles directly into the `dist` folder.
- Use **Live Preview** in Visual Studio Code or a similar tool to view your changes in real-time.

### 4. Build Out Your Components

- Your starter code comes with the basic structure of the webpage.
- Build out the inner content with consideration of how each component will be nested in the overall hierarchy.
- Assign classes to your components based on BEM methodology by assigning a general block name class to each section, and then any elements within those blocks, with modifiers if needed.

### 5. Implement Accessibility Standards

- Refer to the accessibility checklist to ensure your site meets **A and AA standards**.
- Use semantic tags for structure, descriptive alt attributes for images, and ARIA labels where necessary.
- Test your site using accessibility tools like Lighthouse or WAVE.

### 6. Style Your Components

- With the HTML components built and their classes assigned, create a partial file for each block.
- Within each partial, recreate the appropriately nested structure based on BEM methodology. (See rubric for further help.)
- Create any mixins of variables you might need. A good start would be to create variables for your colors and mixins for media queries.
- Once the structure is built and your mixins and variables created, you can style each section as needed.
- As you continue to add new styles, pay attention to any styles that are frequently repeated in your code and consider refactoring them into mixins or variables.

### 7. Test Responsiveness

- Use browser developer tools to simulate mobile, tablet, and desktop views.
- Confirm that the layout adapts correctly and that elements are neither overlapping nor misaligned at any screen size.

### 8. Iterate and Refine

- Revisit the wireframe and compare your design to ensure it matches the expected layout.
- Adjust for visual balance and responsiveness as needed.

## Rubric

Use this project rubric to understand and assess the project criteria.

### Basic Requirements

<table>
    <tr>
        <th>Criteria</th>
        <th>Submission Requirements</th>
    </tr>
    <tr>
        <td>Follow wireframes to build a project layout</td>
        <td>
             <ul>
                <li>The page structure matches the provided wireframes.</li>
                <li>The logo (if included) is at the opposite end from the navbar.</li>
                <li>Proportions, alignment, and placement of elements are consistent with the design.</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>Create a responsive design that adapts to different screen sizes</td>
        <td>
            <ul>
                <li>Pages adjust appropriately for desktop, tablet, and mobile views.</li>
                <li>No elements overflow or break the layout when resizing the browser window.</li>
            </ul>
        </td>
    </tr>
</table>

### Methodology

<table>
    <tr>
        <th>Criteria</th>
        <th>Submission Requirements</th>
    </tr>
    <tr>
        <td>Organize files with a clear structure based on BEM methodology</td>
        <td>
            <ul>
                <li>The <code>scss</code>/<code>less</code> folder structure includes separate folders for <code>base</code>, <code>blocks</code>, and <code>utils</code>.</li>
                <li>Each folder has a main stylesheet file matching the folder name (e.g., <code>base.scss</code>, <code>blocks.less</code>) unless using the <strong>granular approach</strong>, in which case, no <code>utils</code> file is needed.</li>
                <li>Block names reflect the component's purpose (e.g., <code>header</code>, <code>button</code>, <code>bio</code>) rather than being descriptive (e.g., <code>large-text</code>).</li>
                <li>If using the <strong>aggregated approach</strong>, a <code>utils.scss</code> or <code>utils.less</code> file consolidates utilities like <code>_variables</code> and <code>_mixins</code> for import into blocks.</li>
                <li>If using the <strong>granular approach</strong>, <code>_variables</code> and <code>_mixins</code> are imported directly into block files as needed.</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>Apply the BEM methodology to structure CSS</td>
        <td>
            <ul>
                <li>Class names that are created in preprocessor files use BEM methodology</li>
                <li>Class names are logical and consistent, reflecting the page's structure</li>
            </ul>
            You're welcome to refer to the official BEM Methodology documentation to review the BEM rules: <a href="https://en.bem.info/methodology/quick-start/">https://en.bem.info/methodology/quick-start/</a>
        </td>
    </tr>
</table>

### Preprocessors

<table>
    <tr>
        <th>Criteria</th>
        <th>Submission Requirements</th>
    </tr>
    <tr>
        <td>Compile preprocessor stylesheets into a primary CSS file</td>
        <td>
            <ul>
                <li>The <code>/dist</code> folder contains a <code>main.css</code> file which is compiled using a preprocessor through console commands.</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>Use variables and mixins for reusable styles like colors, fonts, and spacing</td>
        <td>
            <ul>
                <li>Variables are defined for reusable values (e.g., <code>$primary-color</code>, <code>@font-size-base</code>).</li>
                <li>Variables are applied consistently across SCSS/Less files.</li>
                <li>At least one mixin is created for common patterns (e.g., media queries, reusable styles).</li>
                <li>Mixins are used effectively across SCSS/Less files.</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>Apply nesting to organize related styles hierarchically</td>
        <td>
            <ul>
                <li>
                    The BEM element and modifier selectors are declared in a nested format to avoid repetition:
                    <ul>
                        <li>A <code>.block</code> selector should contain all the related <code>&__element</code> selectors.</li>
                        <li>Modifiers should be nested under their respective blocks and elements, using the <code>&_modifier</code> syntax (e.g., <code>.block__element</code> and <code>.block__element_modifier</code>).</li>
                        <li>Avoid deep nesting to maintain readability and ensure maintainable code.</li>
                    </ul>
                </li>
            </ul>
        </td>
    </tr>
</table>

### CSS Techniques

<table>
    <tr>
        <th>Criteria</th>
        <th>Submission Requirements</th>
    </tr>
    <tr>
        <td>Implement advanced CSS properties</td>
        <td>
            At least one of the following advanced CSS properties is present in the project:
            <ul>
                <li>Math Functions (calc)</li>
                <li>Scroll Snap</li>
                <li>Inset text color</li>
                <li>Anchor</li>
                <li>Color Scheme Media Query</li>
                <li>Backdrop Filter</li>
                <li>Min and Max</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>Enhance interactivity with CSS animations and transitions</td>
        <td>
            <ul>
                <li>The buttons change background color when hovered over or when clicked/tapped, and this color transition is smooth.</li>
                <li>Includes at least one other transition or animation technique, such as:
                    <ul>
                        <li>Hover transitions (in addition to the buttons, something that affects properties other than color)</li>
                        <li>Animations defined with <code>@keyframes</code></li>
                    </ul>
                </li>
                <li>Effects are smooth, non-distracting, and align with the design intent</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>Incorporate responsive animations and dynamic effects</td>
        <td>
            <ul>
                <li>The <code>nav</code> header needs to minimize its height as the user scrolls down.</li>
                <li>
                    In addition to the nav, the project needs to implement at least one more of the following responsive or dynamic animation techniques:
                    <ul>
                        <li>On-scroll effects</li>
                        <li>Animated backgrounds</li>
                        <li>Turning off animations via media queries</li>
                    </ul>
                </li>
            </ul>
        </td>
    </tr>
</table>

### Accessibility

<table>
    <tr>
        <th>Criteria</th>
        <th>Submission Requirements</th>
    </tr>
    <tr>
        <td>Ensure proper semantic HTML and relationships</td>
        <td>
            <ul>
                <li>Webpage uses semantic tags correctly (header, footer, main, section, h1-h6).</li>
                <li>Heading tags descend in the correct order.</li>
                <li>Labels are associated with input fields using the for attribute (if applicable).</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>Provide accessible non-text content</td>
        <td>
            <ul>
                <li>All images include meaningful <code>alt</code> attributes (or <code>alt=""</code> for decorative images).</li>
                <li>Icons or links without visible text use <code>aria-label</code> or are wrapped in a visually hidden class (e.g., <code>sr-only</code>).</li>
                <li>Form buttons have descriptive text or <code>aria-label</code> attributes.</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>Ensure keyboard and focus accessibility</td>
        <td>
            <ul>
                <li>All functionality is accessible via the keyboard (e.g., tabbing through links and buttons).</li>
                <li>Focus order is logical and intuitive.</li>
                <li>Keyboard focus never gets stuck (no keyboard traps).</li>
                <li>Focused elements are visibly highlighted.</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>Use color and sensory characteristics accessibly</td>
        <td>
            <ul>
                <li>Color is not the sole method to convey information.</li>
                <li>Links are distinguishable from surrounding text without relying solely on color.</li>
                <li>The contrast ratio between text and background is at least 4.5:1.</li>
            </ul>
        </td>
    </tr>
</table>

### Suggestions to Make Your Project Stand Out

**Intro animations:** You can have elements animate into existence by fading in or sliding into place once the page loads.

**Other sections:** The suggested navbar items are pages and/or components that one might find in a typical portfolio website. Although a thorough list of projects and a resume should have their own pages, sections such as Skills and Contact could be included on the home page. Consider building them out into their own sections.

**Custom background images:** Custom background images can be found at https://www.pexels.com. They are free and don’t require purchasing or a license. They can also help inspire your overall color theme.
