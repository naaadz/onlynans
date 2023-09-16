<template>
  <div class="container mx-auto md:flex justify-center md:gap-10">
    <nav class="flex-col py-6 gap-4 hidden md:flex">
      <img class="avatar" :src="data.user.image" alt="">
      <a v-for="navItem in data.nav" href="#" class="flex items-center text-gray-400 gap-4">
        <i class="material-icons-outlined text-3xl">{{ navItem.icon }}</i>
        <span class="font-bold text-lg">{{ navItem.label }}</span>
      </a>
    </nav>
    <main class="md:max-w-lg md:border-x md:border-gray-300">
      <div class="p-4 border-b flex justify-between items-center">
        <div class="text-lg font-bold">Home</div>
        <i class="material-icons-outlined">more_vert</i>
      </div>
      <div class="p-4 send-message border-b">
        <textarea class="w-full text-gray-400 outline-0 resize-none">Write a new post to Nan...</textarea>
        <nav class="flex gap-2 text-gray-400">
          <a href="#" class="material-icons-outlined disabled">image</a>
          <a href="#" class="material-icons-outlined">leaderboard</a>
          <a href="#" class="material-icons-outlined">extension</a>
        </nav>
      </div>
      <div class="posts flex flex-col gap-12 p-4">
        <nav class="flex gap-2 items-center">
          <a class="bg-sky-200 py-1 px-3 rounded-full" href="#">All</a>
          <a class="bg-gray-200 py-1 px-3 rounded-full" href="#"><i class="material-icons-outlined text-sm">edit</i></a>
        </nav>
        <div v-for="post in data.posts" class="post flex flex-col gap-4">
          <div class="meta-header flex items-center justify-between">
            <div class="user flex items-center gap-2">
              <img class="avatar" :src="data.user.image" alt="">
              <div class="info flex flex-col">
                <div class="title flex items-center gap-1">
                  <span class="font-bold text-md">{{ data.user.title }}</span>
                  <i class="material-icons-outlined text-sm">verified</i>
                </div>
                <div class="name text-gray-400 text-sm">{{ data.user.name }}</div>
              </div>
            </div>
            <div class="post-stats flex flex-col items-end text-gray-400 text-sm">
              <div class="flex items-center gap-2">
                <span>{{ post.time }}</span>
                <i class="material-icons-outlined">more_horiz</i>
              </div>
              <div class="flex items-center gap-1">
                <span>${{ post.price }}</span>
                <i class="material-icons-outlined text-sm">lock</i>
              </div>
            </div>
          </div>
          <div class="post-content" v-html="post.text" />
          <img v-for="image in post.images" :src="image" alt="">
          <div class="meta-footer flex justify-between text-gray-400">
            <div class="flex gap-2">
              <a href="#" class="material-icons-outlined">favorite</a>
              <a href="#" class="material-icons-outlined">help</a>
              <a href="#" class="material-icons-outlined">monetization_on</a>
            </div>
            <div>
              <a href="#" class="material-icons-outlined">bookmarks</a>
            </div>
          </div>
        </div>
      </div>
    </main>
    <aside class="md:max-w-sm flex flex-col gap-4 py-8">
      <input class="border border-gray-300 rounded-lg py-2 px-4 w-full" type="text" placeholder="Search posts">
      <div class="flex justify-between text-gray-400">
        <span>Suggestions</span>
        <div class="flex gap-2">
          <a href="#" class="material-icons-outlined">label_off</a>
          <a href="#" class="material-icons-outlined">autorenew</a>
          <a href="#" class="material-icons-outlined disabled">arrow_back_ios</a>
          <a href="#" class="material-icons-outlined">arrow_forward_ios</a>
        </div>
      </div>
      <img v-for="image in data.asideImages" :src="image" alt="">
      <hr>
      <footer class="flex justify-center gap-2 text-xs">
        <a href="#">Privacy</a>
        <span>•</span>
        <a href="#">Cookie Notice</a>
        <span>•</span>
        <a href="#">Terms of Services</a>
      </footer>
    </aside>
  </div>
</template>

<script setup>
import data from '@/data/data.json'


</script>

<style scoped>

</style>
