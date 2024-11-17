<script setup lang="ts">
import MessageCard from '@/components/message-card.vue';
import { ref } from 'vue';
export type Comment = {
  id: number
  content: string
  createdAt: string
  avatar: string
  creator: string
}
export type Message = {
  id: number
  content: string
  createdAt: string
  avatar: string
  comment: string
  creator: string
  comments: Comment[]
}
const messageList =ref<Message[]>([
  {
    id: 1,
    content: 'Happy New Year! Wishing everyone a prosperous 2024.',
    createdAt: '2024-01-01',
    avatar: 'https://via.placeholder.com/150',
    comment: 'Best wishes from the team.',
    creator: 'Admin',
    comments: [
      {
        id: 1,
        content: 'Best wishes from the team.',
        createdAt: '2024-01-01',
        avatar: 'https://via.placeholder.com/150',
        creator: 'Admin',
      },
    ],
  },
  {
    id: 2,
    content: 'I love this platform! It\'s so engaging and fun.',
    createdAt: '2024-01-05',
    avatar: 'https://via.placeholder.com/150',
    comment: 'Keep up the great work!',
    creator: 'John Doe',
    comments: [
      {
        id: 1,
        content: 'Keep up the great work!',
        createdAt: '2024-01-05',
        avatar: 'https://via.placeholder.com/150',
        creator: 'John Doe',
      },
    ],
  },
  {
    id: 3,
    content: 'This is an amazing community. I\'ve learned so much already.',
    createdAt: '2024-01-10',
    avatar: 'https://via.placeholder.com/150',
    comment: 'Thank you to everyone involved.',
    creator: 'Jane Smith',
    comments: [
      {
        id: 1,
        content: 'Thank you to everyone involved.',
        createdAt: '2024-01-10',
        avatar: 'https://via.placeholder.com/150',
        creator: 'Jane Smith',
      },
    ],
  },
  {
    id: 4,
    content: 'This is an amazing community. I\'ve learned so much already.',
    createdAt: '2024-01-10',
    avatar: 'https://via.placeholder.com/150',
    comment: 'Thank you to everyone involved.',
    creator: 'Jane Smith',
    comments: [],
  },
  {
    id: 5,
    content: 'This is an amazing community. I\'ve learned so much already.',
    createdAt: '2024-01-10',
    avatar: 'https://via.placeholder.com/150',
    comment: 'Thank you to everyone involved.',
    creator: 'Jane Smith',
    comments: [],
  },
  {
    id: 6,
    content: 'This is an amazing community. I\'ve learned so much already.',
    createdAt: '2024-01-10',
    avatar: 'https://via.placeholder.com/150',
    comment: 'Thank you to everyone involved.',
    creator: 'Jane Smith',
    comments: [{
      id: 1,
      content: 'Thank you to everyone involved.',
      createdAt: '2024-01-10',
      avatar: 'https://via.placeholder.com/150',
      creator: 'Jane Smith',
    }],
  }
])
</script>

<template>
  <main class="mx-auto min-h-screen bg-gradient-to-b from-pink-200 via-purple-200 to-blue-200">
    <header class="h-12 sm:h-10 sticky top-0 text-center font-bold text-xl sm:text-2xl text-purple-600 bg-yellow-100   shadow-md flex items-center justify-center">
      QQ 留言板 ✨
    </header>
    <section class="h-[calc(100%-48px)] sm:h-[calc(100%-40px)] p-2 sm:p-4">
      <MessageCard :messageList="messageList" />
    </section>
  </main>
</template>
