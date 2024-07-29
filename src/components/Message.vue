<template>
  <h1>Message: {{ message }}</h1>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      message: "",
    };
  },

  methods: {
    getData() {
      axios.get("http://localhost:8080/hello").then((response) => {
        this.message = response.data;
      });
    },
  },

  mounted() {
    this.getData();
  },
};
</script>

<style></style>
