<script>
import mainContent from "./mainContent.vue"

export default {
    name: "mainComponent",
    components: {
        mainContent
    },
    emits: ["subscribed"],
    methods: {
        subscribed2() {
            this.$emit("subscribed")
        }
    }
    
}
</script>


<template>
    <main>
        <mainContent @subscribed2="subscribed2"/>
        <div class="image">
        </div>
    </main>    
</template>

<style>
    main {
        width: 930px;
        height: 640px;
        background-color: #fff;
        border-radius: 2em;
        padding: 25px;
        display: flex;
    }
    .image {
        width: 50%;
        height: 590px;
        border-radius: 2em;
        background-image: url(../assets/images/illustration-sign-up-desktop.svg);
        background-repeat: no-repeat;
        background-size: contain;
    }
</style>