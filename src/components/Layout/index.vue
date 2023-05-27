<template>
    <div class="layout-container">
        <div class="left">
            <slot name="left"></slot>
        </div>
        <div class="main">
            <slot></slot>
        </div>
        <div class="right">
            <slot name="right"></slot>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style lang="less" scoped>
    .layout-container{
        display: flex;
        .left{
           flex: 0 0 250px;
        }
        .main{
            flex: 1;
        }
        .right{
            width: 200px;
        }
    }
</style>