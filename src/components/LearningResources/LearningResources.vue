<template>
  <li>
    <div>
      <header>
        <h3>{{ title }}</h3>
        <button>Delete</button>
      </header>
    </div>
    <p class="description">{{ description }}</p>
    <nav>
      <a :href="link">View Resources</a>
    </nav>
  </li>
</template>

<script>
export default {
  props: ["title", "description", "link"],
};
</script>
