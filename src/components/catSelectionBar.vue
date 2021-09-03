<template>
    <div class="catSelectionBar" >
        <div class="desc">
            <catThumb categoryTitle="overview" :hasLightColor="false"/>
            <div class="category-label">
                <span class="title">Category Name</span>
                <span class="items-counter">5 Items</span>
            </div>
        </div>
        <div class="wrapper-chevron" @click="toggleDropdown()" ref="chevron">
            <img src="../assets/icons/ic_chevron_down.svg" class="dropdown" alt="dropdown">
        </div>
        
    </div>
    
</template>

<script>
    import catThumb from './catThumb.vue'

    export default {
        name: 'catSelectionBar',
        data() {
            return {
                toggled: false
            }
        },
        components: {
            catThumb
        },
        methods: {
            toggleDropdown(){
                const dropDown = document.querySelector('.dropdown')
                if(!this.toggled){
                    dropDown.style.transform = 'rotate(-180deg)'
                    this.toggled = true
                }else{
                    dropDown.style.transform = 'rotate(0deg)'
                    this.toggled = false
                }
            }
        }
    
        
    }
</script>

<style scoped>
span{
  font-size: 16px;
  font-weight: 600;
  line-height: 19px;
  color:white;
}
.catSelectionBar{
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px;
  border-bottom: .5px solid rgba(255,255,255,.16);
}
.desc{
    display: flex;
    align-items: center;
}
.category-label{
  padding-left: 16px;
  display: flex;
  flex-direction: column;
}
span:nth-child(2){
  color: #8d8d8d;
}
.wrapper-chevron{
    width: 24px;
    height: 24px;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
}
.wrapper-chevron img{
    display: block;
    transform: rotate(0deg);
    transform-origin: center;
    transition: transform .5s;
}


</style>