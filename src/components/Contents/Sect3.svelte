<script lang="ts">
    import Tailwindcss from '../../Tailwindcss.svelte'
    type imageData = {
      s:string
      s1:string
      s2:string
      s3:string
    }
    export let imgs:imageData;
    export let mainText:string;
    export let subText:string;
    export let direction:string;
</script>
<style>
  h1 {
    word-break: keep-all;
  }
  p {
    font-family: 'Gmarket Sans';
    word-break: keep-all;
  }


</style>
<Tailwindcss/>
<div class="border-t-2 border-gin mt-12 md:mt-24 w-full"/>
{#if direction === "right"}
<section class="text-gin">
    <div class="container mx-auto my-auto flex md:flex-row flex-col items-center md:pt-24 pt-12">
      
      <div class="lg:flex-grow md:w-1/2 lg:pr-14 md:pr-12 flex flex-col md:items-end md:text-right md:mb-0 items-center text-center lg:items-end lg:text-right">
        <h1 class="sm:text-3xl text-2xl mb-4 h-auto font-bold">
          {mainText}
        </h1>
        <p class="my-4 md:text-xl text-lg font-thin leading-relaxed whitespace-pre-line">{subText}</p>
      </div>
      
      <div class="my-4 lg:pl-5 md:w-1/2 w-5/6 flex items-center">
        <div class="w-full aspect-w-16 aspect-h-9">
          <img class="object-cover object-center rounded" alt="상품 사진" src={imgs.s}>
        </div>
      </div>

    </div>
  </section>
{:else if direction === "left"}
  <section class="text-gin ">
    <div class="container mx-auto my-auto flex md:flex-row flex-col items-center md:pt-24 pt-12">
      
      <div class="my-4 lg:pr-5 md:w-1/2 w-5/6 flex items-center">
        <div class="w-full aspect-w-16 aspect-h-9">
          <img class="object-cover object-center rounded" alt="상품 사진 2" src={imgs.s}>
        </div>
      </div>
      
      <div class="lg:flex-grow md:w-1/2 lg:pl-14 md:pl-12 flex flex-col md:items-start md:text-left items-center text-center">
        <h1 class="sm:text-3xl text-2xl mb-4 font-bold">
          {mainText}
        </h1>
        <p class="my-4 md:text-xl text-lg font-thin leading-relaxed whitespace-pre-line">
          {subText}
        </p>
      </div>

    </div>
  </section>
  {/if}