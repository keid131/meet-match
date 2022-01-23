<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <button @click="onClick">API 実行</button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import axios from 'axios'

export default defineComponent({
  name: "Home",
  setup(_, context) {
    const onClick = () => {
      axios.get(process.env.VUE_APP_API_ENDPOINT + '/hello').then(res => {
        console.log(res)
      })
      console.log("hoge");
    };
    return {
      onClick,
    };
  },
});
</script>
