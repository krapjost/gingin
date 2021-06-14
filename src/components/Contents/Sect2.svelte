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

.info-content {
  transition: all .5s ease-out;
  transition-delay: .1s;
}

.info-section #info-1, .info-section #info-2, .info-section #info-3{
  transform: translateY(40%);
  opacity: 0;
}

#item-1:checked ~ .info-section #info-1, #item-2:checked ~ .info-section #info-2, #item-3:checked ~ .info-section #info-3 {
  transform: translateY(5%);
  opacity: 1;
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


        <div class="info-section relative w-full">
  
          <label for="item-1" id="info-1" class="info-content absolute top-3 w-full flex flex-col mb-16 items-center text-center">
            <h1 class="sm:text-5xl text-3xl mb-4 h-auto whitespace-pre-line translate-x-10">
              산양삼 꿀차
            </h1>
            <h1 class="sm:text-2xl text-xl h-auto whitespace-pre-line">
              {mainText}
            </h1>
            <p class="leading-relaxed whitespace-pre-line">
              {subText}
            </p>
          </label>
          <label for="item-2" id="info-2" class="info-content absolute top-3 w-full flex flex-col mb-16 items-center text-center">
            <h1 class="sm:text-5xl text-3xl mb-4 h-auto whitespace-pre-line translate-x-10">
              산양삼 액기스
            </h1>
            <h1 class="sm:text-2xl text-xl h-auto whitespace-pre-line">
              {mainText}
            </h1>
            <p class="leading-relaxed whitespace-pre-line">
              {subText}
            </p>
          </label>
          <label for="item-3" id="info-3" class="info-content absolute top-3 w-full flex flex-col mb-16 items-center text-center">
            <h1 class="sm:text-5xl text-3xl mb-4 h-auto whitespace-pre-line translate-x-10">
              산양삼 캔디
            </h1>
            <h1 class="sm:text-2xl text-xl h-auto whitespace-pre-line">
              {mainText}
            </h1>
            <p class="leading-relaxed whitespace-pre-line">
              {subText}
            </p>
          </label>
        </div>
      </div>
      

  </section>