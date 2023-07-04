# Svelte & SvelteKit

## Introduction:
During the Minor Web Development we have mainly been working with vanilla Javascript, but for project week 1 we were allowed to use a framework of our choice. I chose to work with a framework that I had never used before, but heard a lot about: Svelte. It is a very popular framework that is gaining a lot of traction in the web development community. I was very curious to see what all the hype was about, so I decided to give it a try.

## What is Svelte?
So, Svelte is a modern JavaScript framework that's all about compiling code at build time instead of interpreting it at runtime. It's different from other frameworks like React or Vue because it doesn't rely on a virtual DOM. Instead, it handles updating the DOM during the build process. This unique approach makes Svelte super optimized and fast.

## Features of Svelte:

### Reactive Declarations
One of the nicest things about Svelte is how it handles reactive variables. You can use the `let` keyword to declare variables that automatically update the UI whenever their values change. It's like magic! This makes managing the state of your app a very easy and keeps your code nice and clean.

Example:
```svelte
<script>
  let count = 0;
  
  function increment() {
    count += 1;
  }
</script>

<main>
  <h1>{count}</h1>
  <button on:click={increment}>Increment</button>
</main>
```

### Component-Based Architecture
Svelte encourages us to build our web applications in a modular way using components. We can create reusable components with their own styles, logic, and templates. Each component takes care of its own stuff, which makes it way easier to understand and manage complex apps.

Example:
```svelte
<script>
  let name = "John Doe";
</script>

<main>
  <h1>Hello, {name}!</h1>
</main>
```

### Scoped CSS
With Svelte, we can write CSS styles that only apply to specific components. This means our styles won't clash with other parts of the app. It's like giving each component its own little world. Plus, it helps keep our styles organized and manageable.

Example:
```svelte
<style>
  main {
    background-color: #f5f5f5;
    padding: 16px;
  }
</style>

<main>
  <h1>Hello, Svelte!</h1>
</main>
```


If for whatever reason you need to apply global styles, you can use the `:global()` selector to do so.

Example:
```svelte
<style>
  :global(body) {
    font-family: sans-serif;
  }
</style>
```


### Lifecycle Methods
Svelte hooks us up with some handy lifecycle methods. These methods allow us to perform actions at different stages of a component's life. For example, we can use the `onMount` method to fetch data from an API when the component is first mounted. It's pretty nifty!

Example:
```svelte
<script>
  import { onMount } from "svelte";

  async function fetchData() {
    // Fetch data from API
  }

  onMount(async () => {
    await fetchData();
  });
</script>

<main>
  <h1>Component Lifecycle</h1>
</main>
```

### Easy Animation and Transition
Svelte makes adding animations and transitions to our web apps very. It has a simple API that lets us define and control animations with ease. There are even built-in transition functions that help us create smooth and eye-catching effects.

Example:
```svelte
<script>
  import { fade } from "svelte/transition";

  let isVisible = true;
</script>

<main>
  {#if isVisible}
    <div transition:fade>
      <h1>Fading In and Out</h1>
    </div>
  {/if}

  <button on:click={() => (isVisible = !isVisible)}>
    Toggle Visibility
  </button>
</main>
```

## Personal Comparison with Vue
Now, let me share my thoughts on Svelte compared to Vue. I found Svelte pretty easy to get into because it has some similarities with Vue. But here's the deal: Svelte's compilation approach gives it some advantages. It results in smaller bundle sizes, faster load times, and better performance overall. However, Vue has a more mature ecosystem and a bigger community, so it offers more plugins and resources.

## SvelteKit
SvelteKit is an official framework built on top of Svelte that extends its capabilities for building server-rendered applications and static sites. It provides a higher-level API for handling routing, server-side rendering, prefetching data, and managing application state.
With SvelteKit, you can create dynamic web applications that deliver optimized content to users. It leverages server-side rendering to generate HTML on the server, improving initial load times and enabling search engine optimization (SEO). Additionally, SvelteKit supports incremental hydration, allowing the application to take over on the client-side once it has loaded, providing a smooth user experience.

SvelteKit introduces a file-based routing system, where you can define routes by creating files and folders in a designated structure. This simplifies the process of managing routes and organizing your project. It also offers features like page transitions, authentication, and error handling out of the box.

## Conclusion:
In a nutshell, Svelte is a modern and high-performing JavaScript framework that makes web development a easier by compiling code at build time. Its features, like reactive declarations, component-based architecture, scoped CSS, lifecycle methods, and easy animations, empower us to build clean and efficient apps. With the addition of SvelteKit it becomes even more powerful and expands its capabilities for server-rendered apps and static sites. So whether you're a seasoned developer or just starting out, exploring Svelte can level up your web development skills.

!!! Note: The code examples I shared here are simplified to keep things concise. Make sure to check out the official Svelte documentation for more details and examples.

Sources:
- [Official Svelte Documentation](https://svelte.dev/docs)
- [SvelteKit Documentation](https://kit.svelte.dev/docs/introduction)
- [The New Stack](https://thenewstack.io/all-about-svelte-the-much-loved-state-driven-web-framework/)