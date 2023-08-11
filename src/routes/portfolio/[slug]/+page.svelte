<script>
    export let data;

    const item = data.items.find(obj => obj.slug === data.slug)
</script>

<h1 class="text-2xl font-bold text-center py-52">{item?.title}</h1>