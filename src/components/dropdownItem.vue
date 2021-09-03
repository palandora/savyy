<template>
    <div class="dropdownItem">
        <div class="label">
            <catThumb :categoryTitle="category" :hasLightColor="false"/>
            <div class="content">
                <span class="title">{{category}}</span>
                <span class="items">12 Items</span>
            </div>
        </div>
    </div>
</template>

<script >
    import catThumb from './catThumb.vue'

    export default {
        name: 'entry',
        data() {
            return {
                
            }
        },
        props: {
            category: String, 
        },
        components: {
            catThumb
        },
        methods: {
        }
    }
</script>

<style scoped>
    span{
        color: white;
        font-size: 16px;
        font-weight: 600;
        line-height: 19px;
    }
    span:nth-child(2){
        color: #8d8d8d;
    }
    .dropdownItem{
        display: flex;
        align-items: center;
        padding: 16px;
        border-bottom: 0.5px solid #444;
        cursor: pointer;
    }
    .dropdownItem:hover{
        background: rgba(255,255,255,.04);
    }
    .label{
        display: flex;
    }
    .content{
        padding-left: 16px;
        display: flex;   
        flex-direction: column; 
    }
</style>