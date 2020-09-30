<script lang="ts">
  import Nav from "../components/Nav.svelte";

  export let segment: string;
</script>

<div class="bg-white dark:bg-black text-black dark:text-white h-full">
  <div class="relative max-w-screen-xl mx-auto">
    <Nav {segment} />
    <main class="p-8">
      <slot />
    </main>
  </div>
</div>
