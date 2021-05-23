<template>
    <div class="md:flex md:flex-row">
        <div class="md:w-1/12"></div>
        <div class="md:w-5/6 md:p-4 p-2">
            <iframe :src="data.link" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen class="w-full md:h-screen h-4/6">
            </iframe>
            <h3 class="pt-4 md:text-2xl text-xl font-bold">{{data.judul}}</h3>
            <p class="pt-2 text-sm">{{data.deskripsi}}</p>
        </div>
        <div class="md:w-1/12"></div>
    </div>
</template>

<script>
export default {
    name: 'Detail',
    data() {
        return {
            id: '',
            data: []
        }
    },
    methods: {
        async getDetail(){
            const res = await fetch("http://127.0.0.1:8000/api/content/" + this.id )
            const data = await res.json()
            return data
        }
    },
    async created() {
        this.id = this.$route.params.id
        const d = await this.getDetail()
        this.data = d.data
    }
}
</script>