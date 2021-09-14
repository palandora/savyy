<template>
    <div class="input-wrapper">
        <input v-model="priority" type="text" placeholder="Priority" name="title" id="title" readonly>
        <div class="toggle" :class="[toggled ? 'toggled' : '']" @click="toggleDropdown">
            <img src="../assets/icons/ic_chevron_down.svg" alt="dropdown toggle" >
        </div>
        <hr>
        <div class="dropdown" v-if="toggled">
            <div class="item" 
                v-for="(priority,index) in priorities"
                :key="index" 
                @click="selectItem(priority)"
                >
                {{priority.title}}
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "dropdown",
    data() {
        return {
            priority: "",
            toggled: false,
            priorities: [
                {title: 'Low', path: 'prio_low'},
                {title: 'Medium', path: 'prio_medium'},
                {title: 'High', path: 'prio_high'},
                {title: 'Very High', path: 'prio_very_high'}
            ]
        }
    },props:{
        newVal: String
    },methods:{
        toggleDropdown(){
            this.toggled ? this.toggled = false : this.toggled = true
        },
        selectItem(elementClicked){
            this.priority = elementClicked.title
            this.$emit('priority-selected',elementClicked)
            this.toggled = false
        }
    },
    watch:{
        newVal(val){
            this.priority = val;
        }
    }
}
</script>

<style scoped>
    *{
        font-size: 16px;
        font-weight: 600;
        line-height: 19px;
    }
    /* styles input */
    .input-wrapper{
        position: relative;
    }
    input{
        font-family: 'Open Sans', Helvetica, sans-serif;
        padding: 16px 18px;
        border: 0;
        width: 100%;
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
    .toggle{
        width: 24px;
        height: 100%; 
        position: absolute;
        display: flex;
        justify-content: center;
        align-items: center;
        right: 16px;
        top: 0;
    }
    .toggle.toggled img{
        transform-origin: center;
        transform: rotate(180deg);
    }
    /* styles dropdown */
    .dropdown{
        position: absolute;
        z-index: 4;
        left: 16px;
        right: 16px;
        border-radius: 0 0 8px 8px;
        display: flex;
        flex-direction: column;
        padding: 4px 0;
        background: white;
        box-shadow: 0 4px 16px rgba(0,0,0,.08), 0 0 0 1px rgba(0,0,0,.06)
    }
    .item{
        cursor: pointer;
        padding: 8px 16px ;
    }
    .item:hover{
        background: #f8f8f8;
    }


</style>