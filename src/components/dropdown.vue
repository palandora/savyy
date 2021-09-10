<template>
    <div class="dropdown" v-if="hidden">
        <div class="item" 
        v-for="(priority,index) in priorities"
        :key="index" 
        >
        {{priority.title}}
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            hidden: false,
            priorities: [
                {title: 'Low', img: 'prio_low'},
                {title: 'Medium', img: 'prio_medium'},
                {title: 'High', img: 'prio_high'}
            ]
        }
    }
}
</script>

<style scoped>
    *{
        font-weight: 600;
    }
    .dropdown{
        position: absolute;
        left: 16px;
        right: 16px;
        border-radius: 0 0 8px 8px;
        display: flex;
        flex-direction: column;
        padding: 4px 0;
        background: white;
        box-shadow: 0 4px 16px rgba(0,0,0,.08), 0 0 0 1px rgba(0,0,0,.06)
    }
    .item{
        padding: 8px 16px ;
    }

</style>