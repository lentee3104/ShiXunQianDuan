<script setup lang="ts">
import { createRouter, useRouter } from 'vue-router';
import Bottom from '@/Components_single/Bottom.vue';
import {useBusinessStore} from "@/store/BusinessList";


const router = useRouter();

const businessStore = useBusinessStore()
const businessList = businessStore.businessList
console.log(businessList)

const toBusinessInfo = (businessList:any) => {
  router.push({
    name: "BusinessInfo",
    query: { businessId: businessList[0].businessId },
  });
};



</script>

<template>
  <head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>饿了么 商家列表</title>
  </head>
  <div class="w=full h-full">
    <!--header部分-->
    <header class="w-full h-14 bg-[#0097FFFF] text-white text-3xl fixed left-0 top-0 z-50 font-bold
    flex justify-center items-center">
      <p>商家列表</p>
    </header>

    <!--商家列表部分-->
    <ul class="w-full mt-18">
      <li v-for="business in businessList" :key="business.businessId" class="w-full p-2 select-none flex items-center cursor-pointer border-solid border-b border-gray-300" @click="toBusinessInfo(businessList)">
        <div class="relative items-center">
          <img class="w-20 h-20" :src="business.businessImg">
        </div>
        <div class="ml-5">
          <h3 class="el-text--primary text-gray-600 font-semibold leading-relaxed">{{ business.businessName }}</h3>
          <p class="text-sm text-gray-500 font-medium leading-relaxed mt-1">&#165;{{ business.starPrice}}起送 | &#165;{{ business.deliveryPrice }}配送</p>
          <p class="text-sm text-gray-500 font-medium leading-relaxed mt-1">{{ business.businessExplain }}</p>
        </div>
      </li>

      <!--      <li class="w-full p-2 select-none flex items-center cursor-pointer border-solid border-b border-gray-300 " onclick="location.href='businessInfo.html'">-->
      <!--        <div class="relative items-center">-->
      <!--          <img class="w-20 h-20" src="/src/assets/img/sj02.png">-->
      <!--        </div>-->
      <!--        <div class="ml-5">-->
      <!--          <h3 class="el-text&#45;&#45;primary text-gray-600 font-semibold leading-relaxed ">小锅饭豆腐馆（全运店）</h3>-->
      <!--          <p class="text-sm text-gray-500 font-medium leading-relaxed mt-1">&#165;15起送 | &#165;3配送</p>-->
      <!--          <p class="text-sm text-gray-500 font-medium leading-relaxed mt-1">特色美食</p>-->
      <!--        </div>-->
      <!--      </li>-->

      <!--      <li class="w-full p-2 select-none flex items-center cursor-pointer border-solid border-b border-gray-300 " onclick="location.href='businessInfo.html'">-->
      <!--        <div class="relative items-center">-->
      <!--          <img class="w-20 h-20" src="/src/assets/img/sj03.png">-->
      <!--        </div>-->
      <!--        <div class="ml-5">-->
      <!--          <h3 class="el-text&#45;&#45;primary text-gray-600 font-semibold leading-relaxed ">麦当劳麦乐送（全运路店）</h3>-->
      <!--          <p class="text-sm text-gray-500 font-medium leading-relaxed mt-1">&#165;15起送 | &#165;3配送</p>-->
      <!--          <p class="text-sm text-gray-500 font-medium leading-relaxed mt-1">汉堡薯条</p>-->
      <!--        </div>-->
      <!--      </li>-->

      <!--      <li class="w-full p-2 select-none flex items-center cursor-pointer border-solid border-b border-gray-300 " onclick="location.href='businessInfo.html'">-->
      <!--        <div class="relative items-center">-->
      <!--          <img class="w-20 h-20" src="/src/assets/img/sj04.png">-->
      <!--          &lt;!&ndash;<div class="w-10 h-10 bg-red-600 text-white text-xl rounded-full flex justify-center items-center absolute -right-4 -top-3">1</div>&ndash;&gt;-->
      <!--        </div>-->
      <!--        <div class="ml-5">-->
      <!--          <h3 class="text-lg text-gray-600 font-semibold leading-relaxed ">米村拌饭（浑南店）</h3>-->
      <!--          <p class="text-sm text-gray-500 font-medium leading-relaxed mt-1">&#165;15起送 | &#165;3配送</p>-->
      <!--          <p class="text-sm text-gray-500 font-medium leading-relaxed mt-1">各种炒菜拌饭</p>-->
      <!--        </div>-->
      <!--      </li>-->

      <!--      <li class="w-full p-2 select-none flex items-center cursor-pointer border-solid border-b border-gray-300 " onclick="location.href='businessInfo.html'">-->
      <!--        <div class="relative items-center">-->
      <!--          <img class="w-20 h-20" src="/src/assets/img/sj05.png">-->
      <!--          &lt;!&ndash;<div class="w-10 h-10 bg-red-600 text-white text-xl rounded-full flex justify-center items-center absolute -right-4 -top-3">1</div>&ndash;&gt;-->
      <!--        </div>-->
      <!--        <div class="ml-5">-->
      <!--          <h3 class="el-text&#45;&#45;primary text-gray-600 font-semibold leading-relaxed ">申记串道（中海康城店）</h3>-->
      <!--          <p class="text-sm text-gray-500 font-medium leading-relaxed mt-1">&#165;15起送 | &#165;3配送</p>-->
      <!--          <p class="text-sm text-gray-500 font-medium leading-relaxed mt-1">烤串炸串</p>-->
      <!--        </div>-->
      <!--      </li>-->

      <!--      <li class="w-full p-2 select-none flex items-center cursor-pointer border-solid border-b border-gray-300 " onclick="location.href='businessInfo.html'">-->
      <!--        <div class="relative items-center">-->
      <!--          <img class="w-20 h-20" src="/src/assets/img/sj06.png">-->
      <!--          &lt;!&ndash;<div class="w-10 h-10 bg-red-600 text-white text-xl rounded-full flex justify-center items-center absolute -right-4 -top-3">1</div>&ndash;&gt;-->
      <!--        </div>-->
      <!--        <div class="ml-5">-->
      <!--          <h3 class="el-text&#45;&#45;primary text-gray-600 font-semibold leading-relaxed ">半亩良田排骨米饭</h3>-->
      <!--          <p class="text-sm text-gray-500 font-medium leading-relaxed mt-1">&#165;15起送 | &#165;3配送</p>-->
      <!--          <p class="text-sm text-gray-500 font-medium leading-relaxed mt-1">排骨米饭套餐</p>-->
      <!--        </div>-->
      <!--      </li>-->

      <!--      <li class="w-full p-2 select-none flex items-center cursor-pointer border-solid border-b border-gray-300 " onclick="location.href='businessInfo.html'">-->
      <!--        <div class="relative items-center">-->
      <!--          <img class="w-20 h-20" src="/src/assets/img/sj07.png">-->
      <!--          &lt;!&ndash;<div class="w-10 h-10 bg-red-600 text-white text-xl rounded-full flex justify-center items-center absolute -right-4 -top-3">1</div>&ndash;&gt;-->
      <!--        </div>-->
      <!--        <div class="ml-5">-->
      <!--          <h3 class="el-text&#45;&#45;primary text-gray-600 font-semibold leading-relaxed ">茶兮鲜果饮品（国际软件园店）</h3>-->
      <!--          <p class="text-sm text-gray-500 font-medium leading-relaxed mt-1">&#165;15起送 | &#165;3配送</p>-->
      <!--          <p class="text-sm text-gray-500 font-medium leading-relaxed mt-1">甜品饮品</p>-->
      <!--        </div>-->
      <!--      </li>-->

      <!--      <li class="w-full p-2 select-none flex items-center cursor-pointer border-solid border-b border-gray-300 " onclick="location.href='businessInfo.html'">-->
      <!--        <div class="relative items-center">-->
      <!--          <img class="w-20 h-20" src="/src/assets/img/sj08.png">-->
      <!--          &lt;!&ndash;<div class="w-10 h-10 bg-red-600 text-white text-xl rounded-full flex justify-center items-center absolute -right-4 -top-3">1</div>&ndash;&gt;-->
      <!--        </div>-->
      <!--        <div class="ml-5">-->
      <!--          <h3 class="el-text&#45;&#45;primary text-gray-600 font-semibold leading-relaxed ">唯一水果捞（软件园E18店）</h3>-->
      <!--          <p class="text-sm text-gray-500 font-medium leading-relaxed mt-1">&#165;15起送 | &#165;3配送</p>-->
      <!--          <p class="text-sm text-gray-500 font-medium leading-relaxed mt-1">新鲜水果</p>-->
      <!--        </div>-->
      <!--      </li>-->

      <!--      <li class="w-full p-2 mb-24 select-none flex items-center cursor-pointer border-solid border-b border-gray-300 " onclick="location.href='businessInfo.html'">-->
      <!--        <div class="relative items-center">-->
      <!--          <img class="w-20 h-20" src="/src/assets/img/sj09.png">-->
      <!--          &lt;!&ndash;<div class="w-10 h-10 bg-red-600 text-white text-xl rounded-full flex justify-center items-center absolute -right-4 -top-3">1</div>&ndash;&gt;-->
      <!--        </div>-->
      <!--        <div class="ml-5">-->
      <!--          <h3 class="el-text&#45;&#45;primary text-gray-600 font-semibold leading-relaxed ">满园春饼（全运路店）</h3>-->
      <!--          <p class="text-sm text-gray-500 font-medium leading-relaxed mt-1">&#165;15起送 | &#165;3配送</p>-->
      <!--          <p class="text-sm text-gray-500 font-medium leading-relaxed mt-1">各种春饼</p>-->
      <!--        </div>-->
      <!--      </li>-->
    </ul>

    <!--底部菜单部分-->
    <Bottom></Bottom>

  </div>
</template>

<style scoped>

</style>