<template>
    <div class="primary-bar">
        <span class="secondary" @click="resetInputs">Reset</span>
        <div class="btn" @click="addTodo">
            <img src="../assets/icons/ic_add.svg" alt="btn new item">
        </div>
        <error-message 
        title="Oops something missing"
        subline="Please enter all the information required"
        :toggle="toggleError"
        />
    </div>

</template>

<script>
import ErrorMessage from './errorMessage.vue'

export default {
    name: 'primary-bar',
    props: {
        addTodo: Function,
        resetInputs : Function,
        toggleError: Boolean
    },
    components:{
        ErrorMessage
    }
}
</script>

<style scoped>
.primary-bar{
    position: relative;
    display: flex;
    justify-content: flex-end;
    align-items: center;
    padding: 16px;
    border-top:.5px solid #efefef;
    background: white;
}
.primary-bar > span + div{
    margin-left: 16px;
}
.btn{
    background: limegreen;
    padding: 8px 16px;
    border-radius: 32px;
}
.btn > img {
    display: block;
}
.secondary{
    cursor: pointer;
}
span{
    display: inline-block;
    font-weight: 600;
    color: #8d8d8d;
}


</style>