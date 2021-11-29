<template>
    <div>
        <h3>Nishan</h3>
        <h3 v-bind="$attrs">Maruf</h3>
        <h3>{{$attrs}}</h3>
    </div>
</template>
<script>
export default{
    name:"NonPrPS",
    inheritAttrs:false
}
</script>
<style scoped>

</style>
