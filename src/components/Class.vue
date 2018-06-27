<template>
    <div>
        <p>3.Class 与 Style 绑定</p>
        <div>
            <p>动态切换样式</p>
            <p class="class-p-base" v-bind:class="{'class-p':isShowClass}">
                是否绑定Class {{isShowClass}}</p>
            <button @click="()=>this.changeClass()">修改样式</button>
        </div>

        <div>
            <p>绑定class对象</p>
            <p :class="classObj">
                是否绑定Class {{classObj.class_p}}</p>
            <button @click="()=>this.changeClassObj()">修改样式</button>
        </div>

        <div>
            <p>三元表达式</p>
            <p v-bind:class="[isShowClass3?'class_p':'class-p']">
                是否绑定Class {{isShowClass3}}</p>
            <button @click="()=>this.changeClass3()">修改样式</button>
        </div>

    </div>
</template>

<script>
import "./styles/class.scss";

export default {
    name: "Class",
    props: {},
    data() {
        return {
            isShowClass: true,
            isShowClass3: true,
            classObj: {
                class_p: true
            }
        };
    },
    //计算属性是基于它们的依赖进行缓存的
    computed: {},
    methods: {
        changeClass() {
            this.isShowClass = !this.isShowClass;
        },
        changeClassObj() {
            this.classObj.class_p = !this.classObj.class_p;
        },
        changeClass3() {
            this.isShowClass3 = !this.isShowClass3;
        }
    }
};
</script>
