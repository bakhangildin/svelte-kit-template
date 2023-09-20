<script>
  import { page } from "$app/stores";
  import { DarkMode, Navbar, NavLi, NavUl } from "flowbite-svelte";
  import "../app.css";
  $: activeUrl = $page.url.pathname;
</script>

{#key activeUrl}
  <Navbar let:hidden let:toggle>
    <NavUl {hidden} {activeUrl}>
      <NavLi href="/">Home</NavLi>
      <NavLi href="/page">Page</NavLi>
    </NavUl>
    <DarkMode />
  </Navbar>
{/key}

<slot />
