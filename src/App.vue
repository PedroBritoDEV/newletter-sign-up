<script>
  import mainComponent from "./components/mainComponent.vue"
  import sucessComponent from "./components/sucessSection.vue"
  export default {
    name: "App",
    components: {
      mainComponent,
      sucessComponent
    },
    data() {
      return {
        isUserSubscribed: false
      }
    },
    methods: {
      subscribed() {
        this.isUserSubscribed = true;
      },
      demissMensage() {
        this.isUserSubscribed = false;
        let input = document.querySelector("input")
        input.value = ""
        
      }

    }
  }
</script>

<template>
  <mainComponent @subscribed="subscribed" v-show="!isUserSubscribed"/>
  <sucessComponent @demissMsg="demissMensage" v-show="isUserSubscribed"/>
</template>


