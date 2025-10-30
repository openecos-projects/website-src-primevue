<template>
    <div class="bg-surface-0 dark:bg-surface-900 py-20 md:px-12 lg:px-20 max-w-400 m-auto">
        <div class="flex flex-col items-center gap-4">
            <h1 class="text-surface-900 dark:text-surface-0 mb-4 font-bold text-4xl text-center leading-normal">项目列表</h1>
            <h3 class="text-surface-600 dark:text-surface-200 mb-12 text-xl text-center leading-normal">{{ navbarListObj.desc_zh }}</h3>
        </div>
        <div class="grid lg:grid-cols-3 md:grid-cols-2 sm:grid-cols-2 gap-x-2 gap-y-8">
            <Card
                v-for="arr in navbarListObj.data_zh"
                :key="arr"
                tabindex="0"
                class="bg-surface-50 dark:bg-surface-950 text-surface-700 dark:text-surface-0 rounded-xl shadow-2xs dark:border dark:border-surface-800 mx-4">
                <template #title>{{ arr.name }}</template>
                <template #content>
                    <div class="flex flex-col gap-5">
                        <a
                            v-for="obj in arr.prjs"
                            :key="obj"
                            tabindex="0"
                            :href="obj.link"
                            target="_blank"
                            :class="[
                                obj.link !== '' ? 'cursor-pointer pointer-events-auto' : 'cursor-not-allowed pointer-events-none'
                            ]">
                        <Card class="dark:border dark:border-surface-800">
                            <template #content>
                                <a class="flex flex-row">
                                    <img
                                        :class="[
                                            obj.name === '' ? '' : 'w-25 h-25'
                                        ]"
                                        :src="obj.logo" />
                                    <div class="ml-4">
                                        <div class="mt-1">{{ obj.name }}</div>
                                        <div class="mt-3">{{ obj.desc }}</div>
                                    </div>
                                </a>
                            </template>
                        </Card>
                        </a>
                    </div>
                </template>
            </Card>
        </div>
    </div>
</template>

<script setup>
    import { ref } from "vue";
    import list from "../json/list.json";

    let navbarListObj = ref(list[0]);
</script>
