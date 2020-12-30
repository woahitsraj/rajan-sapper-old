<script lang="ts">
  import Moon from "./svg/Moon.svelte";

  import Sun from "./svg/Sun.svelte";

  let isDarkMode =
    typeof document !== "undefined" &&
    document.documentElement.classList.contains("mode-dark");
  function toggleDarkMode() {
    isDarkMode = !isDarkMode;
    if (document.documentElement.classList.contains("mode-dark")) {
      document.documentElement.classList.remove("mode-dark");
    } else {
      document.documentElement.classList.add("mode-dark");
    }
  }
</script>

<div class="flex items-center space-x-4">
  <button
    on:click={toggleDarkMode}
    style={isDarkMode ? 'background-color: rgb(17, 24, 39);' : 'background-color: rgb(96, 211, 96);'}
    id="headlessui-switch-1"
    role="switch"
    tabindex="0"
    class={`inline-flex items-center px-0.5 rounded-full w-20 h-9
      transition-colors duration-200 focus-visible:ring-2
      focus-visible:ring-offset-2 focus-visible:ring-offset-white
      focus-visible:ring-gray-500 focus:outline-none justify-between`}
    aria-checked={isDarkMode}>
    <Sun />
    <span class="sr-only">Enable dark mode</span>
    <span
      class="bg-white rounded-full w-8 h-8 transition-all absolute z-10"
      style="box-shadow: rgba(0, 0, 0, 0.05) 0px 2px 5px, rgba(0, 0, 0, 0.1) 0px 1px 1px; transform-origin: 50% 50% 0px; {isDarkMode ? 'margin-left: 42px;' : ''};" />
    <Moon />
  </button>
</div>
