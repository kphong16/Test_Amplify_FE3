<template>
  <div>
    <h1>{{ message }}</h1>
    <ul>
      <li v-for="item in items" :key="item.item_id">{{ item.item_id }}: {{ item.q }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  date() {
    return {
      message: "Hello from Vue.js!",
      items: []
    };
  },
  async created() {
    const response = await fetch("http://43.201.55.4:8000/items/1?q=test");
    const data = await response.json();
    this.items = [data];
  }
};
</script>
