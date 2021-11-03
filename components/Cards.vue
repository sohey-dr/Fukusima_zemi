<template>
  <div class="container mx-auto p-8">
    <div class="flex flex-row flex-wrap -mx-2">
      <div class="w-full sm:w-1/2 md:w-1/3 mb-4 px-2">
        <div class="relative bg-white rounded border">
          <picture class="block bg-gray-200 border-b">
            <img
              class="block"
              src="https://via.placeholder.com/800x600/EDF2F7/E2E8F0/&amp;text=Card"
              alt="Card 1"
            />
          </picture>
          <div class="p-4">
            <h3 class="text-lg font-bold">
              <nuxt-link class="stretched-link" to="/finite_population">世論調査の必要なサンプル数を出す計算</nuxt-link>
            </h3>
          </div>
        </div>
      </div>

      <div class="w-full sm:w-1/2 md:w-1/3 mb-4 px-2">
        <div class="relative bg-white rounded border">
          <picture class="block bg-gray-200 border-b">
            <img
              class="block"
              src="https://via.placeholder.com/800x600/EDF2F7/E2E8F0/&amp;text=Card"
              alt="Card 2"
            />
          </picture>
          <div class="p-4">
            <h3 class="text-lg font-bold">
              <nuxt-link class="stretched-link" to="/dnd" title="Card 2">カード並び替え</nuxt-link>
            </h3>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
