<template>
  <div class="entry">
    <div class="bounds" >
        <div class="desc">
            <catThumb :categoryTitle="content.category" />
            <div class="content">
                <span class="title">{{content.title}}</span>
                <span class="category">{{content.category}}</span>
            </div>
        </div>
        <div class="details" v-if="!dropDownItem">
            <span>{{content.amount}}</span>
            <img src="../assets/icons/ic_chevron_right.svg" alt="link to details">
        </div>
    </div>
    <hr>
  </div>
    
    
</template>
    
<script>
    import catThumb from './catThumb.vue'

    export default {
    name: 'entry',
    data() {
      return {
        imagePath: null
      }
    },
    props: {
        content: Object, 
        dropDownItem: {
          type: Boolean,
          default: false
        }
    },
    components: {
        catThumb
    },
    methods: {
      setCategoryImage(catName){
        return require(`../assets/thumbs/img_${catName.toLowerCase()}.png`)
      }
    }
  }
</script>

<style scoped>
span{
  font-size: 16px;
  font-weight: 600;
  line-height: 19px;
}
.bounds{
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 8px 16px 16px;
}
.desc{
    display: flex;
}
.content{
  padding-left: 16px;
  display: flex;
  flex-direction: column;
}
span:nth-child(2){
  color: #8d8d8d;
}
.details{
  display: flex;
  align-items: center;
  justify-content: flex-end;
}
hr{
  border: 0;
  height: .5px;
  background-color: #dedede;
  margin-left: 16px;
}

</style>
