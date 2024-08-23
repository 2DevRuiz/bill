<template>
    <div
        class="flex items-start justify-center bg-white rounded-lg overflow-visible sp-0 text-slate-800 dark:bg-slate-900 dark:text-slate-100">
        <div class="mx-6 sm:mx-auto">
            <div ref="settings" class="relative">
                <div @click="
                    showMenu = !showMenu;
                showNestedMenu = false;
                "
                    class="relative flex w-52 cursor-pointer items-center justify-center gap-2 rounded-lg border border-slate-100 bg-white/75 px-1 py-1 focus:outline-none dark:border-slate-600 dark:bg-slate-900">
                    <div class="flex items-center gap-1 ">
                        <img src="https://images.unsplash.com/photo-1532170579297-281918c8ae72?w=600"
                            alt="Profile Picture" class="size-8 rounded-full object-cover md:size-10" />
                        <h2>Monica Thomas</h2>
                    </div>
                    <ChevronDownIcon class="pointer-events-none size-5" v-if="!showMenu" />
                    <ChevronUpIcon v-if="showMenu" class="pointer-events-none size-5" />
                </div>
                <div v-show="showMenu"
                    class="absolute right-0 top-16 z-10 mt-1 w-56 rounded-lg border border-slate-300 bg-white shadow-md dark:border-slate-600 dark:bg-slate-900">
                    <div class="flex flex-col divide-y divide-slate-300 dark:divide-slate-600">
                        <div class="flex flex-col py-2">
                            <a href="" :class="linkClasses">Edit Profile</a>
                        </div>
                        <div class="flex flex-col py-2">
                            <div class="relative" @click="showNestedMenu = !showNestedMenu">
                                <div :class="nestedClasses">
                                    <p>Account</p>
                                    <ChevronRightIcon class="size-6" />
                                </div>
                                <div class="absolute -left-48 top-0 flex w-48 flex-col rounded-l-lg border border-slate-300 bg-white py-2 dark:border-slate-600 dark:bg-slate-900"
                                    v-if="showNestedMenu">
                                    <a href="" :class="linkClasses">Change Email</a>
                                    <a href="" :class="linkClasses">Change Password</a>
                                    <a href="" :class="linkClasses">Backup Data</a>
                                </div>
                            </div>
                            <a href="" :class="linkClasses">Privacy</a>
                            <a href="" :class="linkClasses">Security</a>
                        </div>
                        <div class="flex flex-col py-2">
                            <a href="" :class="linkClasses">Help</a>
                            <a href="" :class="linkClasses">About</a>
                            <a href="" :class="linkClasses">Logout</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import {
    ChevronDownIcon,
    ChevronRightIcon,
    ChevronUpIcon,
} from "@heroicons/vue/24/outline";
import { ref, onMounted, onUnmounted } from "vue";

const showMenu = ref(false);
const showNestedMenu = ref(false);
const settings = ref(null);
const linkClasses = `cursor-pointer px-3 py-2 hover:bg-indigo-500 hover:text-white focus:outline-none focus:ring-2 focus:ring-indigo-500 dark:hover:bg-indigo-700 dark:focus:ring-indigo-700`;
const nestedClasses = `cursor-pointer flex gap-2 justify-between items-center px-3 py-2 hover:bg-indigo-500 hover:text-white focus:outline-none focus:ring-2 focus:ring-indigo-500 dark:hover:bg-indigo-700 dark:focus:ring-indigo-700`;

function closeDropdown(event) {
    if (!settings.value.contains(event.target)) {
        showMenu.value = false;
        showNestedMenu.value = false;
    }
}

onMounted(() => {
    window.addEventListener("click", closeDropdown);
});

onUnmounted(() => {
    window.removeEventListener("click", closeDropdown);
});
</script>