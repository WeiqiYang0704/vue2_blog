<template>
    <div class="AvatarName-container">
        <img :src="url" :style="{ width: size + 'px', height: size + 'px' }" class="myImg" />
    </div>
</template>

<script>

export default {
    props: {
        url: {
            required: true,
            type: String
        },
        size: {
            type: Number,
            default: 150
        }
    }
}
</script>

<style scoped>
.myImg {
    border-radius: 50%;
    display: block;
    object-fit: cover;
    margin: 0 auto;
}
</style>