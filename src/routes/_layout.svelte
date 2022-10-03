<script lang="ts">
  import Nav from "../components/Nav.svelte";
  import { onMount } from "svelte";
  onMount(async () => {
    await import("tailwindcss-dark-mode/prefers-dark");
  });
  export let segment: string;
</script>

<div class="min-h-screen text-black bg-white dark:bg-black dark:text-white">
  <div class="relative max-w-screen-xl mx-auto">
    <Nav {segment} />
    <main class="p-8">
      <slot />
    </main>
  </div>
</div>
