<script>
    import Tailwindcss from '../../Tailwindcss.svelte'
    import Devider from './Divider.svelte'
    import SectOne from './Sect1.svelte'
    import SectTwo from './Sect2.svelte'
    import SectThr from './Sect3.svelte'
    import SectFour from './Sect4.svelte'
    import {contents as t} from '../../constants/textData'
    import {Main as i} from '../../constants/imageData'

</script>
<Tailwindcss/>
<aria class="w-full">
    <article class="max-w-screen-xl mx-auto flex flex-col">
        <Devider heading={t.one.h}/>
        <div class="mb-80">

            <SectOne mainText={t.one.m} subText={t.one.s} imgs={i.one} direction="right"/>
            <SectOne mainText={t.one.m} subText={t.one.s} imgs={i.two} direction="left"/>
            <SectOne mainText={t.one.m} subText={t.one.s} imgs={i.thr} direction="right"/>
        </div>
        <Devider heading={t.two.h} />
        <SectTwo subHeading={t.two.sh} mainText={t.two.m} subText={t.two.s} imgs={i.four} direction="center"/>
        <Devider heading={t.thr.h}/>
        <SectThr mainText={t.thr.m1} subText={t.thr.s1} imgs={i.one} direction="right"/>
        <SectThr mainText={t.thr.m2} subText={t.thr.s2} imgs={i.two} direction="left"/>
        <SectThr mainText={t.thr.m3} subText={t.thr.s3} imgs={i.thr} direction="right"/>
        <SectFour mainText={t.four.m} subText={t.four.s}/>

    </article>
</aria>