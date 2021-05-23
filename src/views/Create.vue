<template>
  <div class="md:flex md:flex-row">
    <div class="md:w-1/12"></div>
    <div class="md:w-5/6">
      <div class="w-full h-screen flex justify-center items-center bg-gray-100">
        <form @submit="create" class="md:w-2/5 flex flex-col bg-white p-10 justify-center items-center rounded-lg shadow-md">
          <p class="text-2xl font-bold mb-5">Tambah content</p>
          <input v-model="judul" type="text" name="" id="judul" placeholder="judul" class="w-full mb-5 p-2 border-2 rounded focus:border-indigo-400 outline-none shadow">
          <input v-model="link" type="url" name="" id="link" placeholder="link" class="w-full mb-5 p-2 border-2 rounded focus:border-indigo-400 outline-none shadow">
          <input v-model="deskripsi" type="text" name="" id="deskripsi" placeholder="deskripsi" class="w-full mb-5 p-2 border-2 rounded focus:border-indigo-400 outline-none shadow">
          <button type="submit" class="bg-indigo-500 hover:bg-indigo-800 rounded font-semibold text-white w-3/5 text-2xl shadow">Tambah</button>
        </form>
      </div>
    </div>
    <div class="md:w-1/12"></div>
  </div>
</template>

<script>
export default {
    name: 'Create',
    data() {
      return {
        judul: '',
        link: '',
        deskripsi: '',
        token: ''
      }
    },
    created() {
      this.token = localStorage.getItem('token') || ''
    },
    methods: {
      async create(){
        
      const reqRsponse = {
        method: "POST",
        headers: {
          "Content-Type" : "application/json",
          "Accept": "application/json",
          "Authorization": "Bearer " + this.token
        },
        body: JSON.stringify({
          judul : this.judul,
          link: this.link,
          deskripsi: this.deskripsi
        })
      }

      const res = await fetch("http://127.0.0.1:8000/api/content", reqRsponse)
      const data = await res.json()
      console.log(data)
      }
    }
}
</script>