<template lang="">
    <div>
        <h1>
            <slot name="slotTitle">
                404 Title <!--Defualt card content-->
            </slot>
        </h1>
        <h1>
            <slot>
                404 default<!--Defualt card content-->
            </slot>
        </h1>
    </div>
</template>
<script>
export default {
    
}
</script>
<style scoped>
div {
    border: 3px black solid;
    border-radius: 10%;
    width: 300px;
    margin: auto
}
    
</style>