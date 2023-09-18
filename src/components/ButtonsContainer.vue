<template>
    <div class="buttons-container">
        <MyButton @click="undo" id="left-arrow"> <MyImg src="../img/arrow_left.png"></MyImg> </MyButton>
        <MyButton @click="redo" id="right-arrow"> <MyImg src="../img/arrow_right.png"></MyImg> </MyButton>
        <MyButton @click="makeTitle" id="title"> <MyImg src="../img/T.png"></MyImg> </MyButton>
        <MyButton @click="makeParagraph" id="paragraph"> <MyImg src="../img/TT.png"></MyImg> </MyButton>
        <MyButton @click="createImage"> <MyImg src="../img/img.png"></MyImg> </MyButton>
        <button @click="copyHTML" class="button-html">Скопировать HTML</button>
    </div>
</template>

<script>
export default {
    methods: {
        makeTitle() {
            document.execCommand('fontSize', false, '6')
        },
        makeParagraph() {
            document.execCommand('fontSize', false, '3')
            document.execCommand('justifyLeft')
        },
        createImage() {
            document.execCommand('insertImage', false, prompt())
            for(let child of Object.values(document.querySelector('.article').children)) {
                child.style.width = '30%'
                child.style.height = '25%'
                child.style.borderRadius = '15px'
                child.style.border = '1px solid #87cefa'
            }
        },
        undo() {
            document.execCommand('undo')
            
        },
        redo() {
            document.execCommand('redo')
        },
        copyHTML() {
            document.execCommand('copy')
        }
    }

}
</script>

<style scoped>
.buttons-container {
    display: flex;
    flex-direction: row;
}

.button-html {
    color: #87cefa;
    outline: none;
    border: 2px solid #87cefa;
    border-radius: 10px;
    background-color: black;
    margin: 10px 10px;
    width: 100px;
    height: 40px;
}
</style>