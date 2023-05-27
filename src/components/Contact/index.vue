<template>
    <div class="contact-container">
        <ul>
            <li>
                <a>
                   <IconFont type="github"></IconFont> 
                    ywq-github
                    <div class="pop">
                    <img src="https://pica.zhimg.com/36940066ff196785773634369b4290c8_r.jpg?source=1940ef5c" alt="" >
                </div>
                </a>
                
            </li>
            <li>
                <a>
                   <IconFont type="qq"></IconFont> 
                    995359350
                    <div class="pop">
                    <img src="https://pica.zhimg.com/36940066ff196785773634369b4290c8_r.jpg?source=1940ef5c" alt="" >
                </div>
                </a>
                
            </li>
            <li>
                <a>
                   <IconFont type="weixin"></IconFont> 
                    weixin
                    <div class="pop">
                    <img src="https://pica.zhimg.com/36940066ff196785773634369b4290c8_r.jpg?source=1940ef5c" alt="" >
                </div>
                </a>
                
            </li>
            <li>
                <a>
                    <IconFont type="email"></IconFont>
                    email
                    <div class="pop">
                        <img src="https://pica.zhimg.com/36940066ff196785773634369b4290c8_r.jpg?source=1940ef5c" alt="">
                    </div>
                </a>

            </li>
        </ul>
    </div>
</template>

<script>
import IconFont from '@/components/MyIcon/index.vue'
export default {
    components: {
        IconFont
    }
}
</script>

<style lang="less" scoped>
@import url(@/styles/global.less);

.contact-container {
    padding: 0 16px;

    ul {
        list-style: 0;
        margin: 0;
        //    padding: 20px;
    }

    //  .self-center();
    li {
        position: relative;
        cursor: pointer;
        color: rgba(0, 255, 255, .3);
        margin: 14px 0;

        &:hover {
            .pop {
                transform: scale(1);
            }
        }

        a:hover {
            color: #808c;


        }
    }
}

.pop {
    position: absolute;
    bottom: 10px;
    margin-bottom: 20px;
    z-index: 100;
    border-radius: 5px;
    background-color: #fff;
    transform-origin: center bottom;
    transition: .3s;
    transform: scale(0);

    &::after {
        content: '';
        position: absolute;
        bottom: -4px;
        width: 8px;
        height: 8px;
        background: #fff;
        left: 50%;
        transform: translateX(-50%) rotate(45deg);
    }

    img {
        width: 150px;
        height: 150px;
    }
}</style>