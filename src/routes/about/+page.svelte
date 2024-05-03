<script>
    import Layout from "../__layout.svelte";

    import whiteLayer1 from "$lib/assets/curves/white_layer1.svg"
    import blueLayer1 from "$lib/assets/curves/blue_layer1.svg"
    import blueLayer2 from "$lib/assets/curves/blue_layer2.svg"
</script>

<Layout active="About">
    <section class="h-[700px] bg-white border-4 border-red-500 flex flex-wrap justify-center gap-[18vw]">
        <div class="w-fit font-semibold text-8xl text-MainBlue text-center my-auto leading-[80px] ">
            <h1>What</h1>
            <h1>We</h1>
            <h1>Teach</h1>
        </div>
        <div class="border-green-300 border-4 w-[500px] text-MainBlue font-semibold text-4xl text-center my-auto">
            <ul class="">
                <li>Mandarin</li>
                <li>Physics</li>
                <li>Math</li>
                <li>Chemistry</li>
                <li>Biology</li>
                <li>Civics</li>
                <li>Religion</li>
                <li>And others!</li>
            </ul>
        </div>
    </section>
    <div class="relative h-48 m-0 p-0">
        <img src={blueLayer1} alt="" class="w-full absolute bottom-[-5px]">
    </div>
    <section class="h-[700px] bg-MainBlue">

    </section>
</Layout>
