<script>
    import Layout from "../__layout.svelte";
  
    import whiteLayer1 from "$lib/assets/curves/white_layer1.svg";
    import blueLayer1 from "$lib/assets/curves/blue_layer1.svg";
    import blueLayer2 from "$lib/assets/curves/blue_layer2.svg";
  
    import teach1 from "$lib/assets/images/teach1.jpeg";
    import teach2 from "$lib/assets/images/teach2.jpeg";
    import teach3 from "$lib/assets/images/teach3.jpeg";
    import teach4 from "$lib/assets/images/teach4.jpeg";
    import teach5 from "$lib/assets/images/teach5.jpeg";
    import teach7 from "$lib/assets/images/teach7.jpeg";
    import teach8 from "$lib/assets/images/teach8.jpeg";
    import teach9 from "$lib/assets/images/teach9.jpeg";
    import teach10 from "$lib/assets/images/teach10.jpeg";
    import teach11 from "$lib/assets/images/teach11.jpeg";
    import teach12 from "$lib/assets/images/teach12.jpeg";
    import teach13 from "$lib/assets/images/teach13.jpeg";
    import teach14 from "$lib/assets/images/teach14.jpeg";
    import teach15 from "$lib/assets/images/teach15.jpeg";
    import teach16 from "$lib/assets/images/teach16.jpeg";
    import teach17 from "$lib/assets/images/teach17.jpeg";
    import teach18 from "$lib/assets/images/teach18.jpeg";
    import teach19 from "$lib/assets/images/teach19.jpeg";
    import teach20 from "$lib/assets/images/teach20.jpeg";
    import teach21 from "$lib/assets/images/teach21.jpeg";
  
    import Card from "../components/Card.svelte";
  
    import { onMount } from "svelte";
  
    let photoWrapper;
    let photoElements = [
      teach1, teach2, teach3, teach4, teach5, teach7, 
      teach8, teach9, teach10, teach11, teach12, teach13, 
      teach14, teach15, teach16, teach17, teach18, teach19, 
      teach20, teach21
    ];
  
    // Shuffle the photoElements array on component mount
    onMount(() => {
      photoElements = shuffleArray(photoElements);
    });
  
    // Function to shuffle array elements
    function shuffleArray(array) {
      return array.sort(() => Math.random() - 0.5);
    }
  
    // Rest of your existing code...
  
    function checkPosition() {
      const photos = Array.from(photoWrapper.children);
      photos.forEach(photo => {
        if (photo.getBoundingClientRect().right - 4 <= 0) {
          photoWrapper.appendChild(photo);
          photoWrapper.scrollLeft -= photo.clientWidth + 32; // width + gap
        }
      });
    }
  
    function infiniteScroll() {
      if (photoWrapper) {
        photoWrapper.scrollLeft++;
        checkPosition();
        requestAnimationFrame(infiniteScroll);
      }
    }
  
    onMount(() => {
      const photos = Array.from(document.getElementsByClassName("photo"));
      photos.forEach((photo, index) => {
        if (index % 2 === 0) {
          photo.classList.add("even");
        }
      });
      infiniteScroll();
    });
  
  </script>
  
  <Layout active="About">
    <section class="h-[700px] bg-white flex flex-col justify-center items-center">
      <div class="w-fit font-semibold text-8xl text-MainBlue text-center my-auto leading-[80px]">
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
    <section class="h-[800px] md:h-[900px] lg:h-[1000px] bg-MainBlue pt-12 md:p-0">
      <div class="w-fit font-bold text-white text-center m-auto leading-[90px] mb-12 md:mb-24">
        <h1 class="text-6xl">Our</h1>
        <h1 class="text-8xl">Gallery</h1>
      </div>
      <div class="photo-wrapper gap-5 md:gap-16" id="photoWrapper" bind:this={photoWrapper}>
        {#each photoElements as photoSrc, index}
          <div class="photo shadow-lg  w-[15rem] h-[15rem] md:w-[20rem] md:h-[20rem] lg:w-96 lg:h-96" class:even={index % 2 === 0}>
            <img src={photoSrc} alt="">
          </div>
        {/each}
      </div>
    </section>
  </Layout>
  
  <style>
    .photo-wrapper {
      display: flex;
      padding: 2rem;
      overflow-x: scroll;
      width: 100%;
      scrollbar-width: none; /* Firefox */
      -ms-overflow-style: none;  /* IE 10+ */
    }
  
    .photo-wrapper::-webkit-scrollbar {
      display: none;  /* Chrome, Safari, and Opera */
    }
  
    .photo {
      border-radius: 32px;
      overflow: hidden;
      position: relative;
      flex-shrink: 0;
      transition: transform 0.25s ease;
    }
  
    .photo img {
      border-radius: 16px;
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  
    .photo::after {
      content: "";
      position: absolute;
      top: -1rem;
      bottom: -1rem;
      left: -16rem;
      background: linear-gradient(90deg, transparent, white, transparent);
      width: 16rem;
      opacity: 0;
      transform: rotate(6deg);
    }
  
    .photo:hover::after {
      left: 100%;
      opacity: 0.2;
      transition: inset 1s;
    }
  
    .photo:hover {
      transform: scale(1.1) !important;
    }
  
    .photo.even {        
      transform: rotate(2deg);
    }
  
    .photo:not(.even) {      
      transform: rotate(-2deg);
    }
  

  </style>
  