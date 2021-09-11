<template>
    <div class="header" >
        <div class="desc">
            <div class="thumb">
                <img src="../assets/thumbs/img_other.png" alt="header image">
            </div>
            <div class="content">
                <span class="title">{{title}}</span>
                <span class="subline">{{subline}}</span>
            </div>
        </div>
    </div>
</template>

<script>
    import catThumb from './catThumb.vue'

    export default {
    name: 'appHeader',
    components: {
        catThumb
    },
    props:{
        title: String,
        subline: String
    }
  }
</script>

<style scoped>
    span{
    font-size: 16px;
    font-weight: 600;
    line-height: 19px;
    }
    .header{
    display: flex;
    justify-content: flex-start;
    align-items: center;
    padding: 16px;
    border-bottom: .5px solid #efefef;
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
    span:nth-child(2){
    color: #8d8d8d;
    }

    .thumb{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 40px;
    height: 40px;
    border-radius: 12px;
    background-color: #f0f0f0;
    }

    .thumb img{
    width: 24px;
    }

</style>