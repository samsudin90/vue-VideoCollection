<template>
    <div v-if="token == ''">
        <!-- menerima data token yang akan diproses di method -->
        <Login @getToken="getTokenId" />
    </div>
    <div v-else class="md:flex md:flex-row">
        <div class="md:w-1/12"></div>
        <div v-if="loading == true">
            <div class="text-center flex flex-col justify-center items-center content-center h-screen">
            <img src="@/assets/loading.gif">
            </div>
        </div>
        <div v-else class="md:w-5/6">
            <div class="flex flex-row w-full content-between justify-between">
            <router-link to="/create">
                <button class="flex text-left m-4 -mb-1 p-2 border-2 rounded bg-indigo-500 text-white text-xl focus:outline-none font-semibold outline-none focus:bg-indigo-800">tambah</button>
            </router-link>
            <button v-on:click="logout" class="flex text-right border-2 bg-red-500 text-white focus:outline-none focus:bg-red-600 text-xl outline-none m-4 p-2 rounded-lg">log out</button>
            </div>
            <div class="overflow-x-auto">
                <div class="w-full bg-gray-100 justify-center items-center py-2 rounded">
                    <table class="table-auto w-full justify-between">
                        <thead>
                            <tr class="bg-gray-200 text-gray-600 text-sm leading-normal uppercase">
                                <th class="p-2">judul</th>
                                <th class="">link</th>
                                <th class="">deskripsi</th>
                                <th class="">action</th>
                            </tr>
                        </thead>
                        <tbody class="text-gray-600 text-sm font-light bg-white w-full mx-2 px-2">
                            <tr v-for="d in data" :key="d.id" class="border-b border-gray-200 hover:bg-gray-100 p-4 mx-2">
                                <td class="p-4 justify-center items-center text-center">
                                    <span>{{d.judul}}</span>
                                </td>
                                <td class="p-4 justify-center items-center text-center">
                                    <span>{{d.link}}</span>
                                </td>
                                <td class="p-4 justify-center items-center text-center">
                                    <span>
                                        {{d.deskripsi}}
                                    </span>
                                </td>
                                <td class="p-4 justify-center items-center text-center">
                                    <div class="flex items-center justify-center">
                                        <i class="fas fa-edit px-1 hover:text-green-500"></i>
                                        <i v-on:click="del(`${d.id}`,`${token}`)" class="fas fa-trash-alt px-1 hover:text-red-500"></i>
                                    </div>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
        <div class="md:w-1/12"></div>
    </div>
</template>

<script>
import Login from './Login'

export default {
    name: 'Admin',
    components: {
        Login
    },
    data() {
        return {
            token: '',
            loading: true,
            data: []
        }
    },
    methods: {
        getTokenId(to) {
            this.token = to
            localStorage.setItem('token', to)
        },
        async fetchData(){
            const res = await fetch("http://127.0.0.1:8000/api/content")
            const data = await res.json()
            return data
        },
        async del(i,t){
            if(confirm("yakin ingin menghapusnya?")){
                console.log(t)
                const req = {
                    method: "DELETE",
                    headers: {
                        "Accept": "application/json",
                        "Authorization": "Bearer " + t
                    }
                }

                const res = await fetch("http://127.0.0.1:8000/api/content/" + i, req)
                const d = await res.json()
                location.reload()
                
            }
        },
        async logout(){
            const req = {
                method: "GET",
                headers: {
                    "Accept": "application/json",
                    "Content-Type": "application/json",
                    "Authorization": "Bearer " + this.token
                }
            }
            await fetch("http://127.0.0.1:8000/api/logout", req)
            this.token = ''
            localStorage.removeItem('token')
            location.reload()
        }
    },
    async created() {
        const d =  await this.fetchData()
        this.token = localStorage.getItem('token') || ''
        this.data = d.data
        this.loading = false
    }
}
</script>