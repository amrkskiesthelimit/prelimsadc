<script setup>
import Layout from '@/Layouts/Layout.vue';
import { Head } from '@inertiajs/vue3';
</script>


<template>
    <Head title="Clients" />

    <Layout>
        <div class="">
            <div class="">
                <div class="">
                    <div class="p-6 text-gray-900">
                        <div v-for="client in clients.data" :key="client.id" style="display: inline-flex; flex-wrap: wrap;">
                            <div class="bg-gray-800 text-white m-5 p-5 rounded-lg" style="width: 300px;">
                                <img src="https://cdn-icons-png.flaticon.com/512/3135/3135715.png" alt="">
                                <b>Last Name: </b>{{ client.last_name }} <br>
                                <b>First Name: </b>{{ client.first_name }} <br>
                                <b>Address: </b>{{ client.address }} <br>
                                <b>Phone: </b>{{ client.phone }} <br>
                                <b>Level: </b>{{ client.level }}
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="mt-4 flex justify-between items-center" >
            <div class="flex items-center space-x-2" style="transform: translateY(-20px) translateX(45px);">
                <span v-if="clients.prev_page_url">
                    <a
                        :href="clients.prev_page_url"
                        @click.prevent="$inertia.visit(clients.prev_page_url)"
                        class="text-sm font-medium text-gray-100 p-5 bg-gray-900 rounded-md hover:bg-gray-300"
                    >
                        Previous
                    </a>
                </span>

                <!-- Next Page Link -->
                <span v-if="clients.next_page_url">
                    <a
                        :href="clients.next_page_url"
                        @click.prevent="$inertia.visit(clients.next_page_url)"
                        class="text-sm font-medium text-gray-100 p-5 bg-gray-900 rounded-md hover:bg-gray-300"
                    >
                        Next
                    </a>
                </span>
            </div>

</div>

    </Layout>
</template>

<script>
export default {
    props: {
        clients: Object, // Define the clients prop type as an object
    },
};
</script>
