<script lang="ts">
    export let data
    let currentCategory = 'All'
    let portfolioItems = data.items

    function changeCategory(newCategory: string) {
        currentCategory = newCategory;
        filterPortfolio()
    }

    function filterPortfolio() {
        portfolioItems = data.items.filter(item => {
            return item.category === currentCategory || currentCategory === 'All';
        })
    }
</script>

<section class="bg-white">
    <div class="container px-6 mx-auto">

        <div class="flex py-4 mt-4 overflow-x-auto overflow-y-hidden md:justify-center">
            {#each data.categories as category}

                {#if currentCategory === category}
                    <button
                        class="h-12 px-8 py-2 -mb-px text-sm text-center text-blue-600 bg-transparent border-b-2 border-blue-500 sm:text-base dark:border-blue-400 whitespace-nowrap focus:outline-none">
                        {category}
                    </button>
                {:else}
                    <button
                        on:click={() => changeCategory(category)}
                        class="h-12 px-8 py-2 -mb-px text-sm text-center text-gray-700 bg-transparent border-b-2 border-gray-200 sm:text-base cursor-base focus:outline-none hover:border-gray-400">
                        {category}
                    </button>
                {/if}

            {/each}
            
        </div>

        <section class="mt-8 lg:mt-12 lg:grid lg:grid-cols-2 xl:grid-cols-4 lg:gap-12">
            {#each portfolioItems as { title, slug, category, image }}
                <article class="">
                    <div class="">
                        <p class="text-lg tracking-wider text-blue-500 uppercase">{category}</p>
                        <h2 class="mt-2 text-2xl font-semibold text-gray-800 capitalize">{title}</h2>
                    </div>

                    <div class="mt-4">
                        <a href={`/portfolio/${slug}`}>
                            <img class="object-cover w-full h-64 rounded-lg md:h-96"
                                src={image}
                                alt={title}>
                        </a>
                    </div>
                </article>
            {/each}
        </section>
    </div>
</section>