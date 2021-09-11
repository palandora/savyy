<template>
    <div class="error-message" :class="[toggle ? 'toggle' : '']">
        <div class="desc">
            <div class="thumb">
                <img src="../assets/priorities/prio_very_high.png" alt="header image">
            </div>
            <div class="content">
                <span class="title">{{title}}</span>
                <span class="subline">{{subline}}</span>
            </div>
        </div>
    </div>
</template>

<script>

    export default {
    name: 'appHeader',
    data(){
        return {
            
        }
    },
    props:{
        title: String,
        subline: String,
        toggle: Boolean
    }
  }
</script>

<style scoped>
    span{
        font-size: 16px;
        font-weight: 600;
        line-height: 19px;
        color: white;
    }
    span:nth-child(2){
        color: rgba(255,255,255,.56);
    }
    .error-message{
        pointer-events: none;
        position: absolute;
        left: 0;
        right: 0;
        bottom: -74px;
        height: 73px;
        display: flex;
        opacity: 0;
        justify-content: flex-start;
        align-items: center;
        padding: 16px;
        background: rgb(247, 41, 41);
    }
    .error-message.toggle{
        animation: fadeInOut 4.5s ease-in-out;
    }
    .desc{
        display: flex;
        align-items: center;
    }
    .content{
        padding-left: 16px;
        display: flex;
        flex-direction: column;
    }

    .thumb{
        display: flex;
        justify-content: center;
        align-items: center;
        width: 40px;
        height: 40px;
        border-radius: 12px;
        background-color: rgba(255,255,255,.24);
    }
    .thumb img{
        width: 24px;
    }

    @keyframes fadeInOut{
        0%,100% {
            bottom: -74px;
            opacity: 0;
        }
        16%,64% {
            bottom: -1px;
            opacity: 100%;
        }
    }


</style>