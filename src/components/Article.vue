<template>
    <div>
        <h1 v-bind='$attrs'>{{title}}</h1>
        <h1>Likes - {{likes}}</h1>
        <h1>Published - {{isPublished ? 'Yes' : 'No' }}</h1>
        <h4 v-if="likes >= 100 ">GOOD LIKES</h4>
        <h4 v-else>AVERAGE LIKES</h4>
    </div>
</template>

<script>
export default {
    name:'Article',
    props: { 
        title: {
        type: String,
        required: true,
        default: 'Default Article Title'
        },
        likes: {
        type: Number,
        required: true,
        default: 50
        },
        isPublished : {
        type: Boolean,
        required: true,
        default: true
        },
    },
    inheritAttrs: false,
}
</script>

<style scoped>

</style>