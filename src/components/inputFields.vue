<template>
<div class="input-fields">
    <form>
        <div class="input-wrapper">
            <input v-model="title" type="text" placeholder="Title" name="title" id="title">
            <hr>
        </div>
        <Dropdown :newVal="priority" v-on:priority-selected="updatePriority($event)"   />
        <div class="input-wrapper">
            <input v-model="due_date" type="date" placeholder="12.02.2020" name="title" id="title">
        </div>
    </form>
    <PrimaryBar :addTodo="addTodo" :resetInputs="reset" :toggleError="toggleError"/>
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
            priority: "",
            priority_path: "",
            due_date: "",
            toggleError: false
        }
    },
    props: {
        
    },
    methods:{
       addTodo(){
            const newTodo = {
                title: this.title,
                due_date: this.due_date,
                priority: this.priority_path,
                done: false
            }
            if(!this.inputMissing(newTodo)){
                this.reset()
                this.$emit('new-todo',newTodo)
                this.toggleError = false
            }else{
                this.toggleError = true
            }
        },
        reset(){
            this.title = ""
            this.due_date = ""
            this.priority = ""
        },
        updatePriority(label){
            this.priority = label.title
            this.priority_path = label.path
        },
        inputMissing(obj){
            for(var prop in obj) {
                if(obj[prop] === ''){
                    return true
                }
            }
            return false
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
