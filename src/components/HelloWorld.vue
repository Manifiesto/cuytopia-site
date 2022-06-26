<script setup>

import { ref, onMounted } from 'vue'

const isMetamaskSupported = ref(false)
const address = ref('')

onMounted(() => {
  isMetamaskSupported.value = typeof window.ethereum !== 'undefined'
  // isMetamaskSupported.value = false
})


async function connect() {
  // console.log('connect ...')
  
  const accounts = await window.ethereum.request({ method: 'eth_requestAccounts' })
  // console.log({ accounts })

  address.value = accounts[0]
}

</script>

<template>
  <h1>Cuytopia</h1>

  <button v-if="isMetamaskSupported" @click="connect">Sign In with Metamask</button>

  <p v-else>Install Metamask extension</p>

  <p>{{ address.substring(0, 8) + '...' }}</p>
</template>

