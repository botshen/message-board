<script setup lang="ts">
import type { Message } from '@/views/HomeView.vue';

const props = defineProps<{
  messageList: Message[]
}>()
</script>

<template>
  <div class="space-y-4 sm:space-y-6">
    <div class="p-3 sm:p-4 border-2 border-gray-200 rounded-xl shadow-[2px_2px_8px_rgba(0,0,0,0.1)] bg-gradient-to-br from-white to-gray-50 transition-all hover:shadow-[4px_4px_12px_rgba(0,0,0,0.15)]" v-for="item in props.messageList" :key="item.id">
      <div class="flex items-center mb-2">
        <img :src="item.avatar" alt="avatar" class="w-8 h-8 sm:w-10 sm:h-10 rounded-full mr-2 border-2 border-gray-200">
        <span class="text-sm sm:text-base font-bold text-gray-700">{{ item.creator }}</span>
      </div>
      <p class="text-sm sm:text-base text-gray-600">{{ item.content }}</p>
      <div class="text-xs sm:text-sm text-gray-500 mt-1">{{ item.createdAt }}</div>

      <div class="mt-3 sm:mt-4 border-t border-gray-100 pt-2" v-if="item.comments && item.comments.length">
        <div v-for="comment in item.comments" :key="comment.id" class="flex flex-col mt-2 p-2 rounded-lg bg-gradient-to-r from-gray-50 to-gray-50/50">
          <div class="flex items-center">
            <img :src="comment.avatar" alt="avatar" class="w-5 h-5 sm:w-6 sm:h-6 rounded-full mr-2 border-2 border-gray-200">
            <span class="text-xs sm:text-sm font-bold text-gray-600">{{ comment.creator }}</span>
          </div>
          <p class="text-xs sm:text-sm text-gray-600 ml-6 sm:ml-8">{{ comment.content }}</p>
          <div class="text-xs sm:text-sm text-gray-500 ml-6 sm:ml-8">{{ comment.createdAt }}</div>
        </div>
      </div>
    </div>
  </div>
</template>
