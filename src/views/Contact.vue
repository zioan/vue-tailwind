<template>
  <form class="w-8/12 p-3 bg-gray-100 mx-auto flex flex-col items-center">
    <div class="input-group">
      <label>Email</label>
      <input
        class="custom-input"
        type="email"
        required
        placeholder="Email"
        v-model="email"
      />
    </div>
    <div class="input-group mt-4">
      <label>Password</label>
      <input
        v-model="pass"
        class="custom-input"
        type="password"
        required
        placeholder="Password"
      />
    </div>
    <input
      @click.prevent="showData = !showData"
      class="submit-btn"
      type="submit"
      value="Show data"
    />
  </form>
  <div v-if="showData">
    <p>Email: {{ email }}</p>
    <p>Pass: {{ pass }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      pass: "",
      showData: false,
    };
  },
  methods: {
    readData() {
      this.email = email;
      this.pass = pass;
    },
  },
};
</script>

<style scoped>
.input-group {
  @apply flex flex-col items-start;
}
input[type="submit"] {
  @apply bg-gray-300 outline-none px-6 py-3 my-3 mx-auto hover:bg-red-300 cursor-pointer;
}
label {
  @apply text-lg font-bold;
}
</style>
