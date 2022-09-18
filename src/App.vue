<template>
  <div id="app">
    <input
      type="text"
      placeholder="Enter number"
      v-mask="'#### - #### - #### - ####'"
      v-model="userInputValue"
    />
    <p>Masked input: {{ userInputValue }}</p>
    <h3>Parsed value: {{ parsedInputValue }}</h3>
    <!--
      www.nightprogrammer.com
    -->
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      userInputValue: "",
    };
  },
  computed: {
    parsedInputValue() {
      let matchedInputs = this.userInputValue.match(/\d+/g);
      let parsedString = "";

      if (matchedInputs && matchedInputs.length) {
        matchedInputs.forEach((m) => {
          parsedString += m;
        });
      }

      return parsedString;
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  padding: 24px;
}

input {
  font-size: 18px;
  padding: 4px 8px;
  border: 2px solid rgb(98, 0, 255);
  background: rgb(234, 221, 255);
  outline: none;
}
</style>
