<script setup>
import { Link } from '@inertiajs/vue3';
import { defineProps } from 'vue';

const {hidden} = defineProps (['hidden'])
</script>

<template>

    <div class="main-nav">
        <Link :href="route('dashboard')" :active="route().current('dashboard')">
            <i class="fa fa-home"></i> <span :hidden="hidden">Dashboard</span>
        </Link>
        <Link :href="route('clients')" :active="route().current('clients')">
            <i class="fa-solid fa-users"></i> <span :hidden="hidden">Clients</span>
        </Link>
        <Link :href="route('profile.edit')" :active="route().current('clients')">
            <i class="fa-solid fa-user"></i> <span :hidden="hidden">Profile</span>
        </Link>
        <Link :href="route('logout')" method="post" >
            <i class="fa-solid fa-right-from-bracket"></i> <span :hidden="hidden">Logout</span>
        </Link>

    </div>

</template>
