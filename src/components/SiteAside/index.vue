<template>
    <div class="site-container">
        <!-- 头像 -->
        <AvatarName url="https://img.zcool.cn/community/01116c5afe7689a801209a858a5349.jpg@2o.jpg"></AvatarName>
        <!-- menu -->
        <Menu></Menu>
        <!-- footer -->
        <Contact></Contact>
    </div>
</template>

<script>
import AvatarName from '../AvatarName.vue';
import Menu from '@/components/Menu/index.vue'
import Contact from '@/components/Contact/index.vue'
    export default {
        components:{
            AvatarName,
            Menu,
            Contact
        }
    }
</script>

<style lang="less" scoped>
    .site-container{
        width: 250px;
        height: 600px;
        background: #202020;
        padding: 20px 0px;
        box-sizing: border-box;
        color: rgb(178, 174, 174);
        position: relative
    }

</style>