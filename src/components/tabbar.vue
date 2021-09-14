<template>
  <div class="tabbar">
        <tab-item :title="priority.title"
        v-for="(priority,index) in priorities"
        :key="index" 
        @click="selectTabItem(index)"
        :class="setActiveTab(index)" 
        @mouseover="hover(index)"
        @mouseleave="unhover(index)"
        />
  </div>
</template>

<script>
    import TabItem from './tabItem.vue'
    export default {
        data(){
            return {
                hoveredIndex: null,
                selectedIndex: null,
                hovered: false,
            }
        },
        components: {
            TabItem
        },
        methods: {
            selectTabItem(index){
                this.selectedIndex = index
                this.$emit('tab-selected',index)
            },
            hover(index){
                this.hoveredIndex = index
                this.hovered = true
            },
            unhover(index){
                this.hoveredIndex = index
                this.hovered = false
            },
            setActiveTab(index){
                let newClass = ""
                if(this.selectedIndex === index){
                    newClass = "clicked"
                }else if(this.hoveredIndex === index){
                    newClass = "hovered_light"
                }
                return newClass
            }
        },
        inject : ['priorities']

    }
</script>

<style scoped>
    .tabbar{
        background: white;
        border-top: 1px solid #dedede;
        display: flex;
    }
    .clicked{
        background:black;
        color: white;
        border-right: 0;
    }
    .hovered_dark{
        background: #2b2b2b;
    }
    .hovered_light{
        background: #e6e6e6;
    }

</style>