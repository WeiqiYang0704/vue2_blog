<template>
    <i class="iconfont " :class="getIconName"></i>
</template>

<script>
const icon = {
    home: 'icon-icon-home',
    user: 'icon-icon-user',
    shop: 'icon-icon-store',
    empty:'icon-wushuju',
    qq:'icon-QQ',
    weixin:'icon-weixin',
    email:'icon-youxiang',
    github:'icon-github',
    list:'icon-icon-list',
    more:'icon-icon-more'
}
export default {
    props: {
        type: {
            required: true,
            type: String
        }
    },
    computed:{
        getIconName(){
            return  icon[this.type]
        }
    }

}
</script>

<style scoped>
@import "//at.alicdn.com/t/c/font_1602764_8n2ydhty5zu.css"
</style>