<template>

    <Head title="Create Community" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                All Communities
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div
                    class="p-6 bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <!-- https://tailwindcomponents.com/component/list-order-product -->
                    <div class="bg-white rounded-md w-full">
                        <div class="flex items-center justify-end">
                            <div class="flex items-center justify-between">
                                <div class="lg:ml-40 ml-10 space-x-8">
                                    <Link
                                        :href="route('communities.create')"
                                        class="bg-indigo-600 px-4 py-2 rounded-md text-white font-semibold tracking-wide cursor-pointer">
                                    Create
                                    </Link>
                                </div>
                            </div>
                        </div>
                        <div>
                            <div
                                class="-mx-4 sm:-mx-8 px-4 sm:px-8 py-4 overflow-x-auto">
                                <div
                                    class="inline-block min-w-full shadow rounded-lg overflow-hidden">
                                    <table class="min-w-full leading-normal">
                                        <thead>
                                            <tr>
                                                <th
                                                    class="px-5 py-3 border-b-2 border-gray-200 bg-gray-100 text-left text-xs font-semibold text-gray-600 uppercase tracking-wider">
                                                    Name
                                                </th>
                                                <th
                                                    class="px-5 py-3 border-b-2 border-gray-200 bg-gray-100 text-left text-xs font-semibold text-gray-600 uppercase tracking-wider">
                                                    Slug
                                                </th>
                                                <th
                                                    class="px-5 py-3 border-b-2 border-gray-200 bg-gray-100 text-left text-xs font-semibold text-gray-600 uppercase tracking-wider">
                                                </th>
                                            </tr>
                                        </thead>
                                        <tbody>
                                            <tr
                                                v-for="community in communities.data"
                                                :key="community.id">
                                                <td
                                                    class="px-5 py-5 border-b border-gray-200 bg-white text-sm">
                                                    <div
                                                        class="flex items-center">
                                                        <p
                                                            class="text-gray-900 whitespace-no-wrap">
                                                            {{ community.name }}
                                                        </p>
                                                    </div>
                                                </td>
                                                <td
                                                    class="px-5 py-5 border-b border-gray-200 bg-white text-sm">
                                                    <p
                                                        class="text-gray-900 whitespace-no-wrap">
                                                        {{ community.slug }}
                                                    </p>
                                                </td>
                                                <td
                                                    class="px-5 py-5 border-b border-gray-200 bg-white text-sm">
                                                    <Link
                                                        :href="route('communities.edit', community.id)"
                                                        class="text-blue-400 underline">Edit</Link>

                                                    <Link
                                                        :href="route('communities.destroy', community.id)"
                                                        method="delete" as="button" type="button"
                                                        class="text-red-400 underline ml-2">Delete</Link>
                                                </td>
                                            </tr>
                                        </tbody>
                                    </table>

                                    <div class="m-2 p-2">
                                        <Pagination :links="communities.links" />
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>

<script setup>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import Pagination from '@/Components/Pagination.vue';

import { Head, Link } from "@inertiajs/inertia-vue3";

defineProps({
    communities: Object,
});
</script>
