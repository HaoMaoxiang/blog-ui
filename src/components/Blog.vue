<template>
    <div>
        <Index v-bind:brand="brand"/>
        <div style="height: 10000px; background-color: #42b983"></div>
    </div>
</template>

<script>
    import Index from '../components/Index.vue';
    export default {
        name: "Blog",
        data() {
            return {
                brand: "博客",
            }
        },
        components: {
            Index,
        }
    }
</script>

<style scoped>

</style>