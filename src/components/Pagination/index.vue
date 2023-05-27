<template>
    <div class="page-cotainer">
        <!-- 回到首页 -->
        <a  @click="onChange(1)" :class="{disable:current===1}" v-show="current !== 1">| &lt;&lt; </a>

        <a  @click="onChange(current-1)"  v-show="current !== 1"> &lt;&lt; </a>

        <a  @click="onChange(num)"  v-for="(num, i) in this.getVisibileNumber" :key="i" :class="{ active: current === num }">{{ num }} </a>
        <a @click="onChange(current+1)"  v-show="current !== getPageNumber"> &gt;&gt; </a>
        <!-- 回到最后一页 -->
        <a @click="onChange(getPageNumber)" v-show="current !== getPageNumber"> &gt;&gt; | </a>
    </div>
</template>

<script>
export default {
    props: {
        current: {
            required: true,
            type: Number,
            defalut: 1
        },
        // size:{
        //     required:true,
        //     type:Number,
        //     defalut:10
        // },
        total: {
            required: true,
            type: Number,
            defalut: 0
        },
        //  一页显示多少条数据
        // limit:{
        //     required:true,
        //     type:Number
        // },
        // 显示可见的页码数
        size: {
            required: true,
            type: Number,
            defalut: 10
        }

    },
    computed: {
        getPageNumber() {
            return Math.ceil(this.total / this.size)
        },
        getMinPage() {
            //20  18 19 20 21 22 
            let min = this.current - (Math.floor(this.size / 2))
            if (min <= 1) {
                min = 1
            }
            return min
        },
        getMaxPage() {
            let max = this.getMinPage + this.size - 1
            if (max >= this.getPageNumber) {
                max = this.getPageNumber
            }
            return max
        },
        // 得到显示的数字
        getVisibileNumber() {
            let array = []
            for (let i = this.getMinPage; i <= this.getMaxPage; i++) {
                array.push(i)
            }
            return array
        },


    },
    data: () => ({
        number: [2, 5, 6]
    }),
    methods:{
        onChange(val){
            if(val<1){
                val=2
            }else if(val>this.getPageNumber){
                val=this.getPageNumber
            }
            console.log(val,"=====当前页码===",)
            this.$emit('pageChange',val)
        }
    }
}
</script>

<style lang="less" scoped>
.page-cotainer {
    text-align: center;

    a {
        margin-right: 5px;
        cursor: pointer;

        &.active {
            color: blueviolet;

        }

        &.disable {
            cursor: not-allowed;
            color: #999;
        }

    }

}
</style>