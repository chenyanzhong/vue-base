<template>
    <div>
        <div>
            <p>文本</p>
            <input v-model="input" placeholder="edit me">
            <p>input is: {{ input }}</p>
        </div>

        <div>
            <p>多行文本</p>
            <textarea v-model="textarea" placeholder="add multiple lines"></textarea>
            <p>textarea is: {{ textarea }}</p>
        </div>

        <div>
            <p>单选框</p>
            <input type="checkbox" v-model="checked">
            <label>{{ checked }}</label>
        </div>

        <div>
            <p>复选框</p>
            <input type="checkbox" id="jack" value="Jack" v-model="checkedNames">
            <label for="jack">Jack</label>
            <input type="checkbox" id="john" value="John" v-model="checkedNames">
            <label for="john">John</label>
            <input type="checkbox" id="mike" value="Mike" v-model="checkedNames">
            <label for="mike">Mike</label>
            <p>Checked names: {{ checkedNames }}</p>
        </div>

        <div>
            <p>单选框</p>
            <input type="radio" id="one" value="One" v-model="picked">
            <label for="one">One</label>
            <br>
            <input type="radio" id="two" value="Two" v-model="picked">
            <label for="two">Two</label>
            <p>Picked: {{ picked }}</p>
        </div>

        <div>
            <p>选择框</p>
            <select v-model="selected">
                <option disabled value="">请选择</option>
                <option>A</option>
                <option>B</option>
                <option>C</option>
            </select>
            <span>Selected: {{ selected }}</span>
        </div>

    </div>
</template>

<script>
// .lazy .number .trim
export default {
    name: "Input",
    props: {},
    data() {
        return {
            input: "",
            textarea: "",
            checked: true,
            checkedNames: [],
            picked: "One",
            selected: ""
        };
    }
};
</script>
