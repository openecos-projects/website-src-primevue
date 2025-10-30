<template>
    <div class="bg-surface-0 dark:bg-surface-900 px-6 py-20 md:px-12 lg:px-20 flex flex-col gap-8 max-w-400 m-auto">
        <div class="flex flex-col gap-8">
            <div class="flex flex-col gap-4">
                <div class="text-surface-900 dark:text-surface-0 text-4xl font-semibold leading-tight">订阅消息</div>
                <div class="text-surface-600 dark:text-surface-400 text-lg leading-tight">获取ECOS团队的最新发展动态</div>
            </div>
            <div class="md:w-[402px] flex items-center gap-4 bg-surface-0 dark:bg-surface-900 border border-surface-200 dark:border-surface-700 rounded-[33px] py-2 pl-4 pr-2">
                <InputText
                    class="flex-1 border-0! bg-transparent! leading-normal! shadow-none! p-0! text-surface-400! dark:text-surface-500!"
                    placeholder="输入您的电子邮箱" />
                <Button
                    class="px-3! py-2! font-medium! bg-logo-o border-logo-o rounded-4xl!"
                    label="现在加入" />
            </div>
        </div>
        <div class="h-px bg-surface-200 dark:bg-surface-700"></div>
        <div class="grid lg:grid-cols-5 md:grid-cols-3 grid-cols-1 gap-8">
            <div class="flex flex-col gap-8">
                <div class="flex flex-col gap-4">
                    <div class="flex items-center gap-4">
                        <img class="w-8 h-8" src="https://raw.githubusercontent.com/openecos-projects/website-res/main/img/web/ecos/logo.svg">
                        <span class="text-surface-900 dark:text-surface-0 text-lg font-semibold leading-tight">ECOS团队</span>
                    </div>
                    <div class="text-surface-600 dark:text-surface-400 leading-normal">
                        [构建]一个开源开放、合作共享的芯片生态系统
                    </div>
                </div>
                <div class="flex gap-2">
                    <a
                        v-for="obj in footerIconArr"
                        :key="obj"
                        tabindex="0"
                        :class="[
                            obj.link.data !== '' ? 'cursor-pointer pointer-events-auto' : 'cursor-not-allowed pointer-events-none',
                            'w-8 h-8 bg-surface-0 dark:bg-surface-900 border border-surface-50 dark:border-surface-800 hover:opacity-75 transition-colors flex items-center justify-center rounded-full'
                        ]"
                        :href="obj.link.data"
                        :target="obj.link.type">
                        <span
                            v-if="obj.type === 'material'"
                            class="material-icons text-surface-900 dark:text-surface-0 text-xl!">{{ obj.data }}
                        </span>
                        <i
                            v-else-if="obj.type === 'prime'"
                            :class="`pi pi-${obj.data} text-surface-900 dark:text-surface-0`">
                        </i>
                        <i
                            v-else-if="obj.type === 'fontawesome'"
                            :class="`fa-brands fa-${obj.data} text-surface-900 dark:text-surface-0`">
                        </i>
                    </a>
                </div>
            </div>
            <div
                v-for="arr in footerListArr"
                :key="arr"
                tabindex="0"
                class="flex flex-col gap-6">
                <div class="text-surface-900 dark:text-surface-0 text-lg font-medium leading-tight">{{ arr.name_zh }}</div>
                <div class="flex flex-col gap-4">
                    <a
                        v-for="obj in arr.data_zh"
                        :key="obj"
                        tabIndex="0"
                        class="text-surface-700 dark:text-surface-400 text-logo-hover leading-tight transition-colors cursor-pointer">
                        {{ obj.name }}
                    </a>
                </div>
            </div>
        </div>
        <div class="py-6 px-0 flex flex-wrap items-center justify-between w-full border-t border-surface-200 dark:border-surface-700 gap-4">
            <span class="text-base text-surface-900 dark:text-surface-0 font-normal leading-normal">Copyright © 2025 ECOS Team</span>
        </div>
    </div>
</template>

<script setup>
    import { ref } from "vue";

    import icon from "../json/icon.json";
    import list from "../json/list.json";

    let footerIconArr = ref(icon);
    let footerListArr = ref(list);
</script>
