<script>
    export let polaroidImg;
    export let extraClass;
</script>

<div class="bg-white z-[100] w-[35vw] lg:w-[20vw] aspect-[5/4] pt-[0.7vw] {extraClass}" id="pol">
    <img class="w-[34vw] lg:w-[19vw] aspect-[3/2] mx-auto"  src={polaroidImg} alt=""/>
</div>

<style>
    #pol:hover{
        box-shadow: rgba(0, 0, 0, 0.16) 0px 3px 6px, rgba(0, 0, 0, 0.23) 0px 3px 6px;
        z-index: 1000;
    }        
</style>