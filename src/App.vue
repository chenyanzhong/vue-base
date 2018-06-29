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
        <Life v-if="currenpage===4" />
        <Input v-if="currenpage===5" />
        <ComponentBase v-if="currenpage===6" />
    </div>
</template>

<script>
import "./components/styles/index.scss";

import Grammar from "./components/Grammar.vue";
import ComputeWatch from "./components/ComputeWatch.vue";
import Class from "./components/Class.vue";
import Life from "./components/Life.vue";
import Input from "./components/Input.vue";
import ComponentBase from "./components/ComponentBase.vue";

export default {
    name: "app",
    components: {
        Grammar,
        ComputeWatch,
        Class,
        Life,
        Input,
        ComponentBase
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
                },
                {
                    page: "4.生命周期",
                    index: 4
                },
                {
                    page: "5.表单",
                    index: 5
                },
                {
                    page: "6.组件基础",
                    index: 6
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

