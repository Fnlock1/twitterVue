<template>
    <div class="w-fit h-full toolBar m-3 text-white">

        <div v-for="item in tabBar"
             :key="item.name"
             :class="{'bg-gray-200 text-gray-700':item.path === $route.path}"
             class="flex items-center mt-3  active"
             @click="jump(item.path)"
        >
            <Component :is="item.icon" class="text-xl"/>
            <span class="text-xs font-bold ml-3 pt-1 pb-1">{{ item.name }}</span>
        </div>

    </div>
</template>

<script setup>
import {ref} from "vue";
import Home from "@/components/icons/Home.vue";
import Order from "@/components/icons/order.vue";
import UserIcon from "@/components/icons/UserIcon.vue";
import SettingIcon from "@/components/icons/SettingIcon.vue";
import router from "@/router/index.js";

let tabBar = ref([
    {
        name: "Home",
        path: "/",
        icon: Home
    },
    {
        name: "Order",
        path: "/order",
        icon: Order
    },
    {
        name: "User",
        path: "/user",
        icon: UserIcon
    },
    {
        name: "Setting",
        path: "/setting",
        icon: SettingIcon
    }
])

function jump(path) {
    router.push(path)
}
</script>

<style scoped>
.active {
    transition: all .2s ease;
    cursor: pointer;
    border-radius: 20px;
    padding: .3em 1em;
    user-select: none;
}

.active:hover {
    background: rgba(231, 233, 234, 0.1);
}

.toolBar {
    border-right: 1px solid rgba(231, 233, 234, 0.1);
    padding-right: 1em;
    padding-bottom: 1em;
}
</style>
