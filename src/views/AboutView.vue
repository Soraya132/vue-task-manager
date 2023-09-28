<template>
  <div>
    <header class="text-center py-8">
      <h1 class="text-4xl font-bold text-gray-500">About My Vue.js Todo App</h1>
    </header>
    <section
      class="bg-white rounded-lg shadow-md p-6 mx-4 sm:mx-auto max-w-2xl">
      <h2 class="text-2xl font-semibold mb-4">Introduction</h2>
      <p>
        Welcome to my Vue.js Todo app! This project was created as a part of my
        journey to explore Vue.js and Tailwind CSS. It's a simple yet functional
        task management application designed to help users stay organized and
        focused.
      </p>
    </section>

    <section
      class="bg-white rounded-lg shadow-md p-6 mx-4 sm:mx-auto max-w-2xl mt-4">
      <h2 class="text-2xl font-semibold mb-4">Features</h2>
      <ul class="list-disc pl-6">
        <li>
          <h3 class="text-lg font-semibold">Task Management</h3>
          <p>Add new tasks with ease.</p>
          <p>Mark tasks as completed.</p>
          <p>Delete tasks when they're no longer needed.</p>
        </li>
        <li>
          <h3 class="text-lg font-semibold">Intuitive User Interface</h3>
          <p>
            A clean and user-friendly interface makes it easy to manage tasks.
          </p>
          <p>
            Task statuses are visually represented, making it simple to see
            what's completed and what's pending.
          </p>
        </li>
        <li>
          <h3 class="text-lg font-semibold">Vue.js &amp; Tailwind CSS</h3>
          <p>
            This app is built using Vue.js, a progressive JavaScript framework
            known for its simplicity and reactivity.
          </p>
          <p>
            Tailwind CSS was used for styling, allowing for rapid UI development
            without writing custom CSS.
          </p>
        </li>
      </ul>
    </section>

    <section
      class="bg-white rounded-lg shadow-md p-6 mx-4 sm:mx-auto max-w-2xl mt-4">
      <h2 class="text-2xl font-semibold mb-4">My Learning Journey</h2>
      <ul class="list-disc pl-6">
        <li>
          <h3 class="text-lg font-semibold">Vue.js Composition API</h3>
          <p>
            I used Vue's Composition API to structure my code, allowing for
            better organization and reusability of components.
          </p>
        </li>
        <li>
          <h3 class="text-lg font-semibold">Component-Based Development</h3>
          <p>
            Vue's component-based architecture allowed me to create modular,
            reusable components like the task list and individual task items.
          </p>
        </li>
        <li>
          <h3 class="text-lg font-semibold">
            Parent-Child Component Communication
          </h3>
          <p>
            I utilized Vue's <code>emit</code> function to enable communication
            between parent and child components, enhancing the interactivity of
            the app.
          </p>
        </li>
        <li>
          <h3 class="text-lg font-semibold">Tailwind CSS Styling</h3>
          <p>
            Tailwind CSS made styling a breeze, and its utility-first approach
            sped up the development process.
          </p>
        </li>
      </ul>
    </section>

    <section
      class="bg-white rounded-lg shadow-md p-6 mx-4 sm:mx-auto max-w-2xl mt-4">
      <h2 class="text-2xl font-semibold mb-4">Future Enhancements</h2>
      <p>
        While this app serves as my introduction to Vue.js and Tailwind CSS, I
        have plans to further improve and expand its features in the future.
        Some potential enhancements include:
      </p>
      <ul class="list-disc pl-6">
        <li>User authentication for personalized task lists.</li>
        <li>Task prioritization and due dates.</li>
        <li>Data persistence using a backend server or local storage.</li>
      </ul>
    </section>
  </div>
</template>

<script setup></script>
<style scoped>
h2 {
  color: rgb(77, 71, 71);
  font-size: 1.5rem;
}
li {
  padding-bottom: 0.6rem;
  font-size: 1.3rem;
}
p {
  color: rgb(68, 64, 64);
  font-size: 1.1rem;
}
</style>
