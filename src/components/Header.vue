<template>
    <div class="md:flex md:flex-row">
        <div class="md:w-1/12"></div>
        <div class="md:w-5/6 bg-blue-500 flex items-stretch py-2 rounded px-4 content-between justify-between">
            <div class="flex flex-row">
                <router-link to="/">
                    <i class="far fa-play-circle md:text-5xl text-3xl text-white text-center"></i>
                </router-link>
                <router-link to="/">
                    <h3 class="md:text-3xl text-2xl text-white justify-center items-center font-semibold pl-4">JAJ link</h3>
                </router-link>
            </div>
            <div class="justify-center items-center py-2">
                <input type="text" placeholder="cari video" class="w-20 md:w-60 focus:outline-none border-2 border-gray-100 rounded">
                <!-- <button type="submit" class="absolute pl-3 text-white">
                    <i class="fas fa-search"></i>
                </button> -->
            </div>
            <div class="">
                <router-link to="/login">
                    <i class="fas fa-users-cog text-white text-3xl md:text-5xl"></i>
                </router-link>
            </div>
        </div>
        <div class="md:w-1/12"></div>
    </div>
</template>

<script>
export default {
    name: 'Header'
}
</script>