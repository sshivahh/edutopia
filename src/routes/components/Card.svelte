<script>
    import button_wave from "$lib/assets/curves/button_wave.svg"

    export let subject="halo";
</script>

<div class="bg-white border-[6px] transition-all relative duration-300 border-MainBlue rounded-full w-fit h-fit py-2 px-4 hover:bg-MainBlue">
    <p class="text-MainBlue">{subject}</p>
    <div class="wave"></div>
</div>

<style>

    div:hover > p {
        transition: 300ms;
        color: white;
    }


</style>
<!-- <div class="bg-MainBlue border-[6px] transition-all relative duration-300 border-MainBlue rounded-full w-fit h-fit py-2 px-4 hover:bg-white">
    <p class="text-white">{subject}</p>
    <div class="wave"></div>
</div>

<style>

    div:hover > p {
        transition: 300ms;
        color: #91d8f4;
    }


</style> -->
