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

    let blobDiv;
    let polaroids = [];

    function handleMouseMove(event, element) {
        const rect = element.getBoundingClientRect();
        const mouseX = event.clientX;
        const mouseY = event.clientY;
        const centerX = rect.left + rect.width / 2;
        const centerY = rect.top + rect.height / 2;

        const offsetX = (mouseX - centerX) * 0.2;
        const offsetY = (mouseY - centerY) * 0.2;

        element.style.transform = `translate(${offsetX}px, ${offsetY}px) scale(1.1)`;
    }

    function handleMouseLeave(element) {
        element.style.transform = `translate(0, 0) scale(1)`;
    }

    function addMouseListeners(element) {
        element.addEventListener('mousemove', (event) => handleMouseMove(event, element));
        element.addEventListener('mouseleave', () => handleMouseLeave(element));
    }

    $: if (blobDiv) addMouseListeners(blobDiv);
    $: polaroids.forEach(addMouseListeners);
</script>

<Layout active="Home">
    <section class="bg-white h-[700px] flex flex-wrap lg:flex-nowrap mt-12 lg:mt-0 justify-center  items-center gap-8 lg:gap-[15vw]">
        <div bind:this={blobDiv} class="blobDiv relative w-[350px] h-[350px] lg:w-[500px] lg:h-[500px] flex hover:scale-110 transition-al duration-300 z-10">
            <img src={blob} alt="" id="blob">
            <img src={edutopia} id="edutopia" alt="" class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 rounded-[50%] -z-1 w-56">
        </div>
        <div class="w-[75vw] lg:max-w-[30vw]">
            <h2 class="text-6xl w-full text-center lg:text-start lg:text-[80px] text-MainBlue font-semibold">Edutopia</h2> 
            <p class="text-sm md:text-lg mt-8 text-center lg:text-start lg:text-lg">Selamat datang di Edutopia! Tempat belajar yang menginspirasi, memberikan pengalaman pembelajaran yang mendalam dan penuh kesempatan. Bergabunglah dengan kami untuk menjelajahi dunia pengetahuan dan menciptakan masa depan yang cerah.</p>
        </div>
    </section>
    <div class="relative h-48 m-0 p-0">
        <img src={blueLayer1} alt="" class="w-full absolute bottom-[-5px]">
    </div>
    <section class="bg-MainBlue h-[800px] flex flex-wrap lg:flex-nowrap justify-center items-center pl-[3vw] pr-[5vw] lg:pt-[10vw] xl:pt-0 lg:gap-16">
        <div class="w-[500px] h-fit text-center lg:p-32 flex flex-col">
            <h2 class="text-[80px] text-white font-bold -mb-12">Meet</h2>
            <h2 class="text-[70px] text-white -mb-14">Our</h2>
            <h2 class="text-[80px] text-white font-bold">Team</h2>
        </div>
        <div class="relative w-[80vw] lg:w-[800px] mt-[10vw] xl:mt-0  h-[70vw] md:h-[50vw] lg:h-[30vw] z-[40]">
            <Polaroid polaroidImg={crew1} extraClass="absolute top-0 left-0 -rotate-6  saturate-0 hover:scale-[1.3] hover:rotate-0 hover:z-[100] hover:saturate-100 transition-all duration-300" />
            <Polaroid polaroidImg={crew2} extraClass="absolute top-0 right-0 rotate-12 saturate-0 hover:scale-[1.3] hover:rotate-0 hover:z-[100] hover:saturate-100 transition-all duration-300 transition-all duration-300"/>
            <Polaroid polaroidImg={crew3} extraClass="absolute top-1/2 left-1/2 saturate-0 -translate-x-1/2 -translate-y-1/2 rotate-6 hover:scale-[1.3] hover:rotate-0 hover:z-[100] hover:saturate-100 transition-all duration-300 transition-all duration-300"/>
            <Polaroid polaroidImg={crew4} extraClass="absolute bottom-0 left-0 saturate-0 rotate-6 hover:scale-[1.3] hover:rotate-0 hover:z-[100] hover:saturate-100 transition-all duration-300 transition-all duration-300"/>
            <Polaroid polaroidImg={crew5} extraClass="absolute bottom-0 right-0 saturate-0 -rotate-6 hover:scale-[1.3] hover:rotate-0 hover:z-[100] hover:saturate-100 transition-all duration-300 transition-all duration-300" />
        </div>
    </section>
    <div class="relative h-48 m-0 p-0 bg-MainBlue z-[10]">
        <img src={whiteLayer1} alt="" class="w-full absolute bottom-0">
    </div>
    <section class="bg-white h-[700px] relative flex flex-wrap justify-center items-center gap-10 lg:gap-12 xl:gap-32 mb-12 px-12">
        <div>
            <iframe title="Edutopia 1" class="w-[70vw] md:w-[35vw] md:min-w-[400px] z-[100] drop-shadow-2xl rounded-2xl md:hover:scale-110 transition-all duration-300" src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d247.89131618728229!2d106.66042711297462!3d-6.229273327383737!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2e69fb7e9cf179bb%3A0x8706374b1b477476!2sBimbel%20Edutopia!5e0!3m2!1sen!2sid!4v1721664918935!5m2!1sen!2sid" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
        </div>
        <div class="text-center md:text-start">
            <h2 class="text-[40px] lg:text-[50px] text-MainBlue font-bold ">Our</h2>
            <h2 class="text-[60px] lg:text-[80px] text-MainBlue font-bold -mt-8">Location</h2>
            <button class="bg-MainBlue drop-shadow-md text-white text-xl font-semibold px-3 py-2 rounded-2xl duration-300 transition-all hover:opacity-80 hover:scale-110">
                <a href="https://maps.app.goo.gl/7XKFEzS2yVFbK6kM9" target="_blank">
                    View on Google Maps
                </a>
            </button>
        </div>
    </section>
    <div class="relative h-48 m-0 p-0 -z-40">
        <img src={blueLayer2} alt="" class="w-full z-0 absolute bottom-0">
    </div>
    <section class="bg-MainBlue h-[800px] relative text-center flex flex-col justify-center items-center gap-24">
        <div class="-mt-64">
            <h2 class="text-white font-bold text-[100px]">Join Us</h2>
            <p class="text-white font-semibold text-[30px] -mt-6">Leave a message!</p>
        </div>    
        <button class="bg-white text-MainBlue py-2 px-5 text-4xl font-bold rounded-3xl transition-all duration-300 hover:scale-110 w-fit drop-shadow-xl">
            <a href="https://wa.me/6287808230745?text=Halo, saya ingin bertanya mengenai bimbel Edutopia." target="_blank">
                Click Here
            </a>
        </button>

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
