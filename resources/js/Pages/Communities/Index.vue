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
                    class="p-6 bg-white overflow-hidden shadow-sm sm:rounded-lg"
                >
                    <div class="flex justify-end">
                        <Link
                            :href="route('communities.create')"
                            class="px-4 py-2 bg-blue-400 hover:bg-blue-600 rounded text-white"
                            >New Community</Link
                        >
                    </div>

                    <!-- https://tailwind-elements.com/docs/standard/components/tables/ -->
                    <div class="flex flex-col">
                        <div class="overflow-x-auto sm:-mx-6 lg:-mx-8">
                            <div
                                class="py-2 inline-block min-w-full sm:px-6 lg:px-8"
                            >
                                <!-- Change Here -->
                                <div
                                    class="overflow-hidden shadow-md rounded-lg"
                                >
                                    <!-- Change Here -->
                                    <table class="w-full">
                                        <thead
                                            class="px-5 py-3 border-b-2 border-gray-200 bg-gray-100 text-left text-xs font-semibold text-gray-700 uppercase tracking-wider"
                                        >
                                            <tr>
                                                <th
                                                    scope="col"
                                                    class="text-sm font-medium text-gray-900 px-6 py-4 text-left"
                                                >
                                                    #
                                                </th>
                                                <th
                                                    scope="col"
                                                    class="text-sm font-medium text-gray-900 px-6 py-4 text-left"
                                                >
                                                    Name
                                                </th>
                                                <th
                                                    scope="col"
                                                    class="text-sm font-medium text-gray-900 px-6 py-4 text-left"
                                                >
                                                    Slug
                                                </th>
                                                <th
                                                    scope="col"
                                                    class="text-sm font-medium text-gray-900 px-6 py-4 text-left"
                                                ></th>
                                            </tr>
                                        </thead>
                                        <tbody>
                                            <!-- Change Here -->
                                            <tr
                                                class="border-b bg-white"
                                                v-for="community in communities"
                                                :key="community.id"
                                            >
                                                <td
                                                    class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900"
                                                >
                                                    1
                                                </td>
                                                <td
                                                    class="text-sm text-gray-900 font-light px-6 py-4 whitespace-nowrap"
                                                >
                                                    {{ community.name }}
                                                </td>
                                                <td
                                                    class="text-sm text-gray-900 font-light px-6 py-4 whitespace-nowrap"
                                                >
                                                    {{ community.slug }}
                                                </td>
                                                <th>
                                                    <a
                                                        href=""
                                                        class="text-indigo-600 underline"
                                                        >Edit</a
                                                    >
                                                </th>
                                            </tr>
                                        </tbody>
                                    </table>
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
import { Head, Link } from "@inertiajs/inertia-vue3";

defineProps({
    communities: Object,
});
</script>
