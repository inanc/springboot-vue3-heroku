<template>
  <b-container flex-container class="mx-auto d-flex justify-content-end  flex-column" style="width: 200px;height: 50vh;">

  <h1>{{ msg }}</h1>
  <b-button variant="outline-primary" v-on:click="reverseMessage">Reverse Message</b-button>

  </b-container>

</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      msg: ''
    }
  },
  mounted() {
    fetch("/api/message")
      .then((response) => response.text())
      .then((data) => {
          this.msg = data;
      });
  },
  methods: {
    reverseMessage() {
      this.msg = this.msg
          .split('')
          .reverse()
          .join('');
    }
  }
}
</script>