<template>
  <custom-header @create-account="handleAccountCreate" @login="handleLogin" />

  <contact />

  <div class="flex justify-center bg-brand-gray py-10">
    <p class="text-center font-medium text-gray-800">feedbacker © 2021</p>
  </div>
</template>

<script lang="ts">
import { onMounted } from 'vue'
import Contact from './Contact.vue'
import CustomHeader from './CustomHeader.vue'
import { useRouter } from 'vue-router'

export default {
  components: {
    CustomHeader,
    Contact,
  },
  setup() {
    const router = useRouter()

    onMounted(() => {
      const token = window.localStorage.getItem('token')

      if (token) {
        router.push({ name: 'Feedbacks' })
      }
    })

    function handleLogin() {}

    function handleAccountCreate() {}

    return {
      handleLogin,
      handleAccountCreate,
    }
  },
}
</script>
