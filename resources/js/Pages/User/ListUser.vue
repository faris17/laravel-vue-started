<template>

    <Head title="Users" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Users</h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="container p-5">
                        <Link href="/users/create" class="btn btn-primary mb-2">Create User</Link>
                        <table class="mt-3 table table-striped">
                            <thead>
                                <th>Name</th>
                                <th>Email</th>
                                <th>Action</th>
                            </thead>
                            <tbody>
                                <tr v-for="user in users" :key="user">
                                    <td>{{ user.name }}</td>
                                    <td>{{ user.email }}</td>
                                    <td>
                                        <Link :href="`/users/${user.id}/edit`" class="btn btn-info btn-sm">Edit</Link>

                                        <Link :href="`/users/${user.id}`" method="delete" onclick="return confirm('Are you sure?')" class="ml-1 btn btn-danger btn-sm">Hapus</Link>
                                    </td>
                                </tr>
                            </tbody>
                        </table>
                    </div>

                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head } from '@inertiajs/inertia-vue3';

import { Link } from '@inertiajs/inertia-vue3';

defineProps({
    users: Object,
});
</script>

