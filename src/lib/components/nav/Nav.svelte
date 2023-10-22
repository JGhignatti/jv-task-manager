<script lang="ts">
  import NavItem from './NavItem.svelte';

  const navItems: { path: string; name: string }[] = [
    {
      path: '/s/main',
      name: 'Main',
    },
    {
      path: '/s/work',
      name: 'Work',
    },
    {
      path: '/s/extra',
      name: 'Extra',
    },
  ];

  let open = false;

  $: openBasedNavContainerClasses = open ? 'left-0' : '-left-80';
</script>

<aside class="fixed left-0 top-0 h-full lg:relative">
  <button
    class="m-2 flex h-12 w-12 items-center justify-center rounded-full bg-blue-50 outline outline-8 outline-blue-100 lg:hidden"
    on:click={() => (open = !open)}
  >
    <span class="material-symbols-outlined text-blue-600">
      {open ? 'close' : 'menu'}
    </span>
  </button>

  <section
    class="absolute bottom-0 top-0 mt-16 h-[calc(100%-64px)] w-80 p-4 transition-all duration-300 ease-in-out lg:relative lg:left-0 lg:mt-0 lg:h-full lg:p-6 {openBasedNavContainerClasses}"
  >
    <nav class="h-full rounded-lg bg-blue-100 shadow-lg shadow-zinc-400 lg:shadow-none">
      <section class="flex justify-center py-8">
        <a href="/" class="flex items-center">
          <span class="material-symbols-outlined text-5xl text-blue-600">task_alt</span>
          <h1 class="text-center text-2xl font-bold">JV Task Manager</h1>
        </a>
      </section>

      <section class="p-4">
        <h3 class="mb-2 font-bold uppercase">Spaces</h3>
        <ul class="flex flex-col gap-1">
          {#each navItems as item}
            <NavItem {item} />
          {/each}
        </ul>
      </section>
    </nav>
  </section>
</aside>
