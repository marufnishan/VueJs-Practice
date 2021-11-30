<template>
    
    <div class="card">
        <slot name="h1"></slot>
        <slot name="content"></slot>
        <slot name="btn"><button>Click Now</button></slot>
    </div>
    <br><br>
    <div>
        <slot name="link"></slot>
    </div>
    <div>
        <slot name="image"></slot>
    </div>
    
</template>
<script>
export default{
    name:"Childs",
}
</script>
<style scoped>
.card{
    border: 1px solid black;
    width: 297px;
    padding: 20px;
    background: aquamarine;
    margin: 0 auto;
}
</style>
