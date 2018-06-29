<template>
    <div>
        <p>data 每个实例可以维护一份被返回对象的独立的拷贝</p>
        <ButtonCounter name="one"> </ButtonCounter>
        <ButtonCounter name="two"> </ButtonCounter>
        <ButtonCounter name="three"> </ButtonCounter>

        <p>利用数组循环view</p>
        <ButtonCounter v-for="(item,key) in list" v-bind:key="key" v-bind:name="item.title"> </ButtonCounter>

    </div>
</template>

<script>
import "./styles/class.scss";

import Vue from "vue";
// 定义一个名为 button-counter 的新组件
let ButtonCounter = Vue.component("button-counter", {
    props: ["name"],
    data: function() {
        return {
            count: 0
        };
    },
    template:
        '<button v-on:click="count++">You clicked {{name}} {{ count }} times.</button>'
});

export default {
    name: "Class",
    props: {},
    components: {
        ButtonCounter
    },
    data() {
        return {
            list: [
                { id: 1, title: "one " },
                { id: 2, title: "two " },
                { id: 3, title: "three " }
            ]
        };
    }
};
</script>
