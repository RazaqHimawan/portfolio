<script lang="ts">
import '../app.css';
import Header from '$lib/components/Header.svelte';
import Sidebar from '$lib/components/Sidebar.svelte';

let isOpen = false;
$: drawer = isOpen ? 'left-0' : '-left-60';
</script>

<div
  class="h-full min-h-screen bg-background dark:bg-dark-background text-text dark:text-dark-text md:ml-60"
>
  <Header
    {isOpen}
    hamburgerClick={() => (isOpen = !isOpen)}
  />
  <Sidebar
    {drawer}
    {isOpen}
    modalClick={() => (isOpen = false)}
  />

  <main class="p-8">
    <slot />
  </main>
</div>
