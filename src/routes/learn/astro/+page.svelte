<script>
  const chapters = [
    {
      title: "Prerequisites",
      topics: [
        "Setting Up Development Environment",
        "Deploying to Vercel",
        "Deploying to Netlify",
        "Basic HTML/CSS/JavaScript Knowledge"
      ],
      path: "/learn/astro/prerequisites"
    },
    {
      title: "Chapter 1: Introduction to Astro & Setup",
      topics: [
        "What is Astro?",
        "Static Site Generation vs Server-Side Rendering",
        "Setting Up Your First Astro Project",
        "Understanding Project Structure",
        "Practice Workshop: Hello Astro!"
      ],
      path: "/learn/astro/ch1"
    },
    {
      title: "Chapter 2: Astro Components & Pages",
      topics: [
        "Astro Component Syntax",
        "Creating Pages",
        "File-based Routing",
        "Static & Dynamic Content",
        "Practice Workshop: Building a Blog Layout"
      ],
      path: "/learn/astro/ch2"
    },
    {
      title: "Chapter 3: Markdown & MDX",
      topics: [
        "Working with Markdown Files",
        "MDX Integration",
        "Frontmatter",
        "Content Collections",
        "Practice Workshop: Blog Post System"
      ],
      path: "/learn/astro/ch3"
    },
    {
      title: "Chapter 4: Styling in Astro",
      topics: [
        "CSS in Astro",
        "Scoped Styles",
        "Tailwind CSS Integration",
        "Global Styles",
        "Practice Workshop: Responsive Portfolio"
      ],
      path: "/learn/astro/ch4"
    },
    {
      title: "Chapter 5: Integrations & UI Frameworks",
      topics: [
        "Using React Components",
        "Using Svelte Components",
        "Component Islands",
        "Hydration Strategies",
        "Practice Workshop: Interactive Widget"
      ],
      path: "/learn/astro/ch5"
    }
  ];
</script>

<div class="container">
  <h1>Learn Astro</h1>
  <p class="intro">Master modern static site generation with Astro</p>

  <div class="chapters">
    {#each chapters as chapter}
      <div class="chapter-card">
        <h2>{chapter.title}</h2>
        <ul>
          {#each chapter.topics as topic}
            <li>{topic}</li>
          {/each}
        </ul>
        <button on:click={() => window.location.href = chapter.path}>Start Chapter</button>
      </div>
    {/each}
  </div>
</div>

<style>
  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
  }

  h1 {
    font-size: 2.5rem;
    text-align: center;
    margin-bottom: 1rem;
  }

  .intro {
    text-align: center;
    color: #666;
    margin-bottom: 3rem;
  }

  .chapters {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
  }

  .chapter-card {
    background: white;
    padding: 1.5rem;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }

  .chapter-card h2 {
    margin-bottom: 1rem;
    font-size: 1.25rem;
  }

  .chapter-card ul {
    list-style: none;
    padding: 0;
    margin-bottom: 1.5rem;
  }

  .chapter-card li {
    margin-bottom: 0.5rem;
    color: #666;
  }

  button {
    width: 100%;
    padding: 0.75rem;
    background: var(--primary);
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: background 0.2s;
  }

  button:hover {
    background: var(--secondary);
  }
</style>
