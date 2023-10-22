<script lang="ts">
  import { page } from '$app/stores';

  export let item: { path: string; name: string };

  $: isLinkActive = $page.url.pathname.includes(item.path);
  $: activeBasedRounded = isLinkActive ? 'rounded-r' : 'rounded';
</script>

<li>
  <a
    href={item.path}
    class="{activeBasedRounded} group relative flex w-full p-2 before:absolute before:-left-1 before:bottom-0 before:top-0 before:w-1 before:rounded-l hover:bg-blue-200/50"
    class:active={isLinkActive}
  >
    <span class="transition-transform group-hover:translate-x-1">{item.name}</span>
  </a>
</li>

<style lang="postcss">
  .active {
    @apply bg-blue-200 before:bg-blue-500;
  }

  .active span {
    @apply translate-x-1;
  }
</style>
