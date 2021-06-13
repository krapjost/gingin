<script>
    import Tailwindcss from '../../Tailwindcss.svelte';
    import {Slider as imgs} from '../../constants/imageData';
    import { onMount } from 'svelte';

    const d = {
        center: "translate-x-0",
        left: "-translate-x-full",
        right: "translate-x-full",
    }
    const itemClasses = "absolute ease-in-out duration-500 transition-transform transform-gpu object-cover object-center w-full h-full"
    const circleBtnClasses = "bg-white w-2 h-2 rounded-full"
    const x = {
        one: d.right,
        two: d.left,
        thr: d.center,
    }
    const prev = ({center,left,right}) => {
        for (const key in imgs) {
            const cli = imgs[key].i.classList;
            const getD = (pos) => cli.contains(pos);
            // console.log(center)
            if (getD(center)) {
                cli.replace(center, left)
                cli.add("z-20")
                cli.remove("z-0", "z-10")
            } else if (getD(right)) {
                cli.replace(right, center)
                cli.add("z-10")
                cli.remove("z-20", "z-0")
            } else {
                cli.replace(left, right)
                cli.add("z-0")
                cli.remove("z-10", "z-20")
      
            }
        }
    }
    const next = ({center,left,right}) => {
        for (const key in imgs) {
            const cli = imgs[key].i.classList;
            const getD = (pos) => cli.contains(pos);
            // console.log(center)
            if (getD(center)) {
                cli.replace(center, right)
                cli.add("z-20")
                cli.remove("z-10", "z-0")
            } else if (getD(left)) {
                cli.replace(left, center)
                cli.add("z-10")
                cli.remove("z-20", "z-0")
            } else {
                cli.replace(right, left)
                cli.add("z-0")
                cli.remove("z-20", "z-10")
            }
        }
    }

    onMount(() => {
        
    setInterval(()=>next(d), 4000)
  }); 

</script>
<Tailwindcss/>
<style>
    h2,button {
        font-family: 'Gmarket sans';
    }
</style>
<div class="w-full h-screen flex justify-center relative overflow-hidden bg-black">
    <img bind:this={imgs.one.i} class="{itemClasses} {x.one}" src={imgs.one.s} alt="test"/>
    <img bind:this={imgs.two.i} class="{itemClasses} {x.two}" src={imgs.two.s} alt="test"/>
    <img bind:this={imgs.thr.i} class="{itemClasses} {x.thr}" src={imgs.thr.s} alt="test"/>

    <div class="z-30 flex flex-row gap-2 absolute bottom-10 left-1/2 transform -translate-x-1/2 text-white">
        <div class={circleBtnClasses}/>
        <div class={circleBtnClasses}/>
        <div class={circleBtnClasses}/>
    </div>
    <div class="relative max-w-screen-xl w-full">
        <div on:click={()=>prev(d)} class="absolute transform rounded-full top-1/2 -translate-y-1/2 left-2 w-10 h-10 z-30"> 
            <img src="assets/images/mainSlider/arrow_left.png" alt="arrow" class="transform scale-50 -translate-y-4"/>
        </div>
        <div on:click={()=>next(d)} class="absolute transform rounded-full top-1/2 -translate-y-1/2 right-2 w-10 h-10 z-30">
            <img src="assets/images/mainSlider/arrow_right.png" alt="arrow" class="transform scale-50 -translate-y-4"/>
        </div>
        <div class="absolute text-white transform top-2/4 -translate-y-1/2 left-1/4 z-30">
            <h2 class="text-2xl mb-1 sm:text-3xl lg:text-5xl lg:mb-3 font-thin">
                자연을 드리는
            </h2>
            <h1 class="text-4xl sm:text-6xl lg:text-7xl mb-5">
                풍경원입니다
            </h1>
            <button class="shadow-md ring-1 ring-white ring-opacity-50 hover:bg-gin hover:ring-gin transform transition-all rounded-full pt-2 pb-1 px-3 text-sm">풍경원 둘러보기</button>
        </div>
    </div>
</div>