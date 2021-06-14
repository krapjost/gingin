<script lang="ts">
    import Tailwindcss from '../../Tailwindcss.svelte'

    export let mainText:string;
    export let subText:string;
    
</script>
<style>

  h2 {
    font-family: 'Gmarket Sans';
    word-break: keep-all;
  }


</style>
<Tailwindcss/>
<div class="border-t-2 border-gin mt-12 md:mt-24 w-full"/>

<section class="text-gin">
    <div class="w-full h-screen flex flex-col items-center justify-center">
        <h2 class="text-3xl sm:text-4xl md:text-5xl lg:text-6xl mb-5">{subText}</h2>
        <h1 class="text-3xl sm:text-4xl md:text-5xl lg:text-6xl font-bold">{mainText}</h1>
    </div>
</section>