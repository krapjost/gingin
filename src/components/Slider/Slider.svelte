<script>
    import Tailwindcss from '../../Tailwindcss.svelte';
    import {Slider as imgs} from '../../constants/imageData';
    const d = {
        cntr: "translate-x-0",
        left: "-translate-x-full",
        rght: "translate-x-full",
    }
    const itemClasses = "absolute ease-in-out duration-500 transition-transform transform-gpu object-cover object-center w-full h-full"
    const x = {
        one: d.rght,
        two: d.left,
        thr: d.cntr,
    }
    const prev = ({cntr,left,rght}) => {
        for (const key in imgs) {
            const cli = imgs[key].i.classList;
            const getD = (pos) => cli.contains(pos);
            // console.log(cntr)
            if (getD(cntr)) {
                cli.replace(cntr, left)
                cli.add("z-20")
                cli.remove("z-0", "z-10")
            } else if (getD(rght)) {
                cli.replace(rght, cntr)
                cli.add("z-10")
                cli.remove("z-20", "z-0")
            } else {
                cli.replace(left, rght)
                cli.add("z-0")
                cli.remove("z-10", "z-20")
      
            }
        }
    }
    const next = ({cntr,left,rght}) => {
        for (const key in imgs) {
            const cli = imgs[key].i.classList;
            const getD = (pos) => cli.contains(pos);
            // console.log(cntr)
            if (getD(cntr)) {
                cli.replace(cntr, rght)
                cli.add("z-20")
                cli.remove("z-10", "z-0")
            } else if (getD(left)) {
                cli.replace(left, cntr)
                cli.add("z-10")
                cli.remove("z-20", "z-0")
            } else {
                cli.replace(rght, left)
                cli.add("z-0")
                cli.remove("z-20", "z-10")
            }
        }
    }

</script>

<Tailwindcss/>
<div class="w-full h-screen flex relative overflow-hidden bg-black">
    <img bind:this={imgs.one.i} class="{itemClasses} {x.one}" src={imgs.one.s} alt="test"/>
    <img bind:this={imgs.two.i} class="{itemClasses} {x.two}" src={imgs.two.s} alt="test"/>
    <img bind:this={imgs.thr.i} class="{itemClasses} {x.thr}" src={imgs.thr.s} alt="test"/>
    <div class="absolute text-white transform top-2/4 -translate-y-1/2 left-1/4 z-50">
        <h2 class="text-2xl mb-1 sm:text-3xl lg:text-5xl lg:mb-3">
            자연을 드리는
        </h2>
        <h1 class="text-4xl sm:text-6xl lg:text-7xl">
            풍경원입니다
        </h1>
    </div>
    <div on:click={()=>prev(d)} class="absolute transform rounded-full top-1/2 -translate-y-1/2 left-2 bg-black w-10 h-10 z-30"/>
    <div on:click={()=>next(d)} class="absolute transform rounded-full top-1/2 -translate-y-1/2 right-2 bg-black w-10 h-10 z-30"/>
</div>