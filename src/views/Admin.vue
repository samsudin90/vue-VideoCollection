<template>
    <div class="md:flex md:flex-row">
        <div class="w-1/12"></div>
        <div class="w-5/6">
            <button class="m-4 -mb-1 p-2 border-2 rounded bg-indigo-500 text-white text-xl focus:outline-none font-semibold outline-none focus:bg-indigo-800">tambah</button>
            <div class="overflow-x-auto">
                <div class="w-full bg-gray-100 justify-center items-center overflow-hidden py-2 rounded">
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
                            <tr class="border-b border-gray-200 hover:bg-gray-100 p-4 mx-2">
                                <td class="p-4 justify-center items-center text-center">
                                    <span>ini judul video</span>
                                </td>
                                <td class="p-4 justify-center items-center text-center">
                                    <span>www.youtube.com/embed/yYabf3kab</span>
                                </td>
                                <td class="p-4 justify-center items-center text-center">
                                    <span>Lorem ipsum dolor sit amet consectetur adipisicing elit. Deleniti, dolorem ut quis nam quo est eius quos fugit dolore dicta, tempora odio magnam mollitia vel obcaecati temporibus delectus, a aut.
                                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Suscipit tenetur inventore, amet similique alias nulla laborum a iure possimus neque? Ab dolore voluptatibus suscipit placeat ad, dolor voluptatem provident totam.
                                    </span>
                                </td>
                                <td class="p-4 justify-center items-center text-center">
                                    <div class="flex items-center justify-center">
                                        <i class="fas fa-edit px-1 hover:text-green-500"></i>
                                        <i class="fas fa-trash-alt px-1 hover:text-red-500"></i>
                                    </div>
                                </td>
                            </tr>
                            <tr class="border-b border-gray-200 hover:bg-gray-100 p-4 mx-2">
                                <td class="p-4 justify-center items-center text-center">
                                    <span>ini judul video</span>
                                </td>
                                <td class="p-4 justify-center items-center text-center">
                                    <span>www.youtube.com/embed/yYabf3kab</span>
                                </td>
                                <td class="p-4 justify-center items-center text-center">
                                    <span>Lorem ipsum dolor sit amet consectetur adipisicing elit. Deleniti, dolorem ut quis nam quo est eius quos fugit dolore dicta, tempora odio magnam mollitia vel obcaecati temporibus delectus, a aut.
                                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Suscipit tenetur inventore, amet similique alias nulla laborum a iure possimus neque? Ab dolore voluptatibus suscipit placeat ad, dolor voluptatem provident totam.
                                    </span>
                                </td>
                                <td class="p-4 justify-center items-center text-center">
                                    <div class="flex items-center justify-center">
                                        <i class="fas fa-edit px-1 hover:text-green-500"></i>
                                        <i class="fas fa-trash-alt px-1 hover:text-red-500"></i>
                                    </div>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
        <div class="w-1/12"></div>
    </div>
</template>

<script>
export default {
    name: 'Admin'
}
</script>