<template>
    <button class="button"><slot></slot></button>
</template>

<script>
export default{
    name: 'MyButton'

}

</script>

<style scoped>
.button {
    outline: none;
    border:2px solid #87cefa;
    border-radius: 10px;
    background-color:black;
    margin: 10px 10px;
    width: 40px;
    height: 40px;
   
}
</style>