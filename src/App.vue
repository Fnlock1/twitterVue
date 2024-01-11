<script setup>
import Banner from "@/components/Banner/index.vue";
</script>

<template>
  <!--    left 左边的选择栏目-->
    <div class="center">
        <Banner></Banner>
        <div class="p-2 text-white">
            <RouterView/>
        </div>
    </div>
</template>

<style scoped>
.center {
    margin: 0 auto;
    width: 80%;
    /*background: white;*/
    min-height: 100vh;
    overflow: hidden;
    display: flex;
}
</style>
