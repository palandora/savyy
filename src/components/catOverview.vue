<template>
    <div class="catOverview">
        <div class="title">
            <span>Total</span>
            <h1>2.000,50</h1>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'catOverview',
            data() {
                return {
                    
                }
        },
    }
</script>

<style scoped>
    .catOverview{
        margin-top: 73px;
        display: flex;
        justify-content: center;
        align-items: center;
        flex: 1 0 auto;
    }
    h1{
        color: white;
        font-size: 64px;
        line-height: 74px;
        text-align: center;
    }
    span{
        display: block;
        text-align: center;
        font-weight: 600;
        line-height: 19px;
        color: #8d8d8d;
    }
    
</style>