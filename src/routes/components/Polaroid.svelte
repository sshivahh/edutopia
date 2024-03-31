<script>
    export let polaroidImg;
    export let extraClass;
</script>

<div class="bg-white w-[20vw] aspect-[5/4] pt-[10px] {extraClass}" id="pol">
    <img class="w-[19vw] aspect-[3/2] mx-auto"  src={polaroidImg} alt=""/>
</div>

<style>
    #pol:hover{
        box-shadow: rgba(0, 0, 0, 0.16) 0px 3px 6px, rgba(0, 0, 0, 0.23) 0px 3px 6px;
    }        
</style>