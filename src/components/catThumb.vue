<template>
    <div class="thumb">
        <img :src="setThumbImage(thumbTitle)" alt="category thumbnail">
    </div>
</template>

<script>

export default {
    name: 'catThumb',
    props: {
        thumbTitle: String
    },
    methods: {
      setThumbImage(name){
        try{
          return require(`../assets/priorities/${name.toLowerCase()}.png`)
        }
        catch(e){
          return require(`../assets/thumbs/img_other.png`)
        }
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
  background-color: #f0f0f0;
}

.thumb img{
  width: 24px;
}

</style>