<template>
  <div class="md:flex md:flex-row">
    <div class="md:w-1/12"></div>
    <div class="md:w-5/6">
      <div class="w-full h-screen flex justify-center items-center bg-gray-100">
        <form @submit.prevent="login" class="md:w-2/5 flex flex-col bg-white p-10 justify-center items-center rounded-lg shadow-md">
          <i class="fas fa-user text-5xl mb-5"></i>
          <p class="text-2xl font-bold mb-5">LOGIN</p>
          <input v-model="email" type="email" placeholder="email@example.com" class="mb-5 p-2 border-2 rounded focus:border-indigo-400 outline-none shadow">
          <input v-model="password" type="password" placeholder="some password" class="mb-5 p-2 border-2 rounded focus:border-indigo-400 outline-none shadow">
          <button type="submit" class="bg-indigo-500 hover:bg-indigo-800 rounded font-semibold text-white w-3/5 text-2xl shadow">LOGIN</button>
        </form>
      </div>
    </div>
    <div class="md:w-1/12"></div>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data() {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async login(){
      const reqRsponse = {
        method: "POST",
        headers: {
          "Content-Type" : "application/json",
          "Accept": "application/json"
        },
        body: JSON.stringify({
          email: this.email,
          password: this.password
        })
      }

      const res = await fetch("http://127.0.0.1:8000/api/login", reqRsponse)
      const data = await res.json()
      const token = data.token
      // mengirim dat token
      this.$emit("getToken", token)
    }
  },

  props: [
    
  ]


}
</script>