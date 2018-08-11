<template>
  <div>
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      msg: '',
    };
  },
  created: function onCreate() {
    this.fetchItems();
  },
  methods: {
    fetchItems() {
      const uri = 'http://localhost:3000/home/';
      this.axios.get(uri).then((response) => {
        this.msg = response.data;
      });
    },
  },
};
</script>

<style scoped>
</style>
