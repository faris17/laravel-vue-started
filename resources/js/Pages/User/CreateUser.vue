<template>

    <Head title="Create User" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Create Users</h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="container p-5">
                        <Link href="/users" class="btn btn-primary mb-2">List User</Link>
                        <div class="mt-3 col-md-5">
                            <form @submit.prevent="form.post('/users')">
                                <div class="mb-3">
                                    <label for="exampleFormControlInput1" class="form-label">Name</label>
                                    <input type="text" name="name" class="form-control" id="exampleFormControlInput1"
                                        placeholder="Name" v-model="form.name">
                                </div>
                                <div class="mb-3">
                                    <label for="exampleFormControlInput1" class="form-label">Email</label>
                                    <input type="email" name="email" class="form-control" id="exampleFormControlInput1"
                                        placeholder="name@example.com" v-model="form.email">
                                </div>
                                <div class="mb-3">
                                    <label for="exampleFormControlInput1" class="form-label">Password</label>
                                    <input type="password" name="password" class="form-control"
                                        id="exampleFormControlInput1" v-model="form.password">
                                </div>
                                <div>
                                    <button type="submit" class="btn btn-outline-primary">
                                        Save
                                    </button>
                                </div>
                            </form>
                        </div>
                    </div>

                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import {Head, Link, useForm} from '@inertiajs/inertia-vue3';

const form = useForm({
    name : '',
    email: '',
    password: ''
});

</script>

