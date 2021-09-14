<template>
  <div class="tabbar">
      <tab-item title="Low"/>
      <tab-item title="Medium"/>
      <tab-item title="High"/>
  </div>
</template>

<script>
    import TabItem from './tabItem.vue'
    export default {
        data(){
            return {

            }
        },
        components: {
            TabItem
        }

    }
</script>

<style scoped>
    .tabbar{
        background: white;
        border-top: 1px solid #dedede;
        display: flex;
    }

</style>