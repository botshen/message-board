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
    content: '新年快乐！祝大家2024年顺顺利利。🎉',
    createdAt: '2024-01-01',
    avatar: 'https://via.placeholder.com/150',
    comment: '团队祝福。',
    creator: '管理员',
    comments: [
      {
        id: 1,
        content: '团队祝福。',
        createdAt: '2024-01-01',
        avatar: 'https://via.placeholder.com/150',
        creator: '管理员',
      },
    ],
  },
  {
    id: 2,
    content: '我爱这个平台！它非常有趣和有趣。😄',
    createdAt: '2024-01-05',
    avatar: 'https://via.placeholder.com/150',
    comment: '继续做出伟大的工作！',
    creator: '约翰·多伊',
    comments: [
      {
        id: 1,
        content: '继续做出伟大的工作！',
        createdAt: '2024-01-05',
        avatar: 'https://via.placeholder.com/150',
        creator: '约翰·多伊',
      },
    ],
  },
  {
    id: 3,
    content: '这是一个非常棒的社区。我已经学到了很多。🤩',
    createdAt: '2024-01-10',
    avatar: 'https://via.placeholder.com/150',
    comment: '感谢所有参与的人。',
    creator: '简·史密斯',
    comments: [
      {
        id: 1,
        content: '感谢所有参与的人。',
        createdAt: '2024-01-10',
        avatar: 'https://via.placeholder.com/150',
        creator: '简·史密斯',
      },
    ],
  },
  {
    id: 4,
    content: '这是一个非常棒的社区。我已经学到了很多。',
    createdAt: '2024-01-10',
    avatar: 'https://via.placeholder.com/150',
    comment: '感谢所有参与的人。',
    creator: '简·史密斯',
    comments: [],
  },
  {
    id: 5,
    content: '这是一个非常棒的社区。我已经学到了很多。',
    createdAt: '2024-01-10',
    avatar: 'https://via.placeholder.com/150',
    comment: '感谢所有参与的人。',
    creator: '简·史密斯',
    comments: [],
  },
  {
    id: 6,
    content: '这是一个非常棒的社区。我已经学到了很多。',
    createdAt: '2024-01-10',
    avatar: 'https://via.placeholder.com/150',
    comment: '感谢所有参与的人。',
    creator: '简·史密斯',
    comments: [{
      id: 1,
      content: '感谢所有参与的人。',
      createdAt: '2024-01-10',
      avatar: 'https://via.placeholder.com/150',
      creator: '简·史密斯',
    }],
  }
])
</script>

<template>
  <main class="mx-auto min-h-screen bg-gradient-to-b from-sky-50 via-blue-50 to-indigo-50">
    <header class="h-12 sm:h-10 sticky top-0 text-center font-bold text-xl sm:text-2xl text-blue-600 bg-blue-100/70 backdrop-blur-sm shadow-[0_2px_4px_rgba(0,0,0,0.1)] flex items-center justify-center">
      QQ 留言板 ✨
    </header>
    <section class="h-[calc(100%-48px)] sm:h-[calc(100%-40px)] p-2 sm:p-4">
      <MessageCard :messageList="messageList" />
    </section>
  </main>
</template>
