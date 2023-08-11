<script>
  import { page } from "$app/stores";

    const navItems = [
        { href: '/', label: 'Home' },
        { href: '/sobre', label: 'Sobre' },
        { href: '/portfolio', label: 'Portfolio' },
        { href: '/contato', label: 'Contato' },
        { href: '/faq', label: 'Perguntas Frequentes' },
    ]
</script>

<nav>
    {#each navItems as {href, label}}
        {#if $page.url.pathname === href}
            <a {href} class="text-gray-800 transition-colors duration-300 transform border-b-2 border-blue-500 mx-1.5 sm:mx-6">{label}</a>
        {:else}
            <a
                {href}
                class="border-b-2 border-transparent hover:text-gray-800 transition-colors duration-300 transform hover:border-blue-500 mx-1.5 sm:mx-6"
            >
                {label}
            </a>  
        {/if}  
    {/each}   
</nav>