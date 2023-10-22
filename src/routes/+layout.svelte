<script>
  import '../app.css';
  import Nav from '$lib/components/nav/Nav.svelte';
</script>

<div class="flex h-full">
  <Nav />

  <main class="m-6 grow rounded-2xl bg-white shadow-xl lg:ml-2">
    <slot />
  </main>
</div>
