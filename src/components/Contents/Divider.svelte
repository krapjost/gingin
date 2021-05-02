<script lang="ts">
    import Tailwindcss from '../../Tailwindcss.svelte';
    export let heading:string;
</script>
<style>
    h1 {
        font-family: GmarketSansBold;
    }
</style>
<Tailwindcss/>
<div class="text-gin pt-24 w-full flex flex-row items-center">
    <h1 class="text-3xl sm:text-4xl lg:text-5xl min-w-max pr-3 md:pr-10 font-bold inline-block">
        {heading}
    </h1>
    <div class="inline-block border-gin border-t-4 md:border-t-8 mb-2 w-full h-1"/>
</div>