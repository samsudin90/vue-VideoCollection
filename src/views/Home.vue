<template>
  <div class="home md:flex md:flex-row md:pt-4 pt-1">
    <div class="md:w-1/12"></div>
    <div class="md:w-5/6">
      <div class="text-right">
        <select name="" id="" class="rounded border-gray-500">
          <option value="">terbaru</option>
          <option value="">terlama</option>
        </select>
      </div>
      <hr class="divide-solid pt-2">
      <div class="md:flex-col grid md:grid-flow-col md:grid-cols-2 px-1 justify-items-stretch items-stretch md:space-x-2">
        <div class="flex-row flex md:w-1/5 py-3">
        <iframe src="https://www.youtube.com/embed/tgbNymZ7vqY" frameborder="0" class="w-40"></iframe>
          <div class="px-4">
            <router-link to="/detail">
              <p class="text-2xl font-semibold">lofi hip hop radio - beats to relax/study to</p>
            </router-link>
          </div>
        </div>
        <div class="flex-row flex md:w-1/5 md:border-2">
        <iframe src="https://www.youtube.com/embed/tgbNymZ7vqY" frameborder="0" class="w-40"></iframe>
          <div class="px-4">
            <p class="text-2xl font-semibold">lofi hip hop radio - beats to relax/study to</p>
          </div>
        </div>
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
  }
}
</script>
