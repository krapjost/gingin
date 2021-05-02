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
    export let subHeading:string;
    export let subText:string;
</script>
<style>
  h1 {
    word-break: keep-all;
  }
  p {
    font-family: GmarketSansLight;
    word-break: keep-all;
  }
  .square {
    background: #000;
    width: 50vw;
    height: 50vw;
  }
  .sm-square {
    background: #000;
    width: 40vw;
    height: 40vw;
  }
  .square-wrapper {
    height: 60vw;
    max-width: 800px;
  }

</style>
<Tailwindcss/>

<section class="text-gin">
    <div class="container mx-auto flex flex-col px-5 pt-24 justify-center items-center">
      <div class="square-wrapper md:max-h-96 md:mb-12 relative w-full flex flex-row ">
        <div class="square md:max-h-96 md:max-w-sm absolute rounded z-10 left-1/2 transform -translate-x-1/2">
          <img class="h-full object-fill object-center " alt="hero" src={imgs.s1}>
        </div> 

        <div class="sm-square md:max-h-80 md:max-w-xs absolute opacity-60 rounded transform translate-y-5 right-0">
          <img class="h-full object-fill object-center " alt="hero" src={imgs.s2}>
        </div> 
        
        
        <div class="sm-square md:max-h-80 md:max-w-xs absolute opacity-60 rounded transform translate-y-5">
          <img class="h-full object-fill object-center " alt="hero" src={imgs.s3}>
        </div> 

      </div>
      <div class="w-full md:w-2/3 flex flex-col mb-16 items-center text-center">
        <h1 class="sm:text-5xl text-3xl mb-4 h-auto whitespace-pre-line">
          {subHeading}
        </h1>
        <h1 class="sm:text-2xl text-xl h-auto whitespace-pre-line">
          {mainText}
        </h1>
        <p class="leading-relaxed whitespace-pre-line">
          {subText}
        </p>
      </div>
    </div>
  </section>