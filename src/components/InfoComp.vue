<template lang="">
    <!-- <div>
        {{ firstName }} {{lastName}} {{objectData}}
    </div> -->
    <h1>This is The component </h1>
    <slot></slot>
</template>
<script>
export default {
    // props: ['firsName','lastName','objectData']
    props:{
        firstName: String,
        objectData: Object
 }
}
</script>
<style lang="">
    
</style>