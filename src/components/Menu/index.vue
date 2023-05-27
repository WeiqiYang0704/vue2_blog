<template>
    <div class="menu-container">
        <ul>
            <li v-for="item in items">
                <RouterLink
                :exact="item.exact" 
                active-class="selected" 
                exact-active-class="" 
                :to="{name:item.name}">
                    <Icon :type="item.icon"> </Icon>
                    {{ item.title }}
                </RouterLink>
            </li>

        </ul>
    </div>
</template>

<script>
import Icon from '@/components/MyIcon'
export default {
    components: {
        Icon
    },
    data: () => {
        return ({
            items: [
                {
                    name: 'Home',
                    title: '首页',
                    icon: 'home',
                    exact: true,
                },
                {
                    name: 'Article',
                    title: '文章',
                    icon: 'user',
                    exact: true,
                },
                {
                    name: 'About',
                    title: '关于我',
                    icon: 'shop',
                    exact: true,
                },
                {
                    name: 'Project',
                    title: '项目&效果',
                    icon: 'list',
                    startWidth: true,
                    exact: false,
                },
                {
                    name: 'Message',
                    title: '留言板',
                    icon: 'more',
                    exact: true,
                },
            ],
            pathtitle: ''
        })
    },
    methods: {
        isSelected(val) {
            this.pathtitle = val
            return val === location.pathtitle
        }
    },
    computed: {

    }
}
</script>

<style lang="less" scoped>
.menu-container {
    margin-top: 16px;
    font-size: 16px;

    ul li {

        display: flex;

        a {
            flex: 1;
            padding: 10px 16px;
            cursor: pointer;
        }

        .selected {
            background-color: #815d5d66;
            border-radius: 6px;
        }
    }
}
</style>