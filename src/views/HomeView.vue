<script setup lang="ts">
import ImageCarousel from '../components/ImageCarousel.vue'
</script>

<template>
  <main class="min-h-screen w-full flex flex-col md:flex-row">
    <!-- Sección del carrusel -->
    <div class="w-full h-[40vh] md:h-screen md:w-1/2 relative overflow-hidden">
      <ImageCarousel />
    </div>

    <!-- Sección del contenido -->
    <div
      class="w-full md:w-1/2 min-h-[60vh] md:h-screen bg-gradient-to-br from-purple-900 via-pink-900 to-purple-900 flex items-center justify-center px-4 py-8 md:px-8 lg:px-12"
    >
      <div class="w-full max-w-md mx-auto">
        <h1
          class="text-3xl sm:text-4xl md:text-5xl font-bold mb-4 text-transparent bg-clip-text bg-gradient-to-r from-pink-300 to-purple-200"
        >
          Chat Privado
        </h1>

        <div class="space-y-4 mb-6">
          <p class="text-lg sm:text-xl md:text-2xl text-pink-100">Descubre conexiones especiales</p>

          <div class="flex justify-center gap-4 sm:gap-8 md:gap-12 text-pink-200">
            <div class="flex flex-col items-center">
              <span class="text-2xl sm:text-3xl mb-1">✨</span>
              <span class="text-sm sm:text-base">Discreto</span>
            </div>
            <div class="flex flex-col items-center">
              <span class="text-2xl sm:text-3xl mb-1">🌹</span>
              <span class="text-sm sm:text-base">Romántico</span>
            </div>
            <div class="flex flex-col items-center">
              <span class="text-2xl sm:text-3xl mb-1">💫</span>
              <span class="text-sm sm:text-base">Exclusivo</span>
            </div>
          </div>
        </div>

        <div class="bg-white/10 backdrop-blur-sm rounded-2xl sm:rounded-3xl p-4 sm:p-6 md:p-8">
          <p class="text-base sm:text-lg md:text-xl mb-4 sm:mb-6 text-pink-100">
            ✨ Únete a nuestra comunidad y vive experiencias inolvidables
          </p>

          <a
            href="https://wa.link/m2qjnd"
            target="_blank"
            class="inline-block w-full sm:w-auto bg-gradient-to-r from-pink-400 to-purple-400 hover:from-pink-500 hover:to-purple-500 text-white px-6 sm:px-8 md:px-10 py-3 sm:py-4 rounded-full text-base sm:text-lg md:text-xl font-bold transition-all duration-300 hover:shadow-xl shadow-lg hover:scale-[1.02]"
          >
            Comenzar a Chatear 💝
          </a>
        </div>

        <div class="mt-4">
          <p class="text-xs sm:text-sm text-pink-200/80">
            Ambiente seguro y respetuoso para personas mayores de edad
          </p>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
.hover\:scale-102:hover {
  transform: scale(1.02);
}
</style>
