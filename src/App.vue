<template>
  <div class="container">
    <global-header :user="currentUser"></global-header>
    <router-view></router-view>
    <footer class="text-center py-4 text-secondary bg-light mt-6">
      <small>
        <ul>
          <li class="list-inline-item">₢ 2020 者也专栏</li>
          <li class="list-inline-item">课程</li>
          <li class="list-inline-item">文档</li>
          <li class="list-inline-item">联系</li>
          <li class="list-inline-item">更多</li>
        </ul>
      </small>
    </footer>
  </div>
</template>
<script lang="ts">
import { defineComponent, computed } from 'vue'
import GlobalHeader from '@/components/GlobalHeader.vue'
import { useStore } from 'vuex'
export default defineComponent({
  name: 'App',
  components: {
    GlobalHeader
  },
  // setup里面可以传入两个参数 第一个参数为props 第二个参数为context
  setup () {
    const store = useStore()
    const currentUser = computed(() => store.state.user)
    return {
      currentUser
    }
  }
})
</script>

<style>
</style>
