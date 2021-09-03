<template>
    <div class="catSelectionBar" >
        <div class="desc">
            <div class="thumb">
              <img :src="setCategoryImage(content.category)" alt="category image">
            </div>
            <div class="category-label">
                <span class="title">Category Name</span>
                <span class="items-counter">5 Items</span>
            </div>
        </div>
        <img src="../assets/icons/ic_chevron_down.svg" class="dropdown" alt="dropdown">
        
    </div>
    
</template>

<script>
export default {
    
}
</script>

<style scoped>
span{
  font-size: 16px;
  font-weight: 600;
  line-height: 19px;
}
.catSelectionBar{
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px;
}
.desc{
    display: flex;
    align-items: center;
}
.thumb{
  display: flex;
  justify-content: center;
  align-items: center;
  background: #f0f0f0; 
  width: 40px;
  height: 40px;
  border-radius: 12px;
}
.thumb img{
  width: 24px;
}
.category-label{
  padding-left: 16px;
  display: flex;
  flex-direction: column;
}
span:nth-child(2){
  color: #8d8d8d;
}


</style>