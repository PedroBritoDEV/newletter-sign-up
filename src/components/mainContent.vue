<script>
import formInputs from "./formInputs.vue"

export default {
    name: "mainComponent",
    components: {
        formInputs
    },
    emits: ["subscribed2"],
    methods: {
        subscribed1() {
            this.$emit("subscribed2")
        }
    }
}
</script>

<template>
    <section>
        <h2>Stay Updated!</h2>
        <p class="information">join 60,000+ product managers receiving monthly updates on: </p>
        <ul>
            <li>
                <img src="../assets/images/icon-list.svg" alt="icon list">
                <p>Product discovery and building what matters</p>
            </li>
            <li>
                <img src="../assets/images/icon-list.svg" alt="icon list">
                <p>Measuring to ensure updates are a success</p>
            </li>
            <li>
                <img src="../assets/images/icon-list.svg" alt="icon list">
                <p>And much more!</p>
            </li>
        </ul>
        <formInputs @subscribed1="subscribed1"/>
    </section>
</template>

<style scoped>
    section {
        padding: 30px;
        display: flex;
        flex-direction: column;
        justify-content: center;
    }
    h2 {
        font-size: 3.5em;
    }
    .information {
        margin: 25px 0;
    }
    ul li{
       list-style: none; 
       display: flex;
       margin-bottom: 10px;
    }
    ul li img {
        margin-right: 20px;
        width: 20px;
        height: 20px;
    }
    
</style>