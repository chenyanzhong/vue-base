<template>
    <div id="app">
        <div class="nav-bg">
            <p class="nav-div" v-for="(item,key) in list" :key="key" @click="showPage(item.index)">
                {{item.page}}
            </p>
        </div>

        <Grammar v-if="currenpage===1" />
        <ComputeWatch v-if="currenpage===2" />
        <Class v-if="currenpage===3" />
    </div>
</template>

<script>
import "./components/styles/index.scss";

import Grammar from "./components/Grammar.vue";
import ComputeWatch from "./components/ComputeWatch.vue";
import Class from "./components/Class.vue";

export default {
    name: "app",
    components: {
        Grammar,
        ComputeWatch,
        Class
    },
    data() {
        return {
            currenpage: 1,
            list: [
                {
                    page: "1.模版语法",
                    index: 1
                },
                {
                    page: "2.计算属性和侦听器",
                    index: 2
                },
                {
                    page: "3.class与styles",
                    index: 3
                }
            ]
        };
    },
    methods: {
        showPage(page) {
            this.currenpage = page;
        }
    }
};
</script>

