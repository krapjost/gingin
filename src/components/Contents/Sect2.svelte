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

    let selected = 'foo';
	  let options = [
		'foo',
		'bar',
		'baz'
	  ]

</script>
<style>

  p {
    font-family: 'Gmarket Sans';
    word-break: keep-all;
  }

  img {
  width: 100%;
  height: 100%;
  border-radius: 10px;
  object-fit: cover;
}

.cards {
  position: relative;
  width: 100%;
  height: 100%;
  margin-bottom: 20px;
}

#item-1:checked ~ .cards #song-3, #item-2:checked ~ .cards #song-1, #item-3:checked ~ .cards #song-2 {
  transform: translatex(-40%) scale(.8);
  opacity: .4;
  z-index: 0;
}

#item-1:checked ~ .cards #song-2, #item-2:checked ~ .cards #song-3, #item-3:checked ~ .cards #song-1 {
  transform: translatex(40%) scale(.8);
  opacity: .4;
  z-index: 0;
}

#item-1:checked ~ .cards #song-1, #item-2:checked ~ .cards #song-2, #item-3:checked ~ .cards #song-3 {
  transform: translatex(0) scale(1);
  opacity: 1;
  z-index: 1;
  
}

#item-1:checked ~ .cards #song-1 img, #item-2:checked ~ .cards #song-2 img, #item-3:checked ~ .cards #song-3 img{
  box-shadow: 0px 0px 5px 0px rgba(81, 81, 81, 0.47);
}


input[type=radio] {
  display: none;
}

.card {
  position: absolute;
  width: 60%;
  height: 100%;
  left: 0;
  right: 0;
  margin: auto;
  transition: transform .4s ease;
  cursor: pointer;
}

.card-container {
  width: 100%;
  max-width: 800px;
  max-height: 600px;
  height: 500px;
  transform-style: preserve-3d;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
}

.cards {
  position: relative;
  width: 100%;
  height: 100%;
  margin-bottom: 20px;
}

</style>
<Tailwindcss/>

<section class="text-gin">
    <div class="container mx-auto flex flex-col px-5 pt-24 justify-center items-center">

      <div class="card-container">
        <input type="radio" name="slider"  id="item-1" checked>
        <input type="radio" name="slider"  id="item-2">
        <input type="radio" name="slider"  id="item-3">

        <div class="cards">

          <label class="card" id="song-1" for="item-1" >
            <img alt="hero" src={imgs.s1}>
          </label> 
          
          <label class="card" id="song-2" for="item-2" >
            <img alt="hero" src={imgs.s3}>
          </label> 
          
          <label class="card" id="song-3" for="item-3" >
            <img alt="hero" src={imgs.s2}>
          </label> 
        </div>
          
      </div>

      {#each options as title}
      <div class="w-full md:w-2/3 flex flex-col mb-16 items-center text-center">
        <h1 class="sm:text-5xl text-3xl mb-4 h-auto whitespace-pre-line translate-x-10">
          {subHeading} {title}
        </h1>
        <h1 class="sm:text-2xl text-xl h-auto whitespace-pre-line">
          {mainText}
        </h1>
        <p class="leading-relaxed whitespace-pre-line">
          {subText}
        </p>
      </div>
      {/each}

  </section>