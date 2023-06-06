<script>

export default {
    name: "formInputs",
    data() {
        return {
            idInput: "emailInput",
            isEmailValid: true,
        }
    },
    emits: ["subscribed1"],
    methods: {
        subscribe(e){
            this.isValid()
            if (this.isValid()) {
                this.$emit("Subscribed1")
            }
        },
    
        isValid() {
            var email = document.getElementById("emailInput")
            const regex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            var teste = regex.test(email.value);

            if (teste) {
                this.isEmailValid = true;
                email.classList.remove("invalidInput")
                return true;
            }else {
                this.isEmailValid = false;
                email.classList.add("invalidInput")
                return false;
            }
        },
        removeError(){
            var email = document.getElementById("emailInput")
            const regex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;

            var teste = regex.test(email.value);
            
            if (teste) {
                this.isEmailValid = true;
                email.classList.remove("invalidInput")
                return true;
            }
        }
    }    
}
</script>

<template>
    <form @submit.prevent="subscribe">
        <label for="email">Email Adress</label>
        <p v-show="!isEmailValid" class="errorMsg" >Valid email required</p>
        <input type="email" v-on:keypress="removeError" class="" placeholder="email@company.com" :id="idInput">
        <input class="submitButton" type="submit" value="Subscribe to montly newsletter">
    </form>
    
</template>

<style scoped>
    form {
        display: flex;
        flex-direction: column;
        position: relative;
        margin-top: 40px;
    }
    label {
        font-weight: 800;
    }
    input  {
        width: 375px;
        height: 56px;
        border: 1px solid hsl(235, 18%, 26%);
        border-radius: .7em;
        padding: 0 20px;
        margin: 10px 0;
    }
    .submitButton {
        background-color: hsl(234, 29%, 20%);
        color: #ffffff;
        border-radius: .7em;
        font-size: 1em;
        font-weight: 700;
        letter-spacing: 1px;
        margin-top: 10px;
    }
    .errorMsg {
        position: absolute;
        right: 35px;
        color: hsl(4, 100%, 67%);
        font-weight: 700;
        letter-spacing: 1px;
        transition: .1s;

    }
    .invalidInput, .invalidInput:focus {
        border: 1px solid hsl(4, 100%, 67%) !important;
        background-color: hsla(4, 100%, 67%, 0.206) !important;
        color: hsl(4, 100%, 67%);
        outline: none;
        transition: .1s;

    }

</style>
