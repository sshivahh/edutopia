<script>
    import button_wave from "$lib/assets/curves/button_wave.svg";

    export let subject = "halo";
    let card;

    function handleMouseMove(event) {
        const cardRect = card.getBoundingClientRect();
        const mouseX = event.clientX;
        const mouseY = event.clientY;
        const cardCenterX = cardRect.left + cardRect.width / 2;
        const cardCenterY = cardRect.top + cardRect.height / 2;
        
        // Calculate the offset
        const offsetX = (mouseX - cardCenterX) * 0.2;
        const offsetY = (mouseY - cardCenterY) * 0.2;

        card.style.transform = `translate(${offsetX}px, ${offsetY}px) scale(1.1)`;
    }

    function handleMouseLeave() {
        card.style.transform = `translate(0, 0) scale(1)`;
    }
</script>

<!-- svelte-ignore a11y-no-static-element-interactions -->
<div
    bind:this={card}
    class="card bg-white border-[6px] transition-all relative duration-300 border-MainBlue rounded-full w-fit h-fit py-2 px-4 hover:bg-MainBlue"
    on:mousemove={handleMouseMove}
    on:mouseleave={handleMouseLeave}
>
    <p class="text-MainBlue">{subject}</p>
    <div class="wave"></div>
</div>

<style>
    .card:hover > p {
        transition: 300ms;
        color: white;
    }
    .card {
        transition: transform 0.2s ease-out, box-shadow 0.2s ease-out;
    }
    .card:hover {
        box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
    }
</style>
