<template>
    <div class="primaryBar">
        <span class="label">Cancel</span>
        <div class="btn">
            <img src="../assets/icons/ic_add.svg" alt="btn new item">
        </div>
    </div>

</template>

<script>

</script>

<style scoped>
.primaryBar{
    display: flex;
    justify-content: flex-end;
    align-items: center;
    padding: 16px;
    border-top:.5px solid #dedede;
    background: white;
}
.primaryBar > *{
    margin-left: 16px;
}
.btn{
    background: limegreen;
    padding: 8px 16px;
    border-radius: 32px;
}
.btn > img {
    display: block;
}
span{
    display: inline-block;
    font-weight: 600;
    color: #8d8d8d;
}

</style>