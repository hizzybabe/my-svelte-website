<script>
  import ChapterNavigation from '$lib/components/ChapterNavigation.svelte';
  import SolutionChecker from '$lib/components/SolutionChecker.svelte';
</script>

<div class="container mx-auto px-4 py-8">
  <h1>Chapter 2: Selectors & Properties</h1>

  <h2>Theory</h2>
  
  <h3>Understanding CSS Selectors</h3>
  <div>
    CSS selectors are used to "select" the HTML elements you want to style. Different types of selectors allow you to apply styles to specific elements in your document.
  </div>
  
  <h4>Types of Selectors:</h4>
  <ul>
    <li><strong>Element Selector</strong>: Targets all elements of a specific type.
      <div>Example: <code>p &lbrace; color: blue; &rbrace;</code> styles all <code>&lt;p&gt;</code> elements.</div>
    </li>
    <li><strong>ID Selector</strong>: Targets a specific element with a unique <code>id</code> attribute. The ID selector is represented with a <code>#</code>.
      <div>Example: <code>#profile &lbrace; color: green; &rbrace;</code> styles the element with <code>id="profile"</code>.</div>
    </li>
    <li><strong>Class Selector</strong>: Targets all elements with a specific <code>class</code> attribute. The class selector is represented with a <code>.</code>.
      <div>Example: <code>.highlight &lbrace; background-color: yellow; &rbrace;</code> styles all elements with <code>class="highlight"</code>.</div>
    </li>
    <li><strong>Universal Selector</strong>: Targets all elements on the page and is represented with <code>*</code>.
      <div>Example: <code>* &lbrace; margin: 0; padding: 0; &rbrace;</code> removes default margins and padding from all elements.</div>
    </li>
  </ul>

  <h4>Selector Example:</h4>
  <pre><code>
h1 &lbrace; color: navy; &rbrace;           /* Element selector */
#header &lbrace; font-size: 24px; &rbrace;  /* ID selector */
.container &lbrace; padding: 10px; &rbrace; /* Class selector */
* &lbrace; box-sizing: border-box; &rbrace; /* Universal selector */
  </code></pre>

  <h3>Common CSS Properties</h3>
  <div>
    CSS properties define the styling applied to elements. Here are some of the most common properties you’ll use:
  </div>
  
  <ul>
    <li><strong>Color</strong>: Sets the color of the text.
      <div>Example: <code>color: red;</code></div>
    </li>
    <li><strong>Background</strong>: Sets the background color or image of an element.
      <div>Example: <code>background-color: lightgray;</code></div>
      <div>Example: <code>background-image: url('background.jpg');</code></div>
    </li>
    <li><strong>Fonts</strong>: Controls font type, size, and style.
      <div>Example: <code>font-family: Arial, sans-serif;</code></div>
      <div>Example: <code>font-size: 16px;</code></div>
    </li>
    <li><strong>Text</strong>: Adjusts text alignment, decoration, and more.
      <div>Example: <code>text-align: center;</code></div>
      <div>Example: <code>text-decoration: underline;</code></div>
    </li>
  </ul>

  <h4>Property Example:</h4>
  <pre><code>
body &lbrace;
    color: #333;
    background-color: #f4f4f4;
    font-family: Arial, sans-serif;
    font-size: 16px;
&rbrace;
  </code></pre>

  <h3>Introduction to the Box Model</h3>
  <div>
    The CSS Box Model is a fundamental concept for layout and spacing. Every element on a webpage is represented as a rectangular box made up of four areas: <strong>content</strong>, <strong>padding</strong>, <strong>border</strong>, and <strong>margin</strong>.
  </div>

  <h4>Box Model Components:</h4>
  <ul>
    <li><strong>Content</strong>: The actual content of the element, such as text or images.</li>
    <li><strong>Padding</strong>: Space between the content and the border.</li>
    <li><strong>Border</strong>: A line surrounding the padding and content.</li>
    <li><strong>Margin</strong>: Space outside the border, separating the element from others.</li>
  </ul>

  <h4>Box Model Example:</h4>
  <pre><code>
