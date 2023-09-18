<template>
    <div class="wrapper">
        <ButtonsContainer></ButtonsContainer>
        <Content></Content>
    </div>
</template>

<script>
import ButtonsContainer from './ButtonsContainer.vue';
import Content from './Content.vue';

export default {
    components: { ButtonsContainer, Content }
}
</script>

<style scoped>
.wrapper {
    width: 50%;
    margin: 0 auto;
    margin-top: 100px;
}



</style>