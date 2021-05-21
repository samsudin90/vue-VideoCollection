<template>
  <div class="md:flex md:flex-row">
    <div class="md:w-1/12"></div>
    <div class="md:w-5/6">
      <div class="w-full h-screen flex justify-center items-center bg-gray-100">
        <form action="" method="post" class="md:w-2/5 flex flex-col bg-white p-10 justify-center items-center rounded-lg shadow-md">
          <p class="text-2xl font-bold mb-5">Tambah content</p>
          <input type="text" name="" id="" placeholder="judul" class="w-full mb-5 p-2 border-2 rounded focus:border-indigo-400 outline-none shadow">
          <input type="text" name="" id="" placeholder="link" class="w-full mb-5 p-2 border-2 rounded focus:border-indigo-400 outline-none shadow">
          <input type="text" name="" id="" placeholder="deskripsi" class="w-full mb-5 p-2 border-2 rounded focus:border-indigo-400 outline-none shadow">
          <button type="submit" class="bg-indigo-500 hover:bg-indigo-800 rounded font-semibold text-white w-3/5 text-2xl shadow">Tambah</button>
        </form>
      </div>
    </div>
    <div class="md:w-1/12"></div>
  </div>
</template>

<script>
export default {
    name: 'Create'
}
</script>