<template>
    <div>
        <div>生命周期</div>
        <div>
            <p>生命周期 :</p>
            <p v-for="(item,key) in list" :key="key">{{item}}</p>
        </div>

        <div>
            <p>可以操作数据的生命周期 : </p>
            <p>{{dataList}}</p>
        </div>

        <div>
            <p>更数据操作的生命周期 : </p>
            <p>{{updateList}}</p>
        </div>

        <p>生命周期流程 :</p>
        <img src="./../assets/lifecycle.png" alt="生命周期图">
    </div>
</template>

<script>
export default {
    name: "Life",
    props: {},
    data() {
        return {
            list: [
                "beforeCreate",
                "created",
                "beforeMount",
                "mounted",
                "beforeDestroy",
                "destroyed",
                "beforeUpdate",
                "updated"
            ],
            dataList: [],
            updateList: []
        };
    },
    beforeCreate() {},
    created() {
        this.dataList.push("created");
    },
    beforeMount() {
        this.dataList.push("beforeMount");
    },
    mounted() {
        this.dataList.push("mounted");
        this.dataList.push("beforeDestroy");
        this.dataList.push("destroyed");

        this.updateList.push("beforeUpdate");
        this.updateList.push("updated");
    },
    beforeUpdate() {
        console.log("beforeUpdate");
        // 会造成无限循环
        // this.dataList.push("beforeUpdate");
    },
    updated() {
        console.log("updated");
        // 会造成无限循环
        //  this.dataList.push("updated");
    },
    beforeDestroy() {
        this.dataList.push("beforeDestroy");
    },
    destroyed() {
        this.dataList.push("destroyed");
        console.log(this.dataList);
    }
};
</script>
