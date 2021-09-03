<template>
    <div class="thumb" :class="[hasLightColor ? 'light' : 'dark']">
        <img :src="setCategoryImage(categoryTitle)" alt="category thumbnail">
    </div>
</template>

<script>

export default {
    name: 'catThumb',
    // data() {
    //     return {
        
    //     }
    // },
    props: {
        categoryTitle: String,
        hasLightColor: {
            type: Boolean,
            default: true
        } 
    },
    methods: {
      setCategoryImage(catName){
        return require(`../assets/thumbs/img_${catName.toLowerCase()}.png`)
      }
    }
}
</script>

<style scoped>
.thumb{
  display: flex;
  justify-content: center;
  align-items: center;
  width: 40px;
  height: 40px;
  border-radius: 12px;
}
.light{
    background-color: #f0f0f0;
}
.dark{
    background-color:#444
}
.thumb img{
  width: 24px;
}

</style>