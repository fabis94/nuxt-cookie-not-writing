<template>
  <div>
    <NuxtWelcome />
  </div>
</template>
<script setup lang="ts">

const defineCookie = (name: string) => {
  useCookie(name, {
    default: () => 'test-value',
    maxAge: 60 * 60 * 24 * 7,
  })
}

if (process.client) {
  defineCookie('xx-test-csr-cookie')
}
defineCookie('xx-test-universal-cookie')

</script>