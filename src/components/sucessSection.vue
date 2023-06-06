<script>
export default {
  name: "sucessSection",
  emits: ["demissMsg"]
};
</script>

<template>
  <div class="sucess-section">
    <img src="../assets/images/icon-success.svg" alt="" />
    <h1>Thank you for subscribing!</h1>
    <p>
      A confirmation email has been sent to <br />
      {{ email }}. Please open it and click <br />
      the button inside to confirm your subscription.
    </p>
    <button @click="$emit('demissMsg')">Dismiss message</button>
  </div>
</template>

<style scooped>
  .sucess-section {
    height: 520px;
    width: 500px;           
    background-color: #fff;
    border-radius: 2em;
    padding: 60px;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  .sucess-section button {
    width: 100%;
    height: 55px;
    color: #fff;
    background-color: hsl(234, 29%, 20%);
    border-radius: 1em;
    margin-top: 40px;
    transition: .3s;
  }
  .sucess-section button:hover {
    background: linear-gradient(165deg, rgba(252,112,102,1) 0%, rgba(250,103,52,1) 100%);
  }

  img {
    width: 65px;
    height: 65px;
  }
  h1 {
    margin: 30px 0;
    font-size: 3.3em;
    color: hsl(234, 29%, 20%);
  }


</style>