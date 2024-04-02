<script>
    import { onMount } from "svelte";
    import "../app.css"; //import tailwind
    import icon from '$lib/assets/edutopia/edutopia_no_bg.webp';
    import facebook from '$lib/assets/icons/email.svg';
    import instagram from '$lib/assets/icons/instagram.svg';
    import whatsapp from '$lib/assets/icons/whatsapp.svg';

    export let active;

</script>

<nav class="sticky top-0 shadow-md flex justify-center gap-0 bg-MainBlue h-20 px-10 text-white md:gap-32 z-50">
    <a href="/">
        <img src={icon} alt="" class="w-14 h-14 absolute left-10 top-1/2 -translate-y-1/2 transition-all duration-200 hover:scale-110">
    </a>
    <div class="flex">
        <a href="/">
            <button class="{active === 'Home' ? 'active' : ''} w-32 h-20 lg:w-48 hover:bg-white hover:text-MainBlue hover:text-lg transition-all duration-300" >
                Home
            </button>
        </a>
        <a href="/about">
            <button class="{active === 'About' ? 'active' : ''} w-32 h-20 lg:w-48 hover:bg-white hover:text-MainBlue hover:text-lg transition-all duration-300" >
                About
            </button>
        </a>
        <a href="/contact">
            <button class="{active === 'Contact' ? 'active' : ''} w-32 h-20 lg:w-48 hover:bg-white hover:text-MainBlue hover:text-lg transition-all duration-300" >
                Contact
            </button>
        </a>
    </div>
</nav>
<slot></slot>
<footer class="bg-[#344A53] h-[300px] px-16 py-24 w-full absolute text-white flex justify-around gap-4 lg:gap-32">
    <svg
    xmlns="http://www.w3.org/2000/svg"
    xmlns:xlink="http://www.w3.org/1999/xlink"
    viewBox="0 24 150 28"
    preserveAspectRatio="none"
    >
    <defs>
      <path
        id="gentle-wave"
        d="M-160 44c30 0 
      58-18 88-18s
      58 18 88 18 
      58-18 88-18 
      58 18 88 18
      v44h-352z"
      />
    </defs>
    <g class="waves">
      <use
        xlink:href="#gentle-wave"
        x="50"
        y="0"
        fill="#344A53"
        fill-opacity=".2"
      />
      <use
        xlink:href="#gentle-wave"
        x="50"
        y="3"
        fill="#344A53"
        fill-opacity=".5"
      />
      <use
        xlink:href="#gentle-wave"
        x="50"
        y="6"
        fill="#344A53"
        fill-opacity="1"
      />
    </g>
    </svg>
    
    <div class="lg:w-[30vw]">
        <h3>Edutopia</h3>
        <p class="text-sm opacity-65 mt-6">Edutopia is the largest and most respected learning centre in south east asia. We have more than 6000 teachers all across the globe.</p>
    </div>
    <div class="lg:w-[30vw]">
        <h3>Location</h3>
        <p class="text-sm opacity-65 mt-6">
            Jl. Sutera Flamboyan I No.33 Pd. Jagung, Kec. Serpong Utara, Kota Tangerang Selatan, Banten 15326
        </p>
    </div>
    <div class="lg:w-[30vw]">
        <h3>Socials</h3>
        <div class="flex gap-3 lg:gap-10 mt-6 items-center">
            <a href="https://www.instagram.com/bimbeledutopia/?hl=en" target="_blank">
                <img src={instagram} alt="" class="max-w-10 w-10">
            </a>
            <a href="mailto:example@example.com?subject=Subject%20Here&body=Body%20Here" target="_parent">
                <img src={facebook} alt="" class="max-w-10 w-10 my-auto">
            </a>
            <a href="https://wa.me/6287808230745?text=Halo, saya ingin bertanya mengenai bimbel Edutopia." target="_blank">
                <img src={whatsapp} alt="" class="max-w-10 w-10"> 
            </a>
        </div>
    </div>
</footer>


<style>
    *{
        font-family: "Poppins", sans-serif;
        font-weight: 500;
        font-style: normal;   
    }    
    .active::after{
        display: block;
    }
    button {
        position: relative;
    }

    button::after {
        display: none;
        content: "";
        position: absolute;
        bottom: 20px; /* Adjust this value to position the dot */
        left: 50%;
        transform: translateX(-50%);
        width: 5px; /* Adjust the size of the dot */
        height: 5px; /* Adjust the size of the dot */
        border-radius: 50%;
        background-color: #ffffff; /* Default color of the dot */
        transition: background-color 0.3s; /* Smooth transition for color change */
    }

    button:hover::after {
        display: block;
        background-color: #91d8f4; /* Color of the dot on hover */
        animation: floatUpDown 500ms infinite alternate ease-out; /* Animation for floating effect */
    }

    @keyframes floatUpDown {
        0% {
            bottom: 10px;
        }
       
        100% {
            bottom: 20px;
        }
    }
    .waves > use {
        animation: move-forever 9s -2s linear infinite;
    }

    .waves > use:nth-child(2) {
        animation-delay: -3s;
        animation-duration: 10s;
    }
    .waves > use:nth-child(3) {
        animation-delay: -4s;
        animation-duration: 8s;
    }

    @keyframes move-forever {
    0% {
        transform: translate(-90px, 0%);
    }
    100% {
        transform: translate(85px, 0%);
    }
    }

    svg {
        position: absolute;
        left: 0;
        top: 0;
        transform: translateY(-100%);
        width: 100%;
        height: 30vw;
        max-height: 200px;
    }
</style>
