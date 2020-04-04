<template>
    <div>
        <Blog />
    </div>
</template>

<script>
    import Blog from './components/Blog.vue'

    export default {
        name: 'App',
        components: {
            Blog,
        }
    }
</script>

<style>
    @font-face {
        font-family: Exo;
        src: url("./assets/fonts/Exo.ttf");
    }
    @font-face {
        font-family: Exo-thin;
        src: url("./assets/fonts/Exo-Thin.ttf");
    }
    @font-face {
        font-family: YouYuan;
        src: url("./assets/fonts/YouYuan.ttf");
    }
    body {
        margin: 0;
        padding: 0;
        font-family: Exo, YouYuan, Open Sans, HelveticaNeue-Light, Helvetica Neue Light, Helvetica Neue, Hiragino Sans GB, Microsoft YaHei, Helvetica, Arial, sans-serif;
    }
    p {
        margin: 0;
    }
</style>
