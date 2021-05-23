<template>
  <div v-if="loading == true">
    <div class="text-center flex flex-col justify-center items-center content-center h-screen">
      <img src="@/assets/loading.gif">
    </div>
  </div>
  <div v-else class="home md:flex md:flex-row md:pt-4 pt-1 flex-grow">
    <div class="md:w-1/12"></div>
    <div class="md:w-5/6">
      <div class="md:text-right">
        <select name="" id="" class="rounded border-gray-500">
          <option value="">terbaru</option>
          <option value="">terlama</option>
        </select>
      </div>
      <hr class="divide-solid pt-2">
      <div v-for="d in data" :key="d.id" class="w-full md:h-72 md:px-4 md:pt-4 border-gray-100 border-2 rounded shadow md:mb-4 hover:bg-gray-200">
        <router-link :to="{ name: 'Detail', params: {id: d.id}}">
          <div class="flex flex-row">
            <iframe class="md:h-60 md:w-96 h-24 w-32" :src="d.link" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen>
            </iframe>
            <div class="flex flex-col px-4">
              <p class="md:text-xl text-sm font-semibold md:font-bold md:pt-3">{{d.judul}}</p>
              <p class="text-xs font-light text-gray-500 md:pt-4">{{d.deskripsi}}</p>
            </div>
          </div>
        </router-link>
      </div>
    </div>
    <div class="md:w-1/12"></div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  components: {
  },
  data() {
    return {
      data: [],
      loading: true
    }
  },
  methods: {
    async fetchData(){
      const res = await fetch("http://127.0.0.1:8000/api/content")
      const data = await res.json()
      console.log(data)
      return data
    }
  },
  async created() {
    const data = await this.fetchData()
    this.data = data.data
    this.loading = false
  }
}
</script>
