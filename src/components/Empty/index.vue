<template>
    <div class="empty-container">
        <Icon type="empty"  ></Icon>
        <div>{{ text }} </div>
    </div>
</template>

<script>
import Icon from '../MyIcon/index.vue'
export default {
    components:{
        Icon
    },
    props: {
        text: {
            type: String,
            defalut: '暂无数据'
        }
    }
}
</script>

<style lang="less" scoped>
 @import url(../../styles/global.less);
.empty-container{
    .self-center();
    color: #b4b8bc;
    text-align: center;
}
    .iconfont{
        font-size: 30px;
    }
</style>