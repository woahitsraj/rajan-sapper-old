<script context="module">
  export async function preload() {
    const res = await this.fetch(`https://nomadlist.com/@woahitsraj.json`);
    const nomadlistData = await res.json();

    return { nomadlistData };
  }
</script>

<script>
  export let nomadlistData;
  $: currentLocation = nomadlistData.location.now;
</script>

<svelte:head>
  <title>Rajan Singh</title>
</svelte:head>
<div class="flex flex-col w-full h-full">
  <span class="w-full">
    <h1 class="text-6xl font-bold text-center mb-4">Woah! It's Raj!</h1>
  </span>
  <span class="w-full">
    <img
      class="w-64 h-64 rounded-full mr-4 inline float-left"
      src="/me.jpg"
      alt="Me, Rajan Singh" />
    <p class="text-3xl">
      Hi, I'm Rajan. I am a web developer from California but I tend to move
      around alot. Currently I am in {currentLocation.city}, {currentLocation.country}
    </p>
  </span>
</div>
