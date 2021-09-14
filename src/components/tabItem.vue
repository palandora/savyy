<template>
  <div class="tabitem">
      {{title}}
  </div>
</template>

<script>
export default {
    data(){
        return {
            
        }
    },
    props:{
        title: String
    },
    methods:{
    }
}
</script>

<style scoped>
    .tabitem{
        display: flex;
        justify-content: center;
        align-items: center;
        flex-grow: 1;
        padding: 16px;
        font-size: 16px;
        font-weight: 600;
        line-height: 19px;
        border-right: 1px solid #dedede;
        cursor: pointer;
    }

</style>