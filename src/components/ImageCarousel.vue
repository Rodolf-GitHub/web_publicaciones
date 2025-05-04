<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

// Importamos las imágenes correctamente
const images = ref([
  new URL('../assets/images/img1.jpg', import.meta.url).href,
  new URL('../assets/images/img2.jpg', import.meta.url).href,
  new URL('../assets/images/img3.jpg', import.meta.url).href,
  new URL('../assets/images/img4.jpg', import.meta.url).href,
  new URL('../assets/images/img5.jpg', import.meta.url).href,
  new URL('../assets/images/img6.jpg', import.meta.url).href,
  new URL('../assets/images/img7.jpg', import.meta.url).href,
  new URL('../assets/images/img8.jpg', import.meta.url).href,
  new URL('../assets/images/img9.jpg', import.meta.url).href,
  new URL('../assets/images/img10.jpg', import.meta.url).href,
  new URL('../assets/images/img11.jpg', import.meta.url).href,
])

const currentIndex = ref(0)

const next = () => {
  currentIndex.value = (currentIndex.value + 1) % images.value.length
}

const prev = () => {
  currentIndex.value = currentIndex.value === 0 ? images.value.length - 1 : currentIndex.value - 1
}

let interval: number

// Auto-play con limpieza
onMounted(() => {
  interval = setInterval(next, 5000) // Cambia imagen cada 5 segundos
})

// Limpiar el intervalo cuando el componente se desmonta
onUnmounted(() => {
  if (interval) {
    clearInterval(interval)
  }
})
</script>

<template>
  <div class="relative w-full h-full overflow-hidden">
    <!-- Imágenes -->
    <div class="relative w-full h-full">
      <transition-group name="fade">
        <img
          v-for="(image, index) in images"
          :key="image"
          :src="image"
          :alt="`Imagen ${index + 1}`"
          class="absolute inset-0 w-full h-full object-cover transition-opacity duration-500"
          :class="{ 'opacity-0': currentIndex !== index }"
          loading="lazy"
        />
      </transition-group>
      <div
        class="absolute inset-0 bg-gradient-to-b md:bg-gradient-to-r from-transparent via-transparent to-purple-900/40"
      ></div>
    </div>

    <!-- Controles -->
    <div class="absolute inset-0 flex items-center justify-between p-4">
      <button
        @click="prev"
        class="p-2 rounded-full bg-black/30 text-white hover:bg-black/50 transition-colors"
      >
        ❮
      </button>
      <button
        @click="next"
        class="p-2 rounded-full bg-black/30 text-white hover:bg-black/50 transition-colors"
      >
        ❯
      </button>
    </div>

    <!-- Indicadores -->
    <div class="absolute bottom-4 left-1/2 transform -translate-x-1/2 flex space-x-2">
      <button
        v-for="(_, index) in images"
        :key="index"
        @click="currentIndex = index"
        class="w-2 h-2 rounded-full transition-colors"
        :class="currentIndex === index ? 'bg-white' : 'bg-white/50'"
      ></button>
    </div>
  </div>
</template>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
