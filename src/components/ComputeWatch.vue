<template>
    <div>
        <p>2.计算属性和侦听器</p>
        <div>
            <p>computed : 计算属性是基于它们的依赖进行缓存的</p>
            <p>reversedMessage : {{reversedMessage}}</p>
        </div>
        <div>
            <p>依赖无改动则不改值</p>
            <p>Date.now() : {{now}}</p>
            <p>Date.now() : {{now}}</p>
            <p>Date.now() : {{now}}</p>
            <p>Date.now() : {{now}}</p>
        </div>

        <div>
            <p>设置计算属性的 getter setter</p>
            <p>name : {{fullName}}</p>
            <button @click="()=>this.setName()">点击设置新名字</button>
        </div>

        <div>watch : 侦听器</div>
        <div>
            <p>当需要在数据变化时执行异步或开销较大的操作时，这个方式是最有用的</p>
            <p> time : {{time}}</p>
            <button @click="()=>this.setTime()">设置新时间</button>
            <p>{{timeMessage}}</p>
        </div>

    </div>
</template>

<script>
export default {
    name: "ComputeWatch",
    props: {},
    data() {
        return {
            message: "hello vue",
            name: "old name",
            time: new Date(),
            timeMessage: "旧时间"
        };
    },
    //计算属性是基于它们的依赖进行缓存的
    computed: {
        reversedMessage: function() {
            // `this` 指向 vm 实例
            return this.message
                .split("")
                .reverse()
                .join("");
        },
        now: function() {
            return Date.now();
        },
        fullName: {
            // getter
            get: function() {
                return this.name;
            },
            // setter
            set: function(newValue) {
                this.name = newValue;
            }
        }
    },
    watch: {
        time: function(val, oldVal) {
            new Promise(function(resolve) {
                setTimeout(function() {
                    let time = val - oldVal;
                    resolve(time + "ms前请求修改新时间成功");
                }, 1000);
            }).then(value => {
                this.timeMessage = value;
            });
        }
    },
    methods: {
        setName(name) {
            this.fullName = "new name";
        },
        setTime() {
            this.time = new Date();
        }
    }
};
</script>
