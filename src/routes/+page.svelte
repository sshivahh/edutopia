<script>
    import Layout from "./__layout.svelte";
    import edutopia from "$lib/assets/edutopia/edutopia.svg"
    import blob from "$lib/assets/curves/blob.svg"

    import whiteLayer1 from "$lib/assets/curves/white_layer1.svg"
    import blueLayer1 from "$lib/assets/curves/blue_layer1.svg"
    import blueLayer2 from "$lib/assets/curves/blue_layer2.svg"
    
    import Polaroid from "./components/Polaroid.svelte";
    import crew1 from "$lib/assets/images/cropped1.jpeg"
    import crew2 from "$lib/assets/images/cropped2.jpeg"
    import crew3 from "$lib/assets/images/cropped3.jpeg"
    import crew4 from "$lib/assets/images/cropped4.jpeg"
    import crew5 from "$lib/assets/images/cropped5.jpeg"

</script>

<Layout active="Home">
    <section class=" bg-white h-[700px] flex justify-start pl-[15vw] pr-[8vw] items-center gap-32 b-96 lg:gap-[15vw]">
        <div class="blobDiv relative w-[500px] h-[500px] flex hover:scale-110 transition-al duration-300 z-10">
            <img src={blob} alt="" id="blob">
            <img src={edutopia} id="edutopia" alt="" class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 rounded-[50%] -z-1">
        </div>
        <div class="max-w-[30vw]">
            <h2 class="text-[80px] text-MainBlue font-semibold">Edutopia</h2>
            <p>Selamat datang di Edutopia! Tempat belajar yang menginspirasi, memberikan pengalaman pembelajaran yang mendalam dan penuh kesempatan. Bergabunglah dengan kami untuk menjelajahi dunia pengetahuan dan menciptakan masa depan yang cerah.</p>
        </div>
    </section>
    <div class="relative h-48 m-0 p-0">
        <img src={blueLayer1} alt="" class="w-full absolute bottom-[-5px]">
    </div>
    <section class="bg-MainBlue h-[800px] flex justify-center pl-[3vw] pr-[5vw] gap-16">
        <div class="w-[500px] text-center p-32 flex flex-col">
            <h2 class="text-[80px] text-white font-bold -mb-12">Meet</h2>
            <h2 class="text-[80px] text-white -mb-12">Our</h2>
            <h2 class="text-[80px] text-white font-bold">Team</h2>
        </div>
        <div class="relative w-[800px] h-[600px] z-10">
            <Polaroid polaroidImg={crew1} extraClass="absolute top-0 left-0 -rotate-6 saturate-0 hover:scale-[1.3] hover:rotate-0 hover:z-[100] hover:saturate-100 transition-all duration-300" />
            <Polaroid polaroidImg={crew2} extraClass="absolute top-0 right-0 rotate-12 saturate-0 hover:scale-[1.3] hover:rotate-0 hover:z-[100] hover:saturate-100 transition-all duration-300 transition-all duration-300"/>
            <Polaroid polaroidImg={crew3} extraClass="absolute top-1/2 left-1/2 saturate-0 -translate-x-1/2 -translate-y-1/2 rotate-6 hover:scale-[1.3] hover:rotate-0 hover:z-[100] hover:saturate-100 transition-all duration-300 transition-all duration-300"/>
            <Polaroid polaroidImg={crew4} extraClass="absolute bottom-0 left-0 saturate-0 rotate-6 hover:scale-[1.3] hover:rotate-0 hover:z-[100] hover:saturate-100 transition-all duration-300 transition-all duration-300"/>
            <Polaroid polaroidImg={crew5} extraClass="absolute bottom-0 right-0 saturate-0 -rotate-6 hover:scale-[1.3] hover:rotate-0 hover:z-[100] hover:saturate-100 transition-all duration-300 transition-all duration-300" />
        </div>
    </section>
    <div class="relative m-0 p-0">
        <img src={whiteLayer1} alt="" class="w-full absolute bottom-[-60px]">
    </div>
    <section class="bg-white h-[700px] relative">

    </section>
    <div class="relative m-0 p-0">
        <img src={blueLayer2} alt="" class="w-full absolute bottom-0">
    </div>
    <section class="bg-MainBlue h-[800px] relative">


    </section>
</Layout>


<style>
    #blob{
        filter: drop-shadow(0px 0px 60px rgb(145, 216, 244));
    }
    #edutopia {
        animation: floatUpDown 2.2s infinite alternate ease-in-out;
    }

    @keyframes floatUpDown {
        0% {
            transform: translateX(-50%) translateY(-55%);
        }
        100% {
            transform: translateX(-50%) translateY(-45%); /* Adjust the value to control the floating range */
        }
    }


</style>