.profile &lbrace;
    padding: 10px;     /* Space inside the element */
    border: 2px solid #ccc; /* Border around the element */
    margin: 20px;      /* Space outside the element */
&rbrace;
  </code></pre>

  <h2 class="workshop-title">Practice Workshop: Styling a Personal Profile</h2>
  <div class="workshop-container">
    <h3 class="task">Task: Style your personal profile page using CSS selectors and properties</h3>
    
    <div class="steps">
      <h4>Step 1: Set Up Your Files</h4>
      <ul>
        <li>Open the <code>profile.html</code> file created in the Learn HTML course.</li>
        <li>Create a new CSS file named <code>profile.css</code>.</li>
        <li>Link <code>profile.css</code> to <code>profile.html</code> by adding this line in the <code>&lt;head&gt;</code> section:
          <pre><code>&lt;link rel="stylesheet" href="profile.css"&gt;</code></pre>
        </li>
      </ul>

      <h4>Step 2: Styling with Selectors</h4>
      <ul>
        <li><strong>Element Selector</strong>: Use element selectors to style text elements globally:
          <pre><code>body &lbrace;
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
&rbrace;

h1 &lbrace;
    color: #2c3e50;
    font-size: 28px;
    text-align: center;
&rbrace;</code></pre>
        </li>
        <li><strong>ID Selector</strong>: Apply unique styles to specific sections of the profile:
          <pre><code>#profile-header &lbrace;
    background-color: #3498db;
    color: white;
    padding: 10px;
    text-align: center;
&rbrace;</code></pre>
        </li>
        <li><strong>Class Selector</strong>: Use class selectors to style multiple elements in a similar way:
          <pre><code>.section &lbrace;
    margin: 20px;
    padding: 15px;
    background-color: #ecf0f1;
    border-radius: 5px;
&rbrace;</code></pre>
        </li>
      </ul>

      <h4>Step 3: Applying Common Properties</h4>
      <ul>
        <li><strong>Text Color</strong>: Use <code>color</code> to change the color of headings and paragraphs.</li>
        <li><strong>Background Color</strong>: Set background colors for different sections.</li>
        <li><strong>Font Style</strong>: Experiment with different font sizes and font families.</li>
      </ul>

      <h4>Step 4: Using the Box Model</h4>
      <ul>
        <li>Apply padding and margins to create spacing around elements.</li>
        <li>Add a border to highlight specific sections:
          <pre><code>.profile-section &lbrace;
    padding: 20px;
    margin: 15px 0;
    border: 1px solid #ddd;
&rbrace;</code></pre>
        </li>
      </ul>
    </div>

    <h3>Deliverables</h3>
    <ul>
      <li><strong>Updated profile.html</strong>: Ensure that your <code>profile.html</code> file links to <code>profile.css</code> and includes content for a personal profile.</li>
      <li><strong>CSS File (profile.css)</strong>: Include styles for text, background colors, and the Box Model properties as outlined in the task.</li>
      <li><strong>Before/After Screenshots</strong>: Take a screenshot of the page before adding styles, then another screenshot with the styles applied. Compare the two to observe the visual difference.</li>
    </ul>
  </div>

  <h2>Summary and Key Takeaways</h2>
  <ul>
    <li><strong>Selectors</strong>: Use element, ID, class, and universal selectors to target elements for styling.</li>
    <li><strong>Properties</strong>: Experiment with text, background, font, and color properties to make elements visually appealing.</li>
    <li><strong>Box Model</strong>: Padding, borders, and margins are crucial for layout and spacing.</li>
  </ul>

  <SolutionChecker />

  <div>
    This chapter covered essential CSS selectors and properties, equipping you with the tools to create well-structured, visually pleasing web pages. Keep experimenting with different styles and layouts to develop your CSS skills further.
  </div>

  <ChapterNavigation 
    prevHref="/css/chapter1" 
    nextHref="/css/chapter3" 
  />
</div>