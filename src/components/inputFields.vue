<template>
<div class="input-fields">
    <form>
        <div class="input-wrapper">
            <input v-model="title" type="text" placeholder="Title" name="title" id="title">
            <hr>
        </div>
        <div class="input-wrapper">
            <input v-model="priority" type="text" placeholder="Priority" name="title" id="title" readonly>
            <hr>
            <Dropdown/>
        </div>
        <div class="input-wrapper">
            <input v-model="due_date" type="date" placeholder="12.02.2020" name="title" id="title">
        </div>
    </form>
    <PrimaryBar :addTodo="addTodo" :resetInputs="reset"/>
</div>
    
</template>

<script>
import PrimaryBar from './primaryBar.vue'
import Dropdown from './dropdown.vue'

export default {
    name:'input-fields',
    data() {
        return {
            title: "",
            priority: "High",
            due_date: ""
        }
    },
    methods:{
       addTodo(){
            const newTodo = {
                title: this.title,
                due_date: this.due_date,
                priority: this.priority,
                done: false
            }
            this.reset()
            this.$emit('new-todo',newTodo)
            console.log(newTodo)
        },
        reset(){
            this.title = ""
            this.due_date = ""
            this.priority = ""
        }
    },
    components: {
        PrimaryBar,
        Dropdown
    }
}
</script>

<style scoped>
    input{
        font-family: 'Open Sans', Helvetica, sans-serif;
        font-size: 16px;
        font-weight: 600;
        line-height: 19px;
        padding: 16px 18px;
        border: 0;
        width: 100%;
    }
    .input-wrapper:nth-child(2){
        position: relative;
    }
    input:focus{
        outline: 0;
    }
    hr{
        border: 0;
        height: 1px;
        background-color: #efefef;
        margin-left: 16px;
    }

</style>
