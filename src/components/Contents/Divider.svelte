<script lang="ts">
    import Tailwindcss from '../../Tailwindcss.svelte';
    export let heading:string;
</script>
<style>
    h1 {
        font-family: GmarketSansBold;
        word-break: keep-all;
    }
    @media (min-width: 1024px) {
    h1 {
        font-size: 3.55rem;
        line-height: 1
    }
}
</style>
<Tailwindcss/>
<div class="text-gin pt-60 px-5 xl:px-0 w-full flex flex-row items-center mb-16">
    <h1 class="text-3xl md:min-w-max sm:min-w-min sm:text-5xl pr-3 md:pr-10 font-bold inline-block">
        {heading}
    </h1>
    <div class="inline-block bg-gin mb-2 w-full sm:h-3 h-2"/>
</div>