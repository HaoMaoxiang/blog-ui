<template>
    <div>
        <div class="header" v-show="showHeader">
            <div class="brand">{{brand}}</div>
            <div class="header-tab hidden-sm-and-down">
                <a class="tab">博客</a>
                <a class="tab">刷题</a>
                <a class="tab">Github</a>
                <a class="tab">关于我</a>
            </div>
            <el-dropdown trigger="click" class="hidden-md-and-up">
                <span class="el-dropdown-link">
                    <i class="el-icon-menu"></i>
                </span>
                <el-dropdown-menu slot="dropdown">
                    <el-dropdown-item>博客</el-dropdown-item>
                    <el-dropdown-item>刷题</el-dropdown-item>
                    <el-dropdown-item>Github</el-dropdown-item>
                    <el-dropdown-item>关于我</el-dropdown-item>
                </el-dropdown-menu>
            </el-dropdown>
        </div>
        <div class="index">
            <p class="title">
                Blind men can judge no colours.
            </p>
            <p class="sub-title">
                不宜问道於盲
            </p>
            <div class="desc-tab">
                <a class="tab">博客</a>
                <a class="tab">刷题</a>
                <a class="tab">Github</a>
                <a class="tab">关于我</a>
            </div>
        </div>
    </div>

</template>

<script>
    export default {
        name: "Index",
        props:{
            brand:{           //这个就是父组件中子标签自定义名字
                type: String,
                required: true,
            }
        },
        data() {
            return {
                showHeader: false,
            }
        },
        methods:{
            handleScroll(){
                const height = document.documentElement.clientHeight || document.body.clientHeight;
                const top = document.documentElement.scrollTop + 60;
                this.showHeader = top > height;
            }
        },
        mounted (){
            window.addEventListener('scroll',this.handleScroll)
        },
        // 离开该页面需要移除这个监听的事件
        destroyed(){
            window.removeEventListener('scroll',this.handleScroll)
        }
    }
</script>

<style scoped>
    .header {
        position:fixed;
        display: -webkit-flex;
        display: flex;
        justify-content: space-between;
        align-items: center;
        height: 60px;
        width: 100%;
        background: url(../assets/img/bg.jpg);
    }
    .brand {
        margin-left: 10vw;
        font-size: 2rem;
        color: #efefef;
    }
    .header-tab {
        margin-right: 10vw;
    }
    .el-dropdown {
        margin-right: 10vw;
        font-size: 2rem;
        color: #efefef;
    }
    .index {
        display: -webkit-flex;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        height: 100vh;
        width: 100%;
        background: url(../assets/img/bg.jpg);
        background-size: cover;
        text-align: center;
    }
    .title {
        margin-bottom: 20px;
        font-family: Exo-thin,serif;
        font-weight: 600;
        font-size: 3.3rem;
        color: #efefef;
    }
    .sub-title {
        margin-bottom: 20px;
        font-family: YouYuan,serif;
        letter-spacing: 10px;
        font-size: 1.8rem;
        color: #efefef;
    }
    .desc-tab {
        width: 100%;
    }
    .tab {
        display: inline-block;
        margin: 20px 25px;
        padding: 5px;
        border-radius: 6px;
        background: hsla(0,0%,98%,.75);
        color: #090909;
        width: 100px;
        cursor: pointer;
        text-align: center;
    }

</style>