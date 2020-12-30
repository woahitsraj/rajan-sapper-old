
<script lang="ts">
  import DarkModeToggle from "./DarkModeToggle.svelte";
  export let segment: string;
  const links = [
    { text: "Home", route: "/" },
    { text: "Blog", route: "/blog" },
  ];
</script>

<nav class="flex flex-row py-8 justify-between px-4">
  <div />
  <ul class="flex flex-row">
    {#each links as link}
      <li>
        <a
          class="text-xl mx-4"
          aria-current={segment === link.route.slice(1) ? 'page' : undefined}
          href={link.route}>{link.text}</a>
      </li>
    {/each}
  </ul>
  <DarkModeToggle />
</nav>
