<script>
    import Layout from "../__layout.svelte";

    import whiteLayer1 from "$lib/assets/curves/white_layer1.svg"
    import blueLayer1 from "$lib/assets/curves/blue_layer1.svg"
    import blueLayer2 from "$lib/assets/curves/blue_layer2.svg"
    

    import Card from "../components/Card.svelte";
</script>

<Layout active="About">
    <section class="h-[700px] bg-white flex flex-col justify-center items-center">
        <div class="w-fit fel font-semibold text-8xl text-MainBlue text-center my-auto leading-[80px] ">
            <h1>What</h1>
            <h1>We</h1>
            <h1>Teach</h1>
        </div>
        <div class="max-w-[70vw] gap-[2vw] flex-wrap justify-center text-MainBlue font-semibold z-10 text-4xl text-center my-auto flex">
                <Card subject="Mandarin"></Card>
                <Card subject="Math"></Card>
                <Card subject="Physics"></Card>
                <Card subject="Biology"></Card>
                <Card subject="Chemistry"></Card>
                <Card subject="More..."></Card>
        </div>
    </section>
    <div class="relative h-48 m-0 p-0">
        <img src={blueLayer1} alt="" class="w-full absolute bottom-[-5px]">
    </div>
    <section class="h-[700px] bg-MainBlue">

    </section>
</Layout>
