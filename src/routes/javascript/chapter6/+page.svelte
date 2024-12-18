<script>
  import ChapterNavigation from '$lib/components/ChapterNavigation.svelte';
  import SolutionChecker from '$lib/components/SolutionChecker.svelte';
  let showCode1 = true;
  let showCode2 = true;
  let showCode3 = true;
  let showCode4 = true;
</script>

<div class="container mx-auto px-4 py-8">
  <h1>Chapter 6: Advanced Topics & Best Practices</h1>
  
  <div class="chapter-intro">
    <p>In this chapter, you'll dive into advanced JavaScript concepts such as closures, the module pattern, and the `this` context. These topics will help you write cleaner, more efficient, and secure code.</p>
    
    <div class="chapter-details">
      <p><strong>Duration:</strong> Approximately 2-3 hours</p>
      <p><strong>Goal:</strong> Understand advanced JavaScript concepts and best practices to refactor code for better organization, security, and performance.</p>
    </div>
  </div>

  <hr/>

  <h2>Theory</h2>

  <h3>6.1 Introduction to Closures and the Module Pattern</h3>
  <div class="concept-block">
    <h4>Closures</h4>
    <p>A closure is a function that has access to its own scope, the scope of the outer function, and the global scope. Closures are useful for creating private variables and functions.</p>

    <div class="code-preview bg-gray-100 p-4 rounded-lg my-4">
      <button 
        class="toggle-btn mb-2 px-2 py-1 text-sm text-white rounded"
        style="background-color: rgb(59 130 246) !important"
        on:click={() => showCode1 = !showCode1}
      >
        {showCode1 ? 'Hide Code' : 'Show Code'}
      </button>

      {#if showCode1}
        <pre><code>{`function createCounter() {
    let count = 0;
    return function() {
        count++;
        return count;
    };
}

const counter = createCounter();
console.log(counter()); // Output: 1
console.log(counter()); // Output: 2`}</code></pre>
      {/if}
    </div>

    <h4>Module Pattern</h4>
    <p>The module pattern leverages closures to encapsulate code within a function, allowing you to create private variables and expose only the necessary parts.</p>

    <div class="code-preview bg-gray-100 p-4 rounded-lg my-4">
      <button 
        class="toggle-btn mb-2 px-2 py-1 text-sm text-white rounded"
        style="background-color: rgb(59 130 246) !important"
        on:click={() => showCode2 = !showCode2}
      >
        {showCode2 ? 'Hide Code' : 'Show Code'}
      </button>

      {#if showCode2}
        <pre><code>{`const ToDoModule = (function() {
    let tasks = []; // Private variable

    function addTask(task) {
        tasks.push(task);
    }

    function getTasks() {
        return tasks;
    }

    return {
        addTask,
        getTasks
    };
})();`}</code></pre>
      {/if}
    </div>
  </div>

  <h3>6.2 Understanding 'this' Context</h3>
  <div class="concept-block">
    <h4>The 'this' Keyword</h4>
    <p>The 'this' keyword refers to the current execution context. Its value depends on how and where a function is called, not where it's defined.</p>

    <div class="code-preview bg-gray-100 p-4 rounded-lg my-4">
      <button 
        class="toggle-btn mb-2 px-2 py-1 text-sm text-white rounded"
        style="background-color: rgb(59 130 246) !important"
        on:click={() => showCode3 = !showCode3}
      >
        {showCode3 ? 'Hide Code' : 'Show Code'}
      </button>

      {#if showCode3}
        <pre><code>{`const person = {
    name: 'John',
    greet: function() {
        console.log(\`Hello, I'm \${this.name}\`);
    }
};

person.greet(); // Output: "Hello, I'm John"

const greetFunction = person.greet;
greetFunction(); // Output: "Hello, I'm undefined"`}</code></pre>
      {/if}
    </div>
  </div>

  <h3>6.3 Best Practices for Code Organization</h3>
  <div class="concept-block">
    <h4>Error Handling</h4>
    <div class="code-preview bg-gray-100 p-4 rounded-lg my-4">
      <button 
        class="toggle-btn mb-2 px-2 py-1 text-sm text-white rounded"
        style="background-color: rgb(59 130 246) !important"
        on:click={() => showCode4 = !showCode4}
      >
        {showCode4 ? 'Hide Code' : 'Show Code'}
      </button>

      {#if showCode4}
        <pre><code>{`async function fetchUserData(userId) {
    try {
        const response = await fetch(\`/api/users/\${userId}\`);
        if (!response.ok) {
            throw new Error('User not found');
        }
        return await response.json();
    } catch (error) {
        console.error('Error fetching user:', error);
        throw error;
    }
}`}</code></pre>
      {/if}
    </div>
  </div>

  <h2 class="workshop-title">Practice Workshop: Refactoring the To-Do List App</h2>
  <div class="workshop-container">
    <h3 class="task">Task: Refactor the To-Do List application using advanced JavaScript concepts</h3>
    
    <div class="code-preview bg-gray-100 p-4 rounded-lg my-4">
      <pre><code>
        const ToDoApp = (function() &123;
        // Private array to store tasks
        let tasks = [];
      
        // Cache DOM elements
        const taskInput = document.getElementById("taskInput");
        const taskList = document.getElementById("taskList");
        const addTaskBtn = document.getElementById("addTaskBtn");
      
        // Add event listeners
        addTaskBtn.addEventListener("click", addTask);
        taskList.addEventListener("click", handleTaskClick);
      
        // Add a new task
        function addTask() &123;
            const taskText = taskInput.value.trim();
            if (taskText) &123;
                const newTask = &123; text: taskText, done: false &125;;
                tasks.push(newTask);
                taskInput.value = ""; // Clear input
                updateDisplay();
            &125; else &123;
                alert("Please enter a task.");
            &125;
        &125;
      
        // Update task list display
        function updateDisplay() &123;
            taskList.innerHTML = ""; // Clear the current list
      
            tasks.forEach((task, index) => &123;
                const taskItem = document.createElement("li");
                taskItem.textContent = task.text;
                taskItem.className = task.done ? "done" : "";
      
                // Add data attribute for indexing
                taskItem.setAttribute("data-index", index);
      
                // Add toggle button
                const toggleButton = document.createElement("button");
                toggleButton.textContent = task.done ? "Undo" : "Complete";
                toggleButton.className = "toggle-btn";
                taskItem.appendChild(toggleButton);
      
                // Add remove button
                const removeButton = document.createElement("button");
                removeButton.textContent = "Remove";
                removeButton.className = "remove-btn";
                taskItem.appendChild(removeButton);
      
                taskList.appendChild(taskItem);
            &125;);
        &125;
      
        // Handle task clicks for toggling and removing tasks
        function handleTaskClick(event) &123;
            if (!event.target.matches('button')) return;
            
            const taskItem = event.target.closest('li');
            const index = taskItem.getAttribute("data-index");
            
            if (event.target.classList.contains('toggle-btn')) &123;
                toggleTask(index);
            &125; else if (event.target.classList.contains('remove-btn')) &123;
                removeTask(index);
            &125;
        &125;
      
        // Toggle task completion
        function toggleTask(index) &123;
            tasks[index].done = !tasks[index].done;
            updateDisplay();
        &125;
      
        // Remove a task
        function removeTask(index) &123;
            tasks.splice(index, 1);
            updateDisplay();
        &125;
      
        // Public API
        return &123;
            addTask,
            toggleTask,
            removeTask
        &125;;
      &125;)();
      </code></pre>
    </div>

    <h3>Deliverables</h3>
    <ul>
      <li>Refactored To-Do List application using the module pattern</li>
      <li>Improved error handling and user feedback</li>
      <li>Documentation explaining your refactoring decisions</li>
      <li>Code that follows best practices for organization and maintainability</li>
    </ul>

    <SolutionChecker />
  </div>

  <ChapterNavigation 
    prevHref="/javascript/chapter5" 
    nextHref="/javascript/chapter7"
  />
</div>

<style>
  .chapter-intro {
    background-color: #f8f9fa;
    padding: 1.5rem;
    border-radius: 8px;
    margin-bottom: 2rem;
  }

  .chapter-details {
    margin-top: 1rem;
    padding-top: 1rem;
    border-top: 1px solid #dee2e6;
  }

  .concept-block {
    margin-bottom: 2rem;
  }

  .workshop-container {
    padding: 1rem;
    background-color: #f8f9fa;
  }

  .code-preview {
    margin: 1rem 0;
  }

  .task {
    color: #2563eb;
    margin-bottom: 1rem;
  }
</style>