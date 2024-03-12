<script>
    import { onMount } from "svelte";
    import "../app.css"; //import tailwind
    import icon from '$lib/assets/edutopia_no_bg.webp';

    let isMobile = false;

    onMount(() => {
        if (window.innerWidth < 688) {
            isMobile = true;
        }
    });

    export let active;

</script>

{#if !isMobile}
<nav class="relative flex justify-end gap-0 bg-MainBlue h-20 px-10 text-white md:gap-32">
    <a href="/">
        <img src={icon} alt="" class="w-14 h-14 absolute left-10 top-1/2 -translate-y-1/2 transition-all duration-200 hover:scale-110">
    </a>
    <div class="flex">
        <a href="/">
            <button class="{active === 'Home' ? 'active' : ''} h-20 w-48 hover:bg-white hover:text-MainBlue hover:text-lg transition-all duration-300" >
                Home
            </button>
        </a>
        <a href="/about">
            <button class="{active === 'About' ? 'active' : ''} h-20 w-48 hover:bg-white hover:text-MainBlue hover:text-lg transition-all duration-300" >
                About
            </button>
        </a>
        <a href="/contact">
            <button class="{active === 'Contact' ? 'active' : ''} h-20 w-48 hover:bg-white hover:text-MainBlue hover:text-lg transition-all duration-300" >
                Contact
            </button>
        </a>
    </div>
</nav>
<slot></slot>
<footer class="">
    ini footer
</footer>
{:else}
<h1 class="bg-green-600">ini mobile</h1>
{/if}

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
</style>
