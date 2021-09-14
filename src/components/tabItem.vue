<template>
  <div class="tabitem" 
  :class="[showDarkHover ? 'hovered_light' : '',
  itemClicked ? 'clicked' : '',]" 
  @click="selectTab(itemClicked)"
  @mouseover="hover"
  @mouseleave="unhover"
  >
      {{title}}
  </div>
</template>

<script>
export default {
    data(){
        return {
            itemClicked: false,
            showDarkHover: false
        }
    },
    props:{
        title: String
    },
    methods:{
        selectTab(state){
            !state ? this.itemClicked = true 
            : this.itemClicked = false
        },
        hover(){
            this.showDarkHover = true
        },
        unhover(){
            this.showDarkHover = false
        }
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
    .hovered_light{
        background: #f2f2f2;
    }
    .hovered_dark{
        background:rgb(14, 14, 14);
    }
    .clicked{
        background:black;
        color: white;
        border-right: 0;
    }

</style>