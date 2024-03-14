<script>
    export let polaroidImg;
    export let extraClass;
</script>

<div class="bg-white w-[350px] aspect-[5/4] pt-[10px] {extraClass}">
    <img class="w-[330px] aspect-[3/2] mx-auto"  src={polaroidImg} alt=""/>
</div>