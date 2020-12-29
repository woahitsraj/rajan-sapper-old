<script lang="ts">
  import DarkModeToggle from "./DarkModeToggle.svelte";
  export let segment: string;
</script>

<nav class="flex flex-row py-8">
  <ul class="flex flex-row">
    <li>
      <a
        aria-current={segment === undefined ? 'page' : undefined}
        href="/">Home</a>
    </li>
    <li>
      <a
        rel="prefetch"
        aria-current={segment === 'blog' ? 'page' : undefined}
        href="/blog">Blog</a>
    </li>
  </ul>
  <DarkModeToggle />
</nav>
