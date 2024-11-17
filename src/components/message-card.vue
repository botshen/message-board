<script setup lang="ts">
import type { Message } from '@/views/HomeView.vue';

const props = defineProps<{
  messageList: Message[]
}>()
</script>

<template>
  <div class="space-y-4 sm:space-y-10">
    <div class="p-3 sm:p-4 border-2 border-purple-400 rounded-lg shadow-lg bg-gradient-to-br from-pink-50 to-blue-50 transition-all" v-for="item in props.messageList" :key="item.id">
      <div class="flex items-center mb-2">
        <img :src="item.avatar" alt="avatar" class="w-8 h-8 sm:w-10 sm:h-10 rounded-full mr-2 border-2 border-pink-300">
        <span class="text-xs sm:text-sm font-bold text-purple-600">{{ item.creator }}</span>
      </div>
      <p class="text-xs sm:text-sm text-indigo-700">{{ item.content }}</p>
      <div class="text-[10px] sm:text-xs text-teal-600 mt-1">{{ item.createdAt }}</div>

      <div class="mt-3 sm:mt-4 border-t border-blue-200 pt-2" v-if="item.comments && item.comments.length">
        <div v-for="comment in item.comments" :key="comment.id" class="flex flex-col mt-2 p-2 rounded-lg bg-gradient-to-r from-blue-50 to-purple-50">
          <div class="flex items-center">
            <img :src="comment.avatar" alt="avatar" class="w-5 h-5 sm:w-6 sm:h-6 rounded-full mr-2 border-2 border-blue-300">
            <span class="text-[10px] sm:text-xs font-bold text-blue-600">{{ comment.creator }}</span>
          </div>
          <p class="text-[10px] sm:text-xs text-pink-600 ml-6 sm:ml-8">{{ comment.content }}</p>
          <div class="text-[10px] sm:text-xs text-teal-500 ml-6 sm:ml-8">{{ comment.createdAt }}</div>
        </div>
      </div>
    </div>
  </div>
</template>
