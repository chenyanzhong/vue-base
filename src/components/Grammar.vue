<template>
    <div>
        <p>1.模版语法</p>

        <div> 插入文本: {{msg}}</div>

        <div v-html="rawHtml"> </div>

        <div>
            <p>使用js表达式: </p>
            <p>{{`{ 1+1 }`}} = {{1+1}}</p>
            <p>{ ok ? 'YES' : 'NO' } = {{ ok ? 'YES' : 'NO' }}</p>
            <p>{{`{ ok && YES }`}} = {{ ok && 'YES' }}</p>
        </div>

        <div>
            <p>使用v-if:</p>
            <p>v-if="true" p显示 </p>
            <p v-if="true">p显示</p>
            <p>v-if="false" p隐藏</p>
            <p v-if="false">隐藏</p>
        </div>

        <div>
            <p>参数链接:</p>
            <p>v-bind:href="baiduUrl"</p>
            <a v-bind:href="baiduUrl">百度一下</a>
        </div>

        <div>
            <p>缩写:</p>
            <p>:href="baiduUrl"</p>
            <a :href="baiduUrl">百度一下</a>
        </div>

        <div>
            <p>赋值按钮id: </p>
            <p>v-on:click</p>
            <button class="hello-vue" v-bind:id="btnid" v-on:click="()=>this.getBtnId()">{{btnContent}}</button>
        </div>

         <div>
            <p>缩写: </p>
            <p>@click</p>
            <button class="hello-vue" v-bind:id="btnid" @click="()=>this.getBtnId()">{{btnContent}}</button>
        </div>

    </div>
</template>

<script>
export default {
    name: "Grammar",
    props: {},
    data() {
        return {
            msg: "hello vue",
            rawHtml: `<div>插入html: 被插入的div</div>`,
            btnid: 1,
            btnContent: "点击获取按钮id",
            ok: "YES",
            baiduUrl: "https://www.baidu.com/"
        };
    },
    methods: {
        getBtnId() {
            let id = document.getElementById(1).id;
            console.log(id);
            this.btnContent = "按钮id为" + id;
        }
    }
};
</script>
