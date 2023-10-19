<script>
  import Nav from '$lib/components/nav/Nav.svelte';
</script>

<div class="h-full flex">
  <Nav />

  <main class="m-6 lg:ml-2 bg-white grow rounded-2xl shadow-xl">
    <slot />
  </main>
</div>
