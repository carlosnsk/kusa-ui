<template>
<div class="home">
    <div class="topnavdAndBanner">
        <Topnav />
        <div class="banner">
            <h1 class="title">Kusa UI</h1>
            <h2 class="desc">一个基于Vue 3的UI框架</h2>
            <p class="actions">
                <router-link to="/doc/intro">开始体验</router-link>
                <a href="https://github.com/nshcarlos/kusa-ui" target="_blank">
                    <svg class="icon" aria-hidden="true">
                        <use xlink:href="#icon-github"></use>
                    </svg>
                    <span>github</span>
                    <svg class="icon" aria-hidden="true">
                        <use xlink:href="#icon-zhuanfa"></use>
                    </svg>
                </a>
            </p>
        </div>
    </div>
    <div class="features">
        <ul>
            <li>
                <svg>
                <use xlink:href="#icon-vue"></use>
                </svg>
                <h3>基于 Vue 3</h3>
                <p>使用了 Vue 3 Composition API</p>
            </li>
            <li>
                <svg>
                <use xlink:href="#icon-ts"></use>
                </svg>
                <h3>基于 TypeScript </h3>
                <p>源代码采用 TypeScript 书写（非严格检查）</p>
            </li>
            <li>
                <svg>
                <use xlink:href="#icon-light"></use>
                </svg>
                <h3>代码易读</h3>
                <p>每个组件的源代码都非常简洁</p>
            </li>
        </ul>
    </div>
</div>
</template>
<script lang="ts">
import Topnav from '../components/Topnav.vue'
export default {
    components: {Topnav}
}
</script>
<style lang="scss" scoped>
$border-radius: 50px;
.topnavdAndBanner{
    background: url('../assets/grass.jpg') no-repeat;
    background-attachment:fixed;
    background-position:75% 75%;
    background-size: cover;
}
.banner {
    color:#2c3e46;
    padding: 150px 0;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    padding-bottom: 140px;
    > .title{
        font-size: 46px;
        padding: 0 4px;
        font-weight: 600;
    }
    > .desc{
        font-size: 22px;
        padding: 0 4px;
    }
    > .actions{
        padding: 36px 0 0;
        margin-bottom: -48px;
        a {
            margin:0 16px;
            margin-top: 10px;
            padding: 8px 24px;
            font-weight: 700;
            display: inline-block;
            $h: 28px;
            border-radius: $border-radius;
            transition: all 1s;
            background: rgba( 255, 255, 255, 0.80);
            backdrop-filter: blur( 0px );
            -webkit-backdrop-filter: blur( 0px );
            text-decoration: none;
            &:nth-child(1) {
                color: rgb( 135, 204, 191 );
                border: 1px solid rgb( 135, 204, 191 );
                text-transform: uppercase;
                white-space: nowrap;
                font-weight: 700;
            }
            &:nth-child(2) {
                border: 1px solid rgba(122, 120, 120);
                background-color: rgba(246, 246, 246, .80);
                text-transform: uppercase;
                svg:nth-child(1) {
                    transform: scale(1.6);
                    margin: 0 16px 0 -12px;
                }
                svg:nth-child(3) {
                    transform: scale(0.7);
                    margin: 0 -10px 0 4px;
                }
            }

        }

    }
}
.features {
    margin: 64px auto;
    padding: 0 16px;

    @media (min-width: 800px) {
        width: 800px;
        >ul {
            >li {
                width: 50%;
            }
        }
    }
    @media (min-width: 1200px) {
        width: 1200px;
        >ul {
            >li {
                width: 33.3333%;
            }
        }
    }
    >ul {
        display: flex;
        flex-wrap: wrap;
        >li {
            margin: 16px 0;
            display: grid;
            justify-content: start;
            align-content: space-between;
            grid-template-areas:
                "icon title"
                "icon text";
            grid-template-columns: 80px auto;
            grid-template-rows: 1fr auto;
            >svg {
                grid-area: icon;
                width: 64px;
                height: 64px;
            }
            >h3 {
                grid-area: title;
                font-size: 28px;
            }
            >p {
                grid-area: text
            }
        }
    }
}
</style>