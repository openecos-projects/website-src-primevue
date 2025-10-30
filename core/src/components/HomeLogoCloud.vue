<template>
    <div class="bg-surface-0 dark:bg-surface-900 py-20 md:px-12 lg:px-20 max-w-400 m-auto">
        <div class="flex flex-col items-center gap-4">
            <h1 class="text-surface-900 dark:text-surface-0 mb-4 font-bold text-4xl text-center leading-normal">生态伙伴</h1>
            <h3 class="text-surface-600 dark:text-surface-200 mb-12 text-xl text-center leading-normal">团队的开源项目与服务受到几十家单位机构的信任与应用</h3>
        </div>
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-6 gap-2">
            <div
                v-for="obj in logoArr"
                :key="obj"
                tabindex="0"
                class="flex items-center bg-surface-0 dark:bg-surface-900 justify-center border border-surface-100 dark:border-surface-800">
                <div class="flex items-center justify-center px-5 py-3 relative gap-3">
                    <Image :src="obj.logo" width="100" />
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
    import { ref } from "vue";
    import logo from "../json/logo.json";

    let logoArr = ref(logo);
</script>
