<template>
    <div class="imgage-loader-container">
     
        <img   v-if="isAll" :src="placeHoader" class="place" />
        <img  @load="onLoadImg" :src="src" :style="{opacity:isOnLoadImg?1:0,transition:`${duration}ms`}" />
    </div>
</template>

<script>
    export default {
        props:{
            src:{
                required:true,
                type:String
            },
            placeHoader:{
                required:true,
                type:String
            },
            duration:{
                required:true,
                type:Number
            },
        },
        data:()=>{
            return (
                {
                    isOnLoadImg:false,
                    isAll:false
                }
            )
        },
        methods:{
            onLoadImg(){
                this.isOnLoadImg=true
                setTimeout(()=>{
                    this.isAll=true
                },this.duration)
                
            }
        }
    }
</script>

<style lang="less" scoped>

@import url(../../styles/global.less);
 .imgage-loader-container{
    width: 100%;
    height: 100%;
    position: relative;
    overflow: hidden;
 }
    img{
        .self-fill();
        object-fit: cover;
    }
    .place{
        filter: blur(1vw);
    }
</style>