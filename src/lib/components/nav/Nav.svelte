<script lang="ts">
  let open = false;

  $: openBasedNavContainerClasses = open ? 'left-0' : '-left-80';
</script>

<aside class="fixed left-0 top-0 h-full lg:relative">
  <button
    class="m-2 flex h-12 w-12 items-center justify-center rounded-full bg-violet-50 outline outline-8 outline-violet-200 lg:hidden"
    on:click={() => (open = !open)}
  >
    <span class="material-symbols-outlined text-violet-500">
      {open ? 'close' : 'menu'}
    </span>
  </button>

  <section
    class="absolute bottom-0 top-0 mt-16 h-[calc(100%-64px)] w-80 p-4 transition-all duration-300 ease-in-out lg:relative lg:left-0 lg:mt-0 lg:h-full lg:p-6 {openBasedNavContainerClasses}"
  >
    <nav
      class="h-full rounded-lg bg-violet-100 shadow-lg shadow-zinc-400 lg:bg-violet-200 lg:shadow-none"
    >
      <h1 class="pb-8 pt-4 text-center text-2xl font-bold">JV Task Manager</h1>
    </nav>
  </section>
</aside>
