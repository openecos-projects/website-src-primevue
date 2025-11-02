<template>
    <div class="resize-container-4 h-full bg-surface-0 dark:bg-surface-90 shadow-2xs dark:shadow-surface-800 max-w-400 m-auto">
        <div class="bg-surface-00 dark:bg-surface-900 py-4 px-12 flex items-center justify-between relative">
            <div class="flex items-center gap-4 py-2">
                <img class="w-8 h-8" src="https://raw.githubusercontent.com/openecos-projects/website-res/main/img/web/ecos/logo.svg">
                <span class="text-xl font-semibold text-surface-900 dark:text-surface-0 w-32">ECOS团队</span>
            </div>
            <a
                v-styleclass="{
                    selector: '@next',
                    enterFromClass: 'hidden',
                    enterActiveClass: 'animate-fadein',
                    leaveToClass: 'hidden',
                    leaveActiveClass: 'animate-fadeout',
                    hideOnOutsideClick: true,
                    resizeSelector: '.resize-container-4',
                    hideOnResize: true
                }"
                class="cursor-pointer block lg:hidden text-surface-900 mt-1">
                <i class="pi pi-bars text-2xl!" />
            </a>
            <div class="items-center grow justify-between hidden lg:flex absolute lg:static w-full left-0 top-full px-12 lg:px-0 z-50 shadow lg:shadow-none">
                <ul class="list-none p-0 py-4 lg:py-0 m-0 flex grow lg:items-center lg:justify-center text-surface-900 dark:text-surface-0 select-none flex-col lg:flex-row cursor-pointer">
                    <li>
                        <a
                            class="flex px-0 lg:px-5 py-4 text-logo-hover font-medium transition-colors duration-150 cursor-pointer"
                            href="/">
                            <span>网站首页</span>
                        </a>
                    </li>
                    <!-- <li
                        v-for="arr in navbarListArr"
                        :key="arr"
                        tabindex="0">
                        <a
                            v-styleclass="{
                                selector: '@next',
                                enterFromClass: 'hidden',
                                enterActiveClass: 'animate-scalein',
                                leaveToClass: 'hidden',
                                leaveActiveClass: 'animate-fadeout',
                                hideOnOutsideClick: true
                            }"
                            class="flex px-0 lg:px-3 py-4 items-center text-logo-hover font-medium transition-colors duration-150 cursor-pointer">
                            <span>{{ arr.name_zh }}</span>
                            <i class="pi pi-chevron-down ml-auto lg:ml-4" />
                        </a>
                        <div class="lg:absolute bg-surface-0 dark:bg-surface-900 hidden origin-top left-0 top-full w-full lg:px-12 lg:py-4 lg:pb-12 lg:rounded-b-2xl rounded-2xl lg:rounded-t-none">
                            <div class="flex flex-wrap lg:p-12 p-6 w-full bg-surface-100 dark:bg-surface-800 lg:rounded-2xl">
                                <div class="w-full lg:w-6/12 mb-6 lg:mb-0 flex flex-col gap-4">
                                    <span class="block text-3xl text-surface-900 dark:text-surface-0 leading-tight">{{ arr.name_zh }}</span>
                                    <p class="leading-normal text-surface-700 dark:text-surface-400 max-w-md">{{ arr.desc_zh }}</p>
                                </div>
                                <div class="w-full lg:w-6/12">
                                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 border-b border-surface-700 pb-4 mb-4 gap-4">
                                        <div
                                            v-for="obj in arr.data_zh"
                                            :key="obj"
                                            tabindex="0"
                                            class="flex flex-col gap-2">
                                            <span class="text-surface-900 dark:text-surface-0 font-medium leading-tight">{{ obj.name }}</span>
                                            <p class="text-sm text-surface-700 dark:text-surface-400 leading-normal">{{ obj.desc }}</p>
                                        </div>
                                    </div>
                                    <div class="flex justify-end mt-4">
                                        <a class="flex items-center gap-2 text-surface-900 dark:text-surface-0 font-medium group">
                                            <span>详细内容</span>
                                            <i class="pi pi-arrow-right ml-auto group-hover:translate-x-2 transition-all duration-150" />
                                        </a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </li> -->
                </ul>
            </div>
            <div class="flex border-t lg:border-t-0 border-surface-700 lg:border-surface-800 py-4 lg:py-0 mt-4 lg:mt-0 gap-4 w-48">
                <Button class="text-logo-o text-logo-hover-none-o" type="button" @click="toggleDarkMode" text rounded>
                    <i :class="['pi ', 'pi ', { 'pi-moon': isDarkMode, 'pi-sun': !isDarkMode }]" />
                </Button>
            </div>
        </div>
    </div>
</template>

<script setup>
    import { ref } from "vue";
    import list from "../json/list.json";
    import { useLayout } from "../composables/useLayout";

    const { isDarkMode, toggleDarkMode } = useLayout();

    let navbarListArr = ref(list);
</script>
